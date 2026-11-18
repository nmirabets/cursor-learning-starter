# Project context for the agent

## Who you are working with

A data analytics bootcamp graduate. They know Python, pandas, matplotlib/seaborn, SQL, descriptive and inferential statistics, and the basics of scikit-learn (train/test split, linear and logistic regression, decision trees, random forests, common metrics). They are new to working with an AI agent.

## What this repo is for

Learning. The goal is not a finished notebook; it is a student who can explain and defend every line and every decision in it. The always-on rule in `.cursor/rules/learning-mode.mdc` says how to behave. Follow it even when it would be faster to just write the code.

## Workflow (any dataset)

1. Explore: `explore-data` skill, producing `eda.ipynb` and `DATA_NOTES.md`.
2. Frame: `frame-question` skill, producing `QUESTION.md`. The question comes from the student.
3. Plan and build: `plan-analysis` skill (analysis) or `guided-ml` skill (machine learning), or the student's own prompt.

## Projects

Each project folder holds its `data/`, `PROJECT_BRIEF.md`, `DATA_NOTES.md`, `QUESTION.md` and notebooks.

- `01_data_analysis/`: Barcelona Airbnb listings (in class).
- `02_machine_learning/`: telecom customer churn (homework; the student's own prompt is in `prompts/my-ml-prompt.md`).

## Conventions

- Environment: `.venv` with the libraries in `requirements.txt`. Do not add a library without asking the student first; if they agree, add it to `requirements.txt` and `docs/TECH_STACK.md`.
- Work in Jupyter notebooks inside each project folder (for example `01_data_analysis/analysis.ipynb`). Read data with relative paths (`data/...`).
- Decisions go in `docs/DECISIONS.md`; tools and libraries in `docs/TECH_STACK.md`.
- You write and run the cells; the student reads them and makes the analysis decisions. Never ask them to paste output.
