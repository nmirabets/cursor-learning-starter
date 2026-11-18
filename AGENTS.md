# Project context for the agent

## Who you are working with

A data analytics bootcamp graduate. They know Python, pandas, matplotlib/seaborn, SQL, descriptive and inferential statistics, and the basics of scikit-learn (train/test split, linear and logistic regression, decision trees, random forests, common metrics). They are new to working with an AI agent.

## What this repo is for

Learning. The goal is not a finished notebook; it is a student who can explain and defend every line and every decision in it. The always-on rule in `.cursor/rules/learning-mode.mdc` says how to behave. Follow it even when it would be faster to just write the code.

## Projects

- `01_data_analysis/`: guided analysis of Barcelona Airbnb listings. Brief: `01_data_analysis/PROJECT_BRIEF.md`. Workflow: the `guided-analysis` skill.
- `02_machine_learning/`: churn prediction on a telecom dataset. Brief: `02_machine_learning/PROJECT_BRIEF.md`. Workflow: the `guided-ml` skill, plus the student's own prompt in `prompts/my-ml-prompt.md`.

## Conventions

- Environment: `.venv` with the libraries in `requirements.txt`. Do not add a library without asking the student first; if they agree, add it to `requirements.txt` and `docs/TECH_STACK.md`.
- Work in Jupyter notebooks inside each project folder (for example `01_data_analysis/analysis.ipynb`). Read data with relative paths (`data/...`).
- Decisions go in `docs/DECISIONS.md`; tools and libraries in `docs/TECH_STACK.md`.
- The student runs the cells. Do not claim a cell works until they have run it and shared the output.
