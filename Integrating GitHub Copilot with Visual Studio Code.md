
Integrating **GitHub Copilot** with **Visual Studio Code** and connecting VS Code with **Git** turns your editor into an AI-powered, version-controlled workspace.

## Part 1: How to Integrate GitHub Copilot with VS Code

### Prerequisites

- A GitHub account with access to GitHub Copilot (either a paid plan or the Copilot Free plan).
    

### Step-by-Step Setup

1. **Install the GitHub Copilot Extension**:
2. 
    - Open VS Code.
        
    - Open the Extensions view by clicking the Extensions icon on the Activity Bar (left side) or pressing `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (macOS).
        
    - Search for **GitHub Copilot**.
        
    - Click **Install**. _(Installing this automatically includes or prompts you to install **GitHub Copilot Chat**)_.
        
2. **Sign In and Authenticate**:
    
    - Click on the **Accounts** icon in the bottom-left corner or hover over the **Copilot icon** in the Status Bar at the bottom right.
        
    - Select **Sign in with GitHub to use GitHub Copilot**.
        
    - A browser window will open asking you to authorize Visual Studio Code. Click **Authorize GitHub**.
        
3. **How to Use Copilot in VS Code**:
    
    - **Inline Suggestions**: Start typing code. Copilot will show grayed-out ghost text.
        
        - Press `Tab` to accept.
            
        - Press `Esc` to reject.
            
        - Press `Alt + ]` (Windows) / `Option + ]` (macOS) to view alternative suggestions.
            
    - **Copilot Chat**: Click the Chat icon on the left panel or press `Ctrl+Alt+I` / `Cmd+Ctrl+I` to open the AI chat window for explaining code, generating tests, or debugging.
        

## Part 2: How to Sync VS Code with Git

To use Git in VS Code, Git must first be installed on your computer.

### Step 1: Verify Git Installation & User Setup

1. Download and install Git from [git-scm.com](https://git-scm.com/) if you haven't already.
    
2. Open your terminal inside VS Code (`Ctrl+~` or `Cmd+~`) and configure your global name and email (used for commit attribution):
    
    Bash
    
    ```
    git config --global user.name "Your Name"
    git config --global user.email "your.email@example.com"
    ```
    

### Step 2: Connect a Project to Git / GitHub

Choose one of the following methods depending on your project state:

- **Option A: Clone an Existing Remote Repository**
    
    1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`).
        
    2. Type and select `Git: Clone`.
        
    3. Enter the repository URL (e.g., `[https://github.com/username/repository.git](https://github.com/username/repository.git)`) or select **Clone from GitHub** to pick from your repositories.
        
- **Option B: Publish a Local Project to GitHub**
    
    1. Open your project folder in VS Code.
        
    2. Click the **Source Control** icon on the Activity Bar (`Ctrl+Shift+G` / `Cmd+Shift+G`).
        
    3. Click **Publish to GitHub**.
        
    4. Follow the prompts to log in to GitHub and choose whether to make the repository Public or Private.
        

### Step 3: Daily Syncing (Commit, Push, Pull)

VS Code provides a graphical interface so you don't need to run CLI commands for daily workflow:

1. **Stage & Commit Changes**:
    
    - Open the **Source Control** view (`Ctrl+Shift+G`).
        
    - Hover over changed files under **Changes** and click the **`+`** sign to Stage them.
        
    - Type a commit message in the message box at the top.
        
    - Click **Commit** (or press `Ctrl+Enter` / `Cmd+Enter`).
        
2. **Sync Changes**:
    
    - Once committed, click the blue **Sync Changes** button.
        
    - This performs a `git pull` (fetches remote changes) followed by a `git push` (uploads local commits).
        

### Pro Tip: Enable Auto-Fetch for Real-Time Syncing

To keep VS Code updated with remote changes automatically without manually refreshing:

1. Open Settings (`Ctrl+,` or `Cmd+,`).
    
2. Search for **`git.autofetch`**.
    
3. Set `Git: Autofetch` to **`all`** or **`true`**.
    

VS Code will now periodically check your remote repository and display incoming ($\downarrow$) or outgoing ($\uparrow$) commit counters in the bottom Status Bar.


