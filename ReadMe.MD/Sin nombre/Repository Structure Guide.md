# Repository Structure Strategy

This guide provides a blueprint for your two-repo setup. Using this approach keeps your self-study "lab" separate from your formal academic "records," making your profile look clean and highly organized to recruiters.

## 1. Repository: `cs-engineer-workspace` (The Lab)

**Goal:** Self-directed learning, experimentation, and tech mastery.

```
cs-engineer-workspace/
├── README.md              # Global Portfolio Dashboard (Bio + Roadmap)
├── 03_python/             # Organized by concept
│   ├── 01_core/           # Python Syntax, OOP
│   ├── 02_pandas/         # Data analysis
│   ├── 04_fastapi/        # Web frameworks
│   └── README.md          # Detailed Python index & links to notebooks
└── ...
```

**Key Tip:** Your `README.md` here is your "Home Page." Use it to link to your other repositories.

## 2. Repository: `cs-coursework-labs` (The Academic Hub)

**Goal:** Documenting formal university projects and graded assignments.

```
cs-coursework-labs/
├── README.md              # Academic Transcript/Course List
├── 01_software_arch/
│   ├── assignment_01_design_patterns/
│   └── README.md          # Assignment details, grade, and requirements
├── 02_database_systems/
│   └── lab_01_sql_optimization/
└── ...
```

## 3. How to Cross-Link (The "Cohesive" Effect)

In the `README.md` of your **`cs-engineer-workspace`**, create a section that points to your other repo:

```
## 🎓 Academic Portfolio
If you'd like to see my formal university coursework, assignments, and graded projects, check out my companion repository:

👉 [**View Academic Labs & Coursework**](https://github.com/rco-workspace/cs-coursework-labs)
```

## 💡 Pro-Tip: The "README" Hierarchy

- **Root `README.md`:** Think of this as your "Executive Summary." Keep it short. Link out to the deep-dives.
    
- **Subfolder `README.md`:** Think of these as "Project Reports." Include specific technical details, links to external docs (like FastAPI docs), and your own Jupyter notebooks.
    

This setup allows a recruiter to see your "Professional Engineering" skills at a glance, then dig deeper into your "Formal Education" if they need to verify your background.

