---
name: guided-ml
description: Plans and then builds, phase by phase, a supervised machine learning project (metric, validation, leakage, baseline, features, models, evaluation, threshold, explanation) for the framed question in the project folder's QUESTION.md, with the learner making every modelling decision. Use when the user runs /guided-ml, or asks to plan, start or continue a machine learning or prediction project.
---

# Guided machine learning

Goal: a model that serves the decision in `QUESTION.md`, built by a learner who can defend every modelling choice. Follow `.cursor/rules/learning-mode.mdc`; if the learner gave you their own prompt, it takes priority where it is more specific, but never over the rule. `QUESTION.md`, `DATA_NOTES.md` and `model.ipynb` live in the project folder, next to `data/`.

If `model.ipynb` already has cells, continue from the first unfinished phase of the saved plan.

## Part 1: Plan (Plan mode)

Read `QUESTION.md`, `DATA_NOTES.md`, the brief and the data. If `QUESTION.md` does not say what is predicted, when, and what action follows, suggest `/frame-question` first.

Ask the modelling decisions, one at a time, with options and trade-offs:

1. **Metric**: given the action and the cost of each error, which metric to optimise and which to report (accuracy and when it misleads, recall, precision, F1, ROC AUC, precision in the top-k).
2. **Validation**: stratified train/test split, or split plus cross-validation.
3. **Leakage**: which columns would not be known at prediction time or encode the target.
4. **Baseline**: the simplest thing to beat.
5. **Candidate models**: 2 or 3, and the interpretability vs performance trade-off.

Write the plan: **Question**, **Technologies**, **Phases** (each with open decisions and "done when"), **Decisions** with reasons, **How we build**: "One phase at a time; stop at each open decision."

## Part 2: Build, one phase at a time

Write the decisions to `docs/DECISIONS.md` and the stack to `docs/TECH_STACK.md`. For each phase, write and run the cells, give your read of the results, and stop at the next decision:

1. **Prepare**: fix the data issues that matter for modelling; the learner decides each one that changes results.
2. **Split** before fitting anything, then compute the **baseline**.
3. **Features**: encoding, scaling, dropping ids and leaky columns, any feature they want to add.
4. **Models**: train the candidates and compare them on the chosen metric.
5. **Threshold**: show what different thresholds mean for the action (for example, how many people to contact and how many churners you'd catch); the learner chooses.
6. **Explain**: errors, coefficients or feature importances; the learner writes what they'd tell the team and what the model does **not** prove.
7. Make sure "Restart and Run All" works. Suggest `/review`.
