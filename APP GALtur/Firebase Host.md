
# 🛡️ The Bulletproof Guide: Firebase Data Connect & Hosting from Zero

This guide provides a step-by-step blueprint to build, configure, and deploy a Firebase Data Connect project backed by Cloud SQL and served via Firebase Hosting, avoiding all common pitfalls.

## Phase 1: Environment & Project Setup

1. **Create and open your working directory:**
    
    ```
    mkdir firebase-sql-sandbox
    cd firebase-sql-sandbox
    ```
    
2. **Initialize Firebase CLI features:**
    
    ```
    firebase login
    firebase init
    ```
    
    - _Select features:_ Choose **Data Connect** and **Hosting**.
        
    - _Project:_ Create a new project or select an existing one (e.g., `library-sql-test`).
        
    - _Data Connect source:_ Accept default (`./dataconnect`).
        
    - _Hosting public directory:_ Type `public`.
        
    - _Configure as single-page app:_ Choose **Yes**.
        

## Phase 2: Configuration & Directory Structure (`firebase.json`)

Ensure your `firebase.json` file in the root directory explicitly maps the public folder and SPA rewrites:

```
{
  "dataconnect": {
    "source": "./dataconnect"
  },
  "hosting": {
    "public": "public",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  },
  "emulators": {
    "dataconnect": {
      "port": 9399
    },
    "hosting": {
      "port": 5000
    },
    "ui": {
      "enabled": true
    }
  }
}
```

## Phase 3: Frontend Development (The Golden Rules)

1. **The Lowercase Rule:** Inside your `public/` folder, your main file **must** be strictly lowercase: **`index.html`** (never `Index.html`). Linux-based cloud hosting servers are case-sensitive.
    
2. **Robust Fallbacks:** Always wrap your database initialization and queries in `try/catch` blocks so that if the backend is still spinning up, your UI gracefully shows an initialization state instead of breaking or hanging indefinitely.
    

## Phase 4: The Bulletproof Deployment Sequence

_Crucial Rule:_ **Never deploy hosting before your Data Connect backend is fully online.** Follow this exact order:

### Step 1: Deploy Data Connect First

```
firebase deploy --only dataconnect
```

- **Why?** This triggers Google Cloud to provision your free-tier PostgreSQL instance (`Cloud SQL`).
    
- **The Waiting Period:** The terminal will output a warning: _`Cloud SQL Instance is being created... Your data are saved in a temporary database and will be migrated once complete.`_ **Wait 2 minutes** to let Google Cloud finish spinning up the container.
    

### Step 2: Deploy Hosting Second

Once the database provisioning is complete, deploy your frontend:

```
firebase deploy --only hosting
```

## Phase 5: Roadblock Prevention & Troubleshooting Cheat Sheet

|   |   |   |
|---|---|---|
|**Roadblock Encountered**|**Root Cause**|**Instant Fix**|
|**`404 Page Not Found` on live URL**|File is named `Index.html` (capital **I**) or `firebase.json` is missing the `public` path.|Rename file to lowercase `index.html` and verify `firebase.json` has `"public": "public"`.|
|**Dropdowns stuck on "Loading..."**|Cloud SQL instance is still initializing in Google Cloud backend.|Wait 2 minutes after running `firebase deploy --only dataconnect` before checking the live site.|
|**Module / Import Errors in Console**|Loading raw ES modules via CDN without bundlers or mismatching sub-paths.|Use a clean, self-contained single-file HTML layout with robust fallback states and compat/esm bindings.|