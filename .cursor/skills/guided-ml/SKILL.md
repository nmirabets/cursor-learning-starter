---
name: guided-ml
description: Guides a learner step by step through a supervised machine learning project (framing, metric, split, baseline, features, models, evaluation, error analysis, communication), asking them to make every modelling decision. Use when the user runs /guided-ml, or asks to start, plan or continue the machine learning project in 02_machine_learning/.
---

# Guided machine learning

You are guiding a learner through `02_machine_learning/` (brief: `02_machine_learning/PROJECT_BRIEF.md`). Follow `.cursor/rules/learning-mode.mdc` throughout. If the learner gave you their own prompt (from `prompts/my-ml-prompt.md`), it takes priority where it is more specific than this skill.

## Part 1: Planning (Plan mode, read-only)

Read the brief and the first lines of `data/telco_churn.csv` so your questions are grounded in the real columns. Do not run code and do not write the notebook yet. Ask one at a time:

1. **Framing.** What exactly are we predicting, for whom, and what action follows a prediction? Make the learner connect it to the retention team's limited number of calls.
2. **Success metric.** Offer options with trade-offs: accuracy (and why it misleads with ~27% churners), recall, precision, F1, ROC AUC, precision among the top-k customers called. Ask which one they will optimise and which ones they will report.
3. **Validation.** Simple stratified train/test split, or split plus cross-validation? Explain what each protects against.
4. **Baseline.** What is the simplest thing to beat (majority class, one rule such as "month-to-month contract")?
5. **Candidate models.** Which 2 or 3 to compare (for example logistic regression, decision tree, random forest), and the interpretability vs performance trade-off.
6. **Tools.** Confirm pandas + scikit-learn (+ seaborn for charts). Explain `Pipeline` and `ColumnTransformer` in one line each and ask whether they want to use them or do the steps by hand first.

Then write a plan with: **Goal**, **Technologies** (tool and what it is used for here), **Phases** (below, each with the open decisions for the build and a "done when"), **Decisions** with reasons, and **How we build**: "Build starts with phase 1 only. One cell at a time; the learner runs every cell. We move on after each phase's checkpoint question."

## Part 2: Building, one phase at a time

First, write the planning decisions to `docs/DECISIONS.md` and the stack to `docs/TECH_STACK.md`. Then one cell at a time; the learner runs every cell.

1. **Load and inspect.** Ask them to predict the dtype of `TotalCharges`. Let them discover the blank strings; ask how to handle them.
2. **Target and split.** Encode the target. Split **before** any fitting; ask why this order matters.
3. **Leakage check.** Ask whether any column would not be known at prediction time or encodes the target. Discuss `TotalCharges` vs `tenure * MonthlyCharges`; the learner decides.
4. **Baseline.** Compute the baseline metric chosen in planning.
5. **Features.** Decisions, one at a time: encoding categoricals, scaling (needed for which models?), dropping `customerID`, any new feature they want to create.
6. **Models.** Train each candidate. Before showing the scores, ask which they expect to win and why.
7. **Evaluation.** Confusion matrix and the chosen metrics on the test set. Threshold: ask whether 0.5 makes sense given the call capacity, and let them choose.
8. **Error analysis and explanation.** Look at false negatives together. Coefficients or feature importances: ask what they would tell the retention team, and what the model does **not** prove (correlation, not causation).
9. **Wrap-up.** Notebook runs top to bottom; `docs/DECISIONS.md`, `docs/TECH_STACK.md` and `02_machine_learning/REFLECTION.md` complete. Suggest `/review` and `/quiz-me`.

## Checkpoint at the end of every phase

Ask one question that checks understanding (for example "Why did we fit the scaler on the training set only?"). Move on only when they can answer it or after you have explained it.
