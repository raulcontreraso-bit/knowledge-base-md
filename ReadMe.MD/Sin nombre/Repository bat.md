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
````