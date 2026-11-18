---
name: guided-ml
description: Plans and then builds, one cell at a time, a supervised machine learning project for the learner's framed question in docs/QUESTION.md (metric, validation, baseline, features, models, evaluation, error analysis, communication) for the framed question in the project folder's QUESTION.md, with the learner making every modelling decision. Use when the user runs /guided-ml, or asks to plan, start or continue a machine learning or prediction project.
---

# Guided machine learning

Goal: a model that serves the decision in `QUESTION.md`, built by a learner who can defend every modelling choice. Follow `.cursor/rules/learning-mode.mdc`. If the learner gave you their own prompt, it takes priority where it is more specific than this skill, but never over `learning-mode.mdc`. `QUESTION.md`, `DATA_NOTES.md` and `model.ipynb` live in the project folder, next to `data/`.

If `model.ipynb` already has cells, skip to Part 2 at the first unfinished phase of the saved plan.

## Part 1: Planning (Plan mode, read-only)

If you are not in Plan mode, ask them to switch (`Shift+Tab`); write no files until the plan is approved. Read `QUESTION.md`, `DATA_NOTES.md`, the project brief and the first lines of the data. If `QUESTION.md` does not say what is predicted, when, and what action follows, suggest `/frame-question` first and stop.

Ask one at a time, open question first, then options with trade-offs:

1. **Success metric.** Given the action and the cost of each kind of error in `QUESTION.md`: accuracy (and when it misleads, for example with an imbalanced target), recall, precision, F1, ROC AUC, precision among the top-k. Which one will they optimise, and which will they report?
2. **Validation.** Stratified train/test split, or split plus cross-validation? What does each protect against?
3. **Leakage.** Which columns would not be known at prediction time, or encode the target? The learner decides what to drop.
4. **Baseline.** The simplest thing to beat (majority class, one rule from `DATA_NOTES.md`).
5. **Candidate models.** Two or three to compare, and the interpretability vs performance trade-off.
6. **Tools.** pandas + scikit-learn (+ seaborn for charts). Explain `Pipeline` and `ColumnTransformer` in one line each and ask whether to use them or do the steps by hand first.

Then write a plan with: **Question**, **Technologies** (tool and its job here), **Phases** (below, each with open decisions and "done when"), **Decisions** with reasons, **How we build**: "Build starts with phase 1 only. One cell at a time in `model.ipynb`; the learner runs every cell. Stop at the end of each phase for its checkpoint." Make the to-dos match: one per phase, each worded "Phase N: one cell at a time; stop after each cell for the learner to run."

## Part 2: Building, one phase at a time

First write the planning decisions to `docs/DECISIONS.md` and the stack to `docs/TECH_STACK.md`. Then:

1. **Load and prepare.** Fix the data issues from `DATA_NOTES.md` that matter for modelling; the learner decides each one.
2. **Target and split.** Encode the target. Split **before** fitting anything; ask why the order matters.
3. **Baseline.** Compute the chosen metric for the baseline.
4. **Features.** One decision at a time: encoding categoricals, scaling (needed for which models?), dropping ids and leaky columns, any feature they want to create.
5. **Models.** Train each candidate. Before showing scores, ask which they expect to win and why.
6. **Evaluation.** Confusion matrix and the chosen metrics on the test set. Threshold: does 0.5 fit the action and its costs? Let them choose.
7. **Error analysis and explanation.** Look at the wrong predictions together. Coefficients or feature importances: what would they tell the person in `QUESTION.md`, and what does the model **not** prove (correlation, not causation)?
8. **Wrap-up.** Notebook runs top to bottom; `DECISIONS.md` and `TECH_STACK.md` complete. Suggest `/review` and `/quiz-me`.

## Checkpoint at the end of every phase

One question that checks understanding (for example "Why did we fit the scaler on the training set only?"). Move on when they can answer it, or after you have explained it.
