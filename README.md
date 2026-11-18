# Cursor learning starter

A starter repo for learning to work with an AI coding agent **without handing over your thinking**.

The agent in this repo is set up as a guide, not a ghostwriter. **You** decide what to explore, which question to answer and how. The agent writes small pieces of code, explains them, offers options with their trade-offs, and asks you what you notice. You read and run every line.

```
01_data_analysis/      in class: Barcelona Airbnb listings
02_machine_learning/   homework: telecom customer churn
  data/                  the dataset
  PROJECT_BRIEF.md       the client and the data dictionary
  DATA_NOTES.md          what you learn while exploring
  QUESTION.md            the question you chose to answer
prompts/               how to write a prompt for an agent + your template
docs/DECISIONS.md      every decision you make, and why
docs/TECH_STACK.md     every tool and library you use, and why
.cursor/rules/         always-on instructions for the agent (learning mode)
.cursor/skills/        workflows: /explore-data, /frame-question, /plan-analysis, /guided-ml
.cursor/commands/      reusable prompts: /explain, /review, /quiz-me
AGENTS.md              who you are and what this project is for
```

## 1. Setup (once)

1. Install [Cursor](https://cursor.com/download) and sign in. Students: check [cursor.com/students](https://cursor.com/students) for the current student offer.
2. Install the extensions **Python** and **Jupyter** from the Extensions panel (`Cmd+Shift+X` / `Ctrl+Shift+X`). Check the publisher is `ms-python` / `ms-toolsai` before installing.
3. Create your own copy of this repo: click **Use this template** on GitHub, then clone your copy:

   ```bash
   git clone https://github.com/<your-user>/<your-repo>.git
   cd <your-repo>
   cursor .
   ```

4. Create a virtual environment and install the libraries (in Cursor's terminal, `` Ctrl+` ``):

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate        # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   ```

5. Open any `.ipynb`, click **Select Kernel** (top right) and pick `.venv`.

## 2. How to work in this repo

The same four steps work for any dataset. Open the Agent panel (`Cmd+I` / `Ctrl+I`); start a new chat for each step.

1. **Explore**, in Agent mode: `/explore-data`. You choose what to look at; after each output, say what you notice. You end with `DATA_NOTES.md`.
2. **Frame**, in Agent mode: `/frame-question`. Write the question **you** want to answer; the agent helps you make it precise and answerable. You end with `QUESTION.md`.
3. **Plan**, in Plan mode (`Shift+Tab`): `/plan-analysis` (or your own prompt / `/guided-ml` for the ML project). Answer its questions, read the plan, edit it, and click **Build** only when you understand every step.
4. **Build and review**: run every cell yourself, use `/explain` on anything you can't explain out loud, and finish with `/review` and `/quiz-me`.

If the agent goes in the wrong direction, do not patch it with ten follow-up messages. Go back to the plan, fix it, and run it again.

## Data and licenses

- `01_data_analysis/data/barcelona_listings.csv`: a random sample (8,000 of 15,236 listings, seed 42, 31 columns) of the [Inside Airbnb](https://insideairbnb.com/get-the-data/) Barcelona snapshot from 2026-09-17. Licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) by Inside Airbnb.
- `02_machine_learning/data/telco_churn.csv`: IBM Telco Customer Churn sample dataset, from [IBM/telco-customer-churn-on-icp4d](https://github.com/IBM/telco-customer-churn-on-icp4d), Apache 2.0.
