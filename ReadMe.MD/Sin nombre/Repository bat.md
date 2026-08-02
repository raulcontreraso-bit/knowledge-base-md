Here are the exact contents of both `.bat` files provided directly in the chat window so you can copy and paste them without any formatting issues.

### File 1: `init_repo.bat`

Copy the code below, open **Notepad**, paste it, and save as `init_repo.bat` (make sure "Save as type" is set to **All Files (_._)**):

DOS

```
@echo off
:: Initializing git repository
git init

:: Creating master README.md file
echo # Raul Contreras O. > README.md
echo. >> README.md
echo ### SAP Consultant ^& Software Engineering Professional >> README.md
echo. >> README.md
echo `user@rc-workspace:~$ cat summary.txt` >> README.md
echo. >> README.md
echo With 16+ years of experience in SAP S/4HANA ^(SD, WM, EWM^), I am currently bridging the gap between enterprise-grade ERP systems and modern web architecture. >> README.md
echo. >> README.md
echo Currently pursuing an **MS in Web Development**. >> README.md
echo. >> README.md
echo ## 🛠️ Technical Stack >> README.md
echo. >> README.md
echo ![SAP Fiori](https://img.shields.io/badge/SAP-Fiori-blue?logo=sap^&logoColor=white) >> README.md
echo ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript^&logoColor=black) >> README.md
echo ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5^&logoColor=white) >> README.md
echo ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3^&logoColor=white) >> README.md
echo ![Python](https://img.shields.io/badge/Python-3776AB?logo=python^&logoColor=white) >> README.md
echo ![FastAPI](https://img.shields.io/badge/FastAPI-05998B?logo=fastapi^&logoColor=white) >> README.md
echo ![React](https://img.shields.io/badge/React-61DAFB?logo=react^&logoColor=black) >> README.md
echo. >> README.md
echo --- >> README.md
echo. >> README.md
echo ## 🏗️ Engineering ^& Academic Hubs >> README.md
echo. >> README.md
echo ### 💻 Engineering Workspace >> README.md
echo *Focus: Hands-on labs, Fiori prototyping, and backend engineering.* >> README.md
echo. >> README.md
echo * [**Python Engineering**](cs-engineer-workspace/02_python/): FastAPI, data integration, and automation. >> README.md
echo * [**SAP Fiori Prototypes**](cs-engineer-workspace/03_fiori/): Responsive UI5/Fiori components bridging legacy S/4HANA systems. >> README.md
echo. >> README.md
echo ### 🚀 Project Showcase >> README.md
echo *Featured builds demonstrating full-stack integration.* >> README.md
echo. >> README.md
echo * [**Turismo App**](cs-engineer-workspace/projects/turismo-mapa/): Interactive travel guide integrated with Google Maps API. >> README.md
echo * [**E-commerce Store**](cs-engineer-workspace/projects/shop-app/): Modern shopping cart application with state management. >> README.md
echo. >> README.md
echo ### 🎓 Academic Hub ^(MS in Web Development^) >> README.md
echo *Focus: Formal Master's degree coursework, system design, and architecture.* >> README.md
echo. >> README.md
echo * [**Advanced Web Architecture**](cs-coursework-labs/01_advanced_arch/): Distributed systems and API design. >> README.md
echo * [**Modern Frontend**](cs-coursework-labs/02_frontend/): React, advanced CSS, and UI/UX engineering. >> README.md
echo. >> README.md
echo --- >> README.md
echo. >> README.md
echo ## 🔗 Connect >> README.md
echo. >> README.md
echo [LinkedIn](https://linkedin.com/in/raulcontreraso) ^| [Email](mailto:raul.contreras.cl@gmail.com) >> README.md

:: Commit initial file
git add README.md
git commit -m "Initial commit: Setup master README index"

echo Repository initialized successfully!
pause
```

### File 2: `create_folders.bat`

Copy the code below into a new file, open **Notepad**, paste it, and save as `create_folders.bat` in the same directory:

DOS

```
@echo off
:: Creating directory structure
mkdir "cs-engineer-workspace\projects\turismo-mapa"
mkdir "cs-engineer-workspace\projects\shop-app"
mkdir "cs-engineer-workspace\02_python"
mkdir "cs-engineer-workspace\03_fiori"
mkdir "cs-coursework-labs\01_advanced_arch"
mkdir "cs-coursework-labs\02_frontend"

:: Generating blank README files in each folder
echo # Python Engineering > "cs-engineer-workspace\02_python\README.md"
echo # SAP Fiori Prototypes > "cs-engineer-workspace\03_fiori\README.md"
echo # Turismo App > "cs-engineer-workspace\projects\turismo-mapa\README.md"
echo # E-commerce Store > "cs-engineer-workspace\projects\shop-app\README.md"
echo # Advanced Web Architecture > "cs-coursework-labs\01_advanced_arch\README.md"
echo # Modern Frontend > "cs-coursework-labs\02_frontend\README.md"

:: Staging and committing structure
git add .
git commit -m "Add project folder structure and initial README files"

echo Folders and README files created successfully!
pause
```

### How to execute:

1. Save both files in your main project folder.
    
2. Double-click `init_repo.bat` first.
    
3. Double-click `create_folders.bat` second. 

---


Yes, absolutely! You can create your root folder (e.g., `cs-engineer-workspace`) directly in Windows using File Explorer or Command Prompt first, and then run the scripts right inside it.

Here is how you can do it step-by-step:

### Step 1: Create the Main Folder

1. Open Windows File Explorer.
    
2. Go to where you want your project to live (e.g., `C:\Users\YourName\Documents` or `D:\Projects`).
    
3. Create a new folder and name it **`cs-engineer-workspace`**.
    

### Step 2: Place the `.bat` Files Inside

Place both **`init_repo.bat`** and **`create_folders.bat`** directly inside your new `cs-engineer-workspace` folder.

### Step 3: Run the Scripts

1. Open the `cs-engineer-workspace` folder.
    
2. **Double-click `init_repo.bat`**:
    
    - This creates the local Git repository inside this folder.
        
    - It creates your master **`README.md`** file with all your bio info, badges, and project links.
        
3. **Double-click `create_folders.bat`**:
    
    - This creates all the subfolders (`projects\turismo-mapa`, `02_python`, `03_fiori`, etc.).
        
    - It adds a `README.md` to each subfolder.
        
    - It saves everything to your local Git history.
        

### What to do next (Pushing to GitHub)

Once you run both scripts, if you want this repository hosted online on GitHub:

1. Go to [GitHub](https://github.com/) and create a **New Repository** named `cs-engineer-workspace` (leave it empty—do not check "Initialize with a README").
    
2. Open **Command Prompt** (or terminal) inside your `cs-engineer-workspace` folder.
    
3. Run these two commands to connect and push your code:
    

DOS

```
git remote add origin https://github.com/raulcontreraso-bit/cs-engineer-workspace.git
git add .
git commit -m "Add project folder structure and initial README files"
git push -u origin main
```

_(Replace `YOUR-USERNAME` with your actual GitHub account handle)._



Yes, that exact sequence of commands is **100% correct**!

Here is what each step is doing under the hood to ensure everything goes smoothly:

1. **`git remote add origin [https://github.com/raulcontreraso-bit/cs-engineer-workspace.git](https://github.com/raulcontreraso-bit/cs-engineer-workspace.git)`**
    
    Connects your local Windows folder to your online GitHub repository.
    
2. **`git add .`**
    
    Stages all your new folders and `README.md` files for the commit.
    
3. **`git commit -m "Add project folder structure and initial README files"`**
    
    Saves a snapshot of your new project structure in your local Git history.
    
4. **`git push -u origin main`**
    
    Uploads everything to GitHub and sets `main` as your default tracking branch.
    

### One Quick Tip Before Pushing

If `init_repo.bat` created your default local branch as `master` instead of `main`, running `git push -u origin main` might give you a minor error (_"src refspec main does not match any"_).

If that happens, just rename your local branch to `main` first by running:

DOS

```
git branch -M main
git remote add origin https://github.com/raulcontreraso-bit/cs-engineer-workspace.git
git add .
git commit -m "Add project folder structure and initial README files"
git push -u origin main
```

Otherwise, if you're already on `main`, your exact sequence will work perfectly!


--- 

Yes, **exactly!** You are in the right spot.

You must run those Git commands directly inside `C:\Users\raulc\Desktop\Main_Repo\cs-engineer-workspace`.

### Step-by-Step Command Execution

In your Command Prompt, type these commands in order:

1. **Rename the local branch to `main`** _(ensures compatibility with GitHub defaults)_:
    
    DOS
    
    ```
    git branch -M main
    ```
    
2. **Connect your local folder to GitHub**:
    
    DOS
    
    ```
    git remote add origin https://github.com/raulcontreraso-bit/cs-engineer-workspace.git
    ```
    
3. **Stage all your newly created files and folders**:
    
    DOS
    
    ```
    git add .
    ```
    
4. **Commit the changes**:
    
    DOS
    
    ```
    git commit -m "Add project folder structure and initial README files"
    ```
    
5. **Push everything up to GitHub**:
    
    DOS
    
    ```
    git push -u origin main
    ```
    

Once step 5 completes, refresh your GitHub page at `[https://github.com/raulcontreraso-bit/cs-engineer-workspace](https://github.com/raulcontreraso-bit/cs-engineer-workspace)`—your entire folder structure and master `README.md` will be live!




To **create** a fresh local Git repository inside a folder, the command is:

DOS

```
git init
```

### Understanding the Difference

- **`git init`**
    
    **Creates** a new local Git repository from scratch inside the current directory. It creates a hidden `.git` folder that turns your regular folder into a tracked repository.
    
- **`git remote add origin <URL>`**
    
    **Links** an already created local repository to your remote account on GitHub.
    

### Complete Setup Flow (Creating + Linking)

If you are inside `C:\Users\raulc\Desktop\Main_Repo\cs-engineer-workspace` and haven't initialized Git yet, run these commands in order:

DOS

```
:: 1. Create the local repository
git init

:: 2. Rename the default branch to main
git branch -M main

:: 3. Link it to your GitHub account
git remote add origin https://github.com/raulcontreraso-bit/cs-engineer-workspace.git

:: 4. Add your files
git add .

:: 5. Commit your files
git commit -m "Initial commit: Add project folder structure and README files"

:: 6. Push to GitHub
git push -u origin main
```

---

Your local Git repository was actually created and committed successfully—everything worked locally!

The error **`fatal: repository ... not found`** happens because GitHub does not automatically create a repository on `github.com` just because you ran `git remote add`. You have to create the empty repository on GitHub's website first.

### How to Fix This (2-Minute Fix):

#### 1. Create the repository on GitHub

1. Go to [github.com/new](https://github.com/new).
    
2. Set the **Repository name** to: `cs-engineer-workspace`
    
3. Make sure it is set to **Public** (or **Private** if you prefer).
    
4. **Important:** Leave **"Add a README file"**, **"Add .gitignore"**, and **"Choose a license"** **UNCHECKED** (your local repository already has these files).
    
5. Click **Create repository**.
    

#### 2. Push your local code again

Go back to your PowerShell terminal in `C:\Users\raulc\Desktop\Main_Repo\cs-engineer-workspace` and run:

PowerShell

```
git push -u origin main
```

### Alternative Error Reason:

If you _already_ created the repository on GitHub, check these two quick items:

- **Username typo:** Verify that your GitHub username is spelled exactly as `raulcontreraso-bit`.
    
- **Repository name typo:** Verify the repository name on GitHub matches `cs-engineer-workspace` word-for-word.
    

Once you create the empty repository on GitHub, that `git push` command will succeed!


Your local Git repository was actually created and committed successfully—everything worked locally!

The error **`fatal: repository ... not found`** happens because GitHub does not automatically create a repository on `github.com` just because you ran `git remote add`. You have to create the empty repository on GitHub's website first.

### How to Fix This (2-Minute Fix):

#### 1. Create the repository on GitHub

1. Go to [github.com/new](https://github.com/new).
    
2. Set the **Repository name** to: `cs-engineer-workspace`
    
3. Make sure it is set to **Public** (or **Private** if you prefer).
    
4. **Important:** Leave **"Add a README file"**, **"Add .gitignore"**, and **"Choose a license"** **UNCHECKED** (your local repository already has these files).
    
5. Click **Create repository**.
    

#### 2. Push your local code again

Go back to your PowerShell terminal in `C:\Users\raulc\Desktop\Main_Repo\cs-engineer-workspace` and run:

PowerShell

```
git push -u origin main
```

### Alternative Error Reason:

If you _already_ created the repository on GitHub, check these two quick items:

- **Username typo:** Verify that your GitHub username is spelled exactly as `raulcontreraso-bit`.
    
- **Repository name typo:** Verify the repository name on GitHub matches `cs-engineer-workspace` word-for-word.
    

Once you create the empty repository on GitHub, that `git push` command will succeed!


----

Congrats on getting the initial push working! Now that your repository is live on GitHub, updating it as you build projects, add labs, or edit files follows a simple **3-step workflow**.

Whenever you make changes on your computer, run these commands in your terminal inside `C:\Users\raulc\Desktop\Main_Repo\cs-engineer-workspace`:

### The 3-Step Daily Workflow

PowerShell

```
# Step 1: Stage all your changes (new files, edits, deleted files)
git add .

# Step 2: Save a snapshot with a message describing what you changed
git commit -m "Add new FastAPI backend lab"

# Step 3: Send your changes up to GitHub
git push
```

_(Note: You only needed `-u origin main` on the very first push. For all future pushes, a plain `git push` is all you need!)_

### Useful Commands to Keep Handy

|**Command**|**What It Does**|
|---|---|
|`git status`|Shows which files have been modified, created, or deleted before you commit.|
|`git log --oneline`|Shows a clean, 1-line history of all your past commits.|
|`git pull`|Downloads changes from GitHub to your computer (useful if you ever edit files directly on GitHub's website).|

### Recommended Habit

Before you close your laptop or finish working for the day:

1. Run `git status` to see what you worked on.
    
2. Run `git add .`
    
3. Run `git commit -m "Describe today's progress"`
    
4. Run `git push`
    

This ensures your online GitHub profile is always up-to-date with your latest work!


---



Here is a simple `.bat` file that automates those three steps for you.

It will prompt you to type your commit message, stage all modified or new files, commit them with your message, and push everything to GitHub automatically.

### `update_repo.bat`

Copy the code below, open **Notepad**, paste it, and save it as **`update_repo.bat`** (with "Save as type" set to **All Files (_._)**) directly inside your `cs-engineer-workspace` folder:

DOS

```
@echo off
echo ===================================
echo   Syncing Workspace with GitHub
echo ===================================
echo.

:: Step 1: Stage all changes
git add .
echo [OK] All changes staged.
echo.

:: Ask for commit message
set /p msg="Enter a brief commit message (e.g., Updated README or Added new lab): "

:: Step 2: Commit changes
git commit -m "%msg%"
echo.

:: Step 3: Push to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo   Repository Updated Successfully!
echo ===================================
pause
```

### How to use it:

1. Whenever you add new files or make edits, just **double-click `update_repo.bat`**.
    
2. Type a short description of what you did when prompted (e.g., _Updated Python lab notes_) and press **Enter**.
    
3. The script will handle the `git add`, `git commit`, and `git push` commands for you!




----

To target only a specific subfolder, you just need to pass that relative path to `git add` and `git commit` instead of using `.` (which targets the entire repository root).

Here is an updated batch script tailored specifically for updating **`cs-engineer-workspace\02_python`**.

### `update_python.bat`

Save this file as `update_python.bat` inside your main repository folder:

DOS

```
@echo off
echo ===================================
echo   Syncing 02_python with GitHub
echo ===================================
echo.

:: Step 1: Stage changes ONLY in the 02_python directory
git add "cs-engineer-workspace\02_python"
echo [OK] Staging changes in cs-engineer-workspace\02_python...
echo.

:: Ask for commit message
set /p msg="Enter a commit message for Python changes: "

:: Step 2: Commit only the staged files in that folder
git commit -m "[02_python] %msg%"
echo.

:: Step 3: Push changes to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo   Python Folder Synced Successfully!
echo ===================================
pause
```

### Key Adjustments Made:

1. **`git add "cs-engineer-workspace\02_python"`**: Tells Git to stage modified, deleted, or new files exclusively inside the `02_python` folder. Any edits made in other directories (like `03_fiori` or `projects`) will be ignored for this commit.
    
2. **`[02_python] %msg%`**: Automatically prefixes your commit message with `[02_python]` so your Git commit history stays clean and organized by module.



---









Here is the corrected batch script.

To add a prefix (like `[02_python]` or `[Workspace Update]`) to your commit message and use a default fallback message if you hit Enter, you can handle the `set /p` prompt like this:

### Option A: Fixed Prefix + Custom Message

This script automatically prefixes **whatever you type** (or uses "Routine update" if left blank) with `[Workspace Update]`:

DOS

```
@echo off
echo ===================================
echo    Syncing Workspace with GitHub
echo ===================================
echo.

:: Step 1: Stage all changes
git add .
echo [OK] All changes staged.
echo.

:: Ask for commit message with a fallback default
set "user_msg="
set /p user_msg="Enter commit message (Press ENTER for default): "

:: If input is empty, set a default message
if "%user_msg%"=="" set user_msg=Routine update

:: Combine prefix with the user message
set "msg=[Workspace Update] %user_msg%"

:: Step 2: Commit changes
git commit -m "%msg%"
echo.

:: Step 3: Push to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo    Repository Updated Successfully!
echo ===================================
pause
```

### Option B: Interactive Choice for Folder Prefixes

If you want to **choose** which section prefix to attach before committing:

DOS

```
@echo off
echo ===================================
echo    Syncing Workspace with GitHub
echo ===================================
echo.

:: Select Prefix
echo Select a module prefix:
echo 1) [Workspace]
echo 2) [02_python]
echo 3) [03_fiori]
echo 4) [Projects]
echo.
set /p choice="Choose (1-4, default is 1): "

set "prefix=[Workspace]"
if "%choice%"=="2" set "prefix=[02_python]"
if "%choice%"=="3" set "prefix=[03_fiori]"
if "%choice%"=="4" set "prefix=[Projects]"

:: Step 1: Stage all changes
git add .
echo [OK] All changes staged.
echo.

:: Ask for custom message
set "user_msg="
set /p user_msg="Enter commit description: "
if "%user_msg%"=="" set user_msg=Updated workspace files

set "msg=%prefix% %user_msg%"

:: Step 2: Commit changes
git commit -m "%msg%"
echo.

:: Step 3: Push to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo    Repository Updated Successfully!
echo ===================================
pause
```

### Fixes made from your draft:

1. **Removed `echo` before `set /p`:** In Windows batch files, `echo set /p ...` prints the code itself as plain text instead of asking for user input.
    
2. **Fixed assignment spacing:** In batch files, `msg= "..."` (with a space) creates a variable with a space in its name (`%msg %`). Using `set "msg=..."` prevents string variable bugs.



--------



















Here is the corrected batch script.

To add a prefix (like `[02_python]` or `[Workspace Update]`) to your commit message and use a default fallback message if you hit Enter, you can handle the `set /p` prompt like this:

### Option A: Fixed Prefix + Custom Message

This script automatically prefixes **whatever you type** (or uses "Routine update" if left blank) with `[Workspace Update]`:

DOS

```
@echo off
echo ===================================
echo    Syncing Workspace with GitHub
echo ===================================
echo.

:: Step 1: Stage all changes
git add .
echo [OK] All changes staged.
echo.

:: Ask for commit message with a fallback default
set "user_msg="
set /p user_msg="Enter commit message (Press ENTER for default): "

:: If input is empty, set a default message
if "%user_msg%"=="" set user_msg=Routine update

:: Combine prefix with the user message
set "msg=[Workspace Update] %user_msg%"

:: Step 2: Commit changes
git commit -m "%msg%"
echo.

:: Step 3: Push to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo    Repository Updated Successfully!
echo ===================================
pause
```

### Option B: Interactive Choice for Folder Prefixes

If you want to **choose** which section prefix to attach before committing:

DOS

```
@echo off
echo ===================================
echo    Syncing Workspace with GitHub
echo ===================================
echo.

:: Select Prefix
echo Select a module prefix:
echo 1) [Workspace]
echo 2) [02_python]
echo 3) [03_fiori]
echo 4) [Projects]
echo.
set /p choice="Choose (1-4, default is 1): "

set "prefix=[Workspace]"
if "%choice%"=="2" set "prefix=[02_python]"
if "%choice%"=="3" set "prefix=[03_fiori]"
if "%choice%"=="4" set "prefix=[Projects]"

:: Step 1: Stage all changes
git add .
echo [OK] All changes staged.
echo.

:: Ask for custom message
set "user_msg="
set /p user_msg="Enter commit description: "
if "%user_msg%"=="" set user_msg=Updated workspace files

set "msg=%prefix% %user_msg%"

:: Step 2: Commit changes
git commit -m "%msg%"
echo.

:: Step 3: Push to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo    Repository Updated Successfully!
echo ===================================
pause
```

### Fixes made from your draft:

1. **Removed `echo` before `set /p`:** In Windows batch files, `echo set /p ...` prints the code itself as plain text instead of asking for user input.
    
2. **Fixed assignment spacing:** In batch files, `msg= "..."` (with a space) creates a variable with a space in its name (`%msg %`). Using `set "msg=..."` prevents string variable bugs.


The error `fatal: pathspec 'cs-engineer-workspace\02_python' did not match any files` happens because of your **current working folder**.

Since `update_python.bat` is running **inside** `cs-engineer-workspace` (as shown in your File Explorer path at the top), Windows looks for `cs-engineer-workspace\cs-engineer-workspace\02_python`, which doesn't exist.

Inside this folder, the path is simply **`02_python`**.

### Corrected `update_python.bat`

Here is the fixed code. Open `update_python.bat` in Notepad, replace its content with this, and save:

DOS

```
@echo off
echo ===================================
echo   Syncing 02_python with GitHub
echo ===================================
echo.

:: Step 1: Stage changes ONLY inside 02_python
git add "02_python"
echo [OK] Staging changes in 02_python...
echo.

:: Ask for commit message
set /p msg="Enter a commit message for Python changes: "

:: Step 2: Commit only staged files in that folder
git commit -m "[02_python] %msg%"
echo.

:: Step 3: Push changes to GitHub
echo Pushing changes to GitHub...
git push
echo.

echo ===================================
echo   Python Folder Synced Successfully!
echo ===================================
pause
```

### Rule of thumb:

- If running from **inside** `cs-engineer-workspace`, use `git add "02_python"`.
    
- If running from the parent directory (`Main_Repo`), use `git add "cs-engineer-workspace\02_python"`.

You are thinking ahead, and that is a great setup! Setting up a `.gitignore`, Python virtual environments, and workspace-specific VS Code settings is essential to keep your repository clean and ensure VS Code automatically selects the right Python interpreter based on which folder you are working in.

Here is how to set up all three components cleanly:

## 1. Create a `.gitignore` File

You don't want to commit compiled Python files (`__pycache__`), virtual environments (`.venv`), or temporary IDE caches to GitHub.

Create a file named **`.gitignore`** in the root directory (`C:\Users\raulc\Desktop\Main_Repo\cs-engineer-workspace`) and add the following:

Code snippet

```
# Python bytecode & cache
__pycache__/
*.py[cod]
*$py.class

# Python Virtual Environments
.venv/
env/
venv/
ENV/

# VS Code directory settings (except project workspace settings if you share them)
.vscode/*.log

# Operating System Files
.DS_Store
Thumbs.db

# Environment variables & secrets
.env
```

## 2. Setting Up Python Virtual Environments (`.venv`)

For python projects (like in `02_python` or `projects/turismo-mapa`), it is best practice to create isolated virtual environments so dependencies don't collide.

Inside your folder (for example `02_python`), open PowerShell/Command Prompt and run:

PowerShell

```
# Navigate to your target folder
cd 02_python

# Create the virtual environment named .venv
python -m venv .venv
```

_(Because `.venv` is in your `.gitignore`, Git will automatically ignore this folder, keeping your GitHub repository small and fast!)_

## 3. Configuring VS Code Settings (`.vscode/settings.json`)

To make VS Code automatically use the virtual environment for python files in specific folders, you can set up workspace settings.

In the root of your project (`cs-engineer-workspace`), create a hidden folder named `.vscode` and place a file inside called `settings.json`:

`cs-engineer-workspace\.vscode\settings.json`

JSON

```
{
  "python.defaultInterpreterPath": "${workspaceFolder}/02_python/.venv/Scripts/python.exe",
  "python.terminal.activateEnvironment": true,
  "editor.formatOnSave": true,
  "python.formatting.provider": "black",
  "files.exclude": {
    "**/__pycache__": true,
    "**/*.pyc": true
  }
}
```

### Pro-Tip for Multi-Folder Python Environments:

If you have multiple folders with their own separate environments (e.g., one in `02_python` and one in `projects/turismo-mapa`), you can use a **VS Code Multi-Root Workspace**:

1. In VS Code, go to **File > Save Workspace As...** and save `cs-engineer-workspace.code-workspace`.
    
2. This allows you to define unique Python interpreters for individual sub-folders directly in the workspace configuration file.