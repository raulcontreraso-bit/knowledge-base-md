
# End-to-End Implementation Guide: JupyterLite to GitHub Direct Sync

This guide provides a comprehensive, step-by-step walkthrough for building and deploying a custom JupyterLab toolbar button extension in a static **JupyterLite** instance hosted on **GitHub Pages**, paired with a **Cloudflare Worker** acting as a secure proxy to commit notebooks directly to your GitHub repository via the GitHub REST API.

## Architecture Overview

1. **JupyterLite Frontend (User Interface):** A custom TypeScript extension injects a **"Save to GitHub"** button into the notebook toolbar.
    
2. **Local Browser Save:** Clicking the button triggers an internal save (`context.save()`) and extracts the notebook's JSON payload and filename.
    
3. **Cloudflare Worker (Secure Proxy):** Receives the HTTP POST request. Because it hosts your private GitHub Personal Access Token (`GITHUB_REPO_TOKEN`) as an environment secret, the token is never exposed to the public browser frontend.
    
4. **GitHub REST API:** The worker checks if the file exists on your target branch, retrieves its file `sha` if present, and commits the updated notebook content directly.
    

## Step 1: Set Up the Cloudflare Worker Proxy

The Cloudflare Worker receives notebook payloads from your browser extension, handles GitHub authentication, and performs the commit via the GitHub Contents API.

### 1. Create and Configure the Worker

Create a new worker (e.g., `jupyterlite-sync`) in your Cloudflare dashboard and paste the following JavaScript code into `worker.js`:

```
export default {
  async fetch(request, env) {
    const corsHeaders = {
      "Access-Control-Allow-Origin": "*",
      "Access-Control-Allow-Methods": "GET, POST, OPTIONS",
      "Access-Control-Allow-Headers": "Content-Type, Authorization"
    };

    // Handle CORS preflight requests
    if (request.method === "OPTIONS") {
      return new Response(null, { headers: corsHeaders });
    }

    if (request.method !== "POST") {
      return new Response(JSON.stringify({ error: "Method not allowed" }), {
        status: 405,
        headers: { ...corsHeaders, "Content-Type": "application/json" }
      });
    }

    try {
      const body = await request.json();
      const { filename, content } = body;

      if (!filename || !content) {
        return new Response(JSON.stringify({ error: "Missing filename or content" }), {
          status: 400,
          headers: { ...corsHeaders, "Content-Type": "application/json" }
        });
      }

      const repoOwner = env.GITHUB_REPO_OWNER; // e.g., "raulcontreraso-bit"
      const repoName = env.GITHUB_REPO_NAME;   // e.g., "my-study-notebooks_devops"
      const branch = env.GITHUB_BRANCH || "feature/github-sync";
      const token = env.GITHUB_REPO_TOKEN;

      const filePath = `content/notebooks/${filename}`;
      const apiUrl = `https://api.github.com/repos/${repoOwner}/${repoName}/contents/${filePath}`;

      // 1. Check if file already exists to retrieve its current SHA (required for updates)
      let fileSha = null;
      const getResponse = await fetch(`${apiUrl}?ref=${branch}`, {
        headers: {
          "Authorization": `Bearer ${token}`,
          "User-Agent": "JupyterLite-GitHub-Sync-Worker",
          "Accept": "vnd.github+json"
        }
      });

      if (getResponse.ok) {
        const fileData = await getResponse.json();
        fileSha = fileData.sha;
      }

      // 2. Prepare payload for GitHub Contents API
      const fileContentString = JSON.stringify(content, null, 2);
      const encodedContent = btoa(unescape(encodeURIComponent(fileContentString)));

      const commitPayload = {
        message: `Sync notebook ${filename} from JupyterLite [skip ci]`,
        content: encodedContent,
        branch: branch,
        ...(fileSha && { sha: fileSha })
      };

      // 3. Commit/Update file via GitHub API
      const putResponse = await fetch(apiUrl, {
        method: "PUT",
        headers: {
          "Authorization": `Bearer ${token}`,
          "User-Agent": "JupyterLite-GitHub-Sync-Worker",
          "Content-Type": "application/json",
          "Accept": "vnd.github+json"
        },
        body: JSON.stringify(commitPayload)
      });

      if (!putResponse.ok) {
        const errorText = await putResponse.text();
        throw new Error(`GitHub API error: ${putResponse.status} - ${errorText}`);
      }

      return new Response(JSON.stringify({ success: true, message: `Successfully committed ${filename}` }), {
        status: 200,
        headers: { ...corsHeaders, "Content-Type": "application/json" }
      });

    } catch (err) {
      return new Response(JSON.stringify({ success: false, error: err.message }), {
        status: 500,
        headers: { ...corsHeaders, "Content-Type": "application/json" }
      });
    }
  }
};
```

### 2. Configure Cloudflare Environment Variables

In your Cloudflare Worker settings under **Settings > Variables**, add the following environment secrets:

- `GITHUB_REPO_OWNER`: Your GitHub username (e.g., `raulcontreraso-bit`)
    
- `GITHUB_REPO_NAME`: Your repository name (e.g., `my-study-notebooks_devops`)
    
- `GITHUB_BRANCH`: Target branch for commits (e.g., `feature/github-sync`)
    
- `GITHUB_REPO_TOKEN`: A GitHub Personal Access Token (PAT) with `repo` scope permissions.
    

## Step 2: Build the JupyterLab Frontend Extension

Create a subdirectory in your repository named `extension/` to house your custom JupyterLab UI extension.

### 1. `extension/package.json`

Defines the Node dependencies and registers the extension output directory for Hatchling.

```
{
  "name": "jupyterlite-github-sync",
  "version": "0.1.0",
  "description": "Extension to sync notebooks directly to GitHub.",
  "main": "lib/index.js",
  "types": "lib/index.d.ts",
  "files": [
    "lib/**/*.{d.ts,js,js.map}",
    "style/**/*.{css,js,eot,gif,html,jpg,otf,png,svg,ttf,woff,woff2}"
  ],
  "sideEffects": [
    "-style/*.css",
    "style/*.css"
  ],
  "jupyterlab": {
    "extension": true,
    "outputDir": "jupyterlite_github_sync/labextension"
  },
  "scripts": {
    "build": "tsc --build",
    "clean": "tsc --build --clean"
  },
  "dependencies": {
    "@jupyterlab/application": "^4.0.0",
    "@jupyterlab/apputils": "^4.0.0",
    "@jupyterlab/docregistry": "^4.0.0",
    "@jupyterlab/notebook": "^4.0.0",
    "@lumino/disposable": "^2.0.0"
  },
  "devDependencies": {
    "@jupyter/builder": "^1.0.0",
    "typescript": "~5.0.0"
  }
}
```

### 2. `extension/tsconfig.json`

TypeScript configuration for compiling the extension.

```
{
  "compilerOptions": {
    "target": "es2022",
    "module": "esnext",
    "moduleResolution": "node",
    "lib": ["es2022", "DOM"],
    "declaration": true,
    "sourceMap": true,
    "strict": true,
    "noUnusedLocals": false,
    "noUnusedParameters": false,
    "noImplicitReturns": true,
    "skipLibCheck": true,
    "outDir": "lib",
    "rootDir": "src"
  },
  "include": ["src/**/*"]
}
```

### 3. `extension/src/index.ts`

Implements the JupyterLab widget extension that injects the **"Save to GitHub"** button into the toolbar and handles HTTP communication with your Cloudflare Worker.

```
import {
  JupyterFrontEnd,
  JupyterFrontEndPlugin
} from '@jupyterlab/application';

import { INotebookTracker, NotebookPanel, INotebookModel } from '@jupyterlab/notebook';
import { ToolbarButton } from '@jupyterlab/apputils';
import { DocumentRegistry } from '@jupyterlab/docregistry';
import { IDisposable, DisposableDelegate } from '@lumino/disposable';

// Your deployed Cloudflare Worker base URL (NO trailing slash)
const WORKER_BASE_URL = 'https://jupyterlite-sync.raulcontreraso.workers.dev';

export class GitHubSyncButtonExtension
  implements DocumentRegistry.IWidgetExtension<NotebookPanel, INotebookModel>
{
  createNew(
    panel: NotebookPanel,
    context: DocumentRegistry.IContext<INotebookModel>
  ): IDisposable {
    const button = new ToolbarButton({
      className: 'github-sync-button',
      label: 'Save to GitHub',
      onClick: async () => {
        // 1. Ensure the notebook is fully saved locally in the browser first
        await context.save();

        const content = context.model.toJSON();
        const filename = context.path.split('/').pop() || 'untitled.ipynb';

        button.node.textContent = 'Syncing...';

        try {
          // 2. Post payload to Cloudflare Worker endpoint
          const response = await fetch(`${WORKER_BASE_URL}/save-notebook`, {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json'
            },
            body: JSON.stringify({
              filename: filename,
              content: content
            })
          });

          const result = await response.json();

          if (response.ok && result.success) {
            alert(`Successfully synced ${filename} to GitHub branch feature/github-sync!`);
            button.node.textContent = 'Save to GitHub';
          } else {
            throw new Error(result.error || 'Unknown error from worker');
          }
        } catch (error: any) {
          console.error('GitHub Sync Error:', error);
          alert(`Failed to sync: ${error.message}`);
          button.node.textContent = 'Save to GitHub';
        }
      },
      tooltip: 'Commit this notebook directly to your GitHub repository'
    });

    // Insert button into notebook toolbar
    panel.toolbar.insertItem(10, 'githubSync', button);
    
    return new DisposableDelegate(() => {
      button.dispose();
    });
  }
}

const plugin: JupyterFrontEndPlugin<void> = {
  id: 'jupyterlite-github-sync:plugin',
  autoStart: true,
  requires: [INotebookTracker],
  activate: (app: JupyterFrontEnd, tracker: INotebookTracker) => {
    app.docRegistry.addWidgetExtension('Notebook', new GitHubSyncButtonExtension());
  }
};

export default plugin;
```

### 4. `extension/pyproject.toml`

Configures Hatchling to package compiled lab extensions into the Python wheel shared data structure required by JupyterLite.

```
[build-system]
requires = ["hatchling>=1.5.0", "hatch-jupyter-builder>=0.5"]
build-backend = "hatchling.build"

[project]
name = "jupyterlite-github-sync"
version = "0.1.0"
description = "Extension to sync notebooks directly to GitHub."
readme = "README.md"
requires-python = ">=3.8"
dependencies = [
    "jupyterlab>=4.0.0,<5"
]

[tool.hatch.build]
artifacts = [
    "jupyterlite_github_sync/labextension"
]

[tool.hatch.build.targets.wheel]
packages = ["jupyterlite_github_sync"]

[tool.hatch.build.targets.wheel.shared-data]
"jupyterlite_github_sync/labextension" = "share/jupyter/labextensions/jupyterlite-github-sync"

[tool.hatch.build.hooks.jupyter-builder]
dependencies = ["hatch-jupyter-builder>=0.5"]
build-function = "hatch_jupyter_builder.npm_builder"
ensured-targets = [
    "jupyterlite_github_sync/labextension/package.json"
]

[tool.hatch.build.hooks.jupyter-builder.build-kwargs]
build_cmd = "build"
npm = ["npm"]

[tool.hatch.build.hooks.jupyter-builder.editable-build-kwargs]
build_cmd = "build"
npm = ["npm"]
```

## Step 3: Configure CI/CD Deployment Pipeline (`.github/workflows/deploy.yml`)

Create your GitHub Actions workflow file to build the TypeScript extension, compile the Python wheel, inject it into JupyterLite, and deploy to GitHub Pages.

```
name: Build and Deploy

on:
  push:
    branches:
      - main
      - feature/github-sync
  pull_request:
    branches:
      - '*'

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: Install Python build tools and dependencies
        run: |
          python -m pip install --upgrade pip
          python -m pip install hatchling hatch-jupyter-builder build
          python -m pip install -r requirements.txt

      - name: Build custom JupyterLab extension
        run: |
          cd extension
          npm install
          npm run build
          jupyter-builder build .
          python -m build --wheel
          pip install dist/*.whl
          jupyter labextension list

      - name: Build the JupyterLite site
        run: |
          cp README.md content
          jupyter lite build --contents content --output-dir dist

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./dist

  deploy:
    needs: build
    if: github.ref == 'refs/heads/main' || github.ref == 'refs/heads/feature/github-sync'
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## Step 4: Verification and Testing

1. **Commit & Push:** Push all files (`extension/src/index.ts`, `extension/package.json`, `extension/tsconfig.json`, `extension/pyproject.toml`, and `.github/workflows/deploy.yml`) to your repository.
    
2. **Monitor Actions:** Watch the GitHub Actions tab until the workflow turns green.
    
3. **Hard Refresh Browser:** Open your deployed JupyterLite URL (`https://<username>.github.io/<repo>/lab/index.html`). Perform a hard refresh (`Ctrl + Shift + R` or `Cmd + Shift + R`) to purge old service workers.
    
4. **Test Sync:** Open any `.ipynb` notebook, make an edit, click the **"Save to GitHub"** button in the toolbar, and confirm the success alert. Check your target branch on GitHub to verify the direct commit.


Yes! The approach you implemented combines two standard design patterns recommended across the Jupyter and JupyterLite documentation communities:

  

1. **JupyterLab Frontend Extension Architecture:** JupyterLite runs entirely in the browser via WebAssembly (Wasm), meaning it uses the exact same frontend extension hooks as standard JupyterLab. You can read more about how JupyterLite handles browser extensions and static assets in the [Official JupyterLite How-To Guides for Extensions](https://jupyterlite.readthedocs.io/en/latest/howto/index.html).
    
      
    
2. **The Stateless / Client-Side Persistence Challenge:** Because JupyterLite saves files to volatile local browser storage (`IndexedDB` via `localForage`), cross-device syncing or pushing back to an upstream repository requires a custom synchronization bridge. Discussions regarding cloud sync architectures, external storage backends, and Git integrations are heavily discussed in upstream developer issues like the [JupyterLite File Storage and Synchronization Issue #315](https://github.com/jupyterlite/jupyterlite/issues/315), where developers explore bridging the Jupyter Contents API with external REST endpoints or secure proxies like Cloudflare Workers.