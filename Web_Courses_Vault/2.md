vscv


> [!abstract] Workspace Directory Map
> ```text
```
Web_Courses_Vault/
│
├── .obsidian/                    # Obsidian config & settings
├── .github/
│   └── workflows/
│       └── deploy.yml            # Auto-publishes to GitHub Pages on push
│
├── _templates/                   # Templates for fast note creation
│   ├── Course_Module_Template.md
│   └── Chapter_Note_Template.md
│
├── _assets/                      # Images, diagrams, and attachments
│
├── .gitignore                    # Ignores _build/, .venv/, etc.
├── myst.yml                      # Master config & Table of Contents
├── README.md                     # Main vault homepage
│
├── 01_python/                    # Python Fundamentals
│   ├── index.md                  # Python Module Overview
│   ├── 01_basics.md              # Notes with embedded code blocks
│   └── 02_data_structures.ipynb  # Interactive Jupyter Notebook
│
├── 02_pandas/                    # Data Science & Pandas
│   ├── index.md                  # Pandas Module Overview
│   └── aaltoscicomp.ipynb        # Aalto SciComp Pandas Review
│
├── 03_frontend/                  # Front-End Web Dev
│   ├── index.md
│   └── 01_html_css.md
│
└── 04_backend/                   # Back-End Web Dev
    ├── index.md
    └── 01_sql_basics.md
```





> [!abstract] Workspace Directory Map
> ```text
> 📁 Web_Courses_Vault/
> ├── 00_ACTIVE_PROJECTS/
> │   ├── WEB/
> │   ├── APP/
> │   └── AI_ML/
> ├── 01_PYTHON_VAULT/
> │   ├── 00_Cheatsheets_&_Snippets/
> │   ├── 01_Data_Science_&_Analytics/
> │   │   ├── Pandas/
> │   │   ├── NumPy/
> │   │   ├── Matplotlib_Seaborn/
> │   │   └── Polars/
> │   ├── 02_AI_&_Machine_Learning/
> │   │   ├── PyTorch/
> │   │   ├── OpenAI_API/
> │   │   ├── LangChain_LlamaIndex/
> │   │   ├── HuggingFace/
> │   │   └── Scikit_Learn/
> │   ├── 03_Web_Frameworks/
> │   │   ├── FastAPI/
> │   │   ├── Django/
> │   │   └── Flask/
> │   └── 04_Automation_&_Scraping/
> │       ├── Playwright_Selenium/
> │       ├── BeautifulSoup/
> │       └── Requests_Aiohttp/
> ├── 02_LEARNING_&_RESEARCH/
> │   ├── Online_Courses/
> │   ├── Video_Courses/



Web_Courses_Vault/
│
├── 01_python/
│   ├── index.md                      # Overview of the Python Ecosystem
│   │
│   ├── 00_vanilla/                   # Pure Python Fundamentals
│   │   ├── 01_basics.md              # Syntax, Variables, Control Flow
│   │   ├── 02_data_structures.ipynb  # Lists, Dicts, Sets, Tuples
│   │   └── 03_oop_and_modules.md     # Classes, Functions, Imports
│   │
│   ├── 01_pandas/                    # Data Manipulation & Cleaning
│   │   ├── index.md                  # Pandas Overview
│   │   └── aaltoscicomp.ipynb        # Aalto SciComp Review
│   │
│   ├── 02_numpy/                     # Numerical & Vectorized Computing
│   │   └── 01_arrays_matrices.ipynb
│   │
│   ├── 03_matplotlib_seaborn/        # Data Visualization
│   │   └── 01_plotting_basics.ipynb
│   │
│   └── 04_scikit_learn/              # Machine Learning Basics
│       └── 01_intro_to_ml.ipynb
│
├── 02_frontend/                      # HTML, CSS, JS, React
│   └── ...
│
└── 03_backend/                       # Node.js, FastAPI, SQL
    └── ...