---
name: frame-question
description: Helps a learner turn their own curiosity about a dataset into a clear, answerable analysis or machine learning question, written to QUESTION.md in the project folder. Use when the user runs /frame-question, or wants to decide what to analyse, what to predict, or how to phrase their research question.
---

# Frame the question

Goal: a question the learner chose, that matters to someone, and that this data can answer. Follow `.cursor/rules/learning-mode.mdc`. `DATA_NOTES.md` and `QUESTION.md` live in the project folder, next to `data/`.

**The question comes from the learner.** Never propose one, not even as options, before they have written one. If they are stuck, point them to "Things I'm curious about" in `DATA_NOTES.md` and to who in the brief needs an answer.

## Steps

1. Read `DATA_NOTES.md` and the brief. If the notes are still the empty template, suggest `/explore-data` first.
2. Ask: "What do you want to find out? Write it however it comes out."
3. Make it precise. Ask only what their wording leaves open, usually 2 or 3 of these, with options where they help:
   - **Who and what for**: who uses the answer and what will they do with it?
   - **Measure**: which columns and calculation turn the vague words into numbers?
   - **Scope and comparison**: which rows; groups, trend, ranking or relationship?
4. **Check feasibility yourself**: run a quick check (group sizes, share missing, columns needed) and tell them the result. If something blocks the question (tiny groups, a missing column, "why" when the data can only show "what"), say so and ask how they want to adjust.
5. For a **machine learning** question, also settle: the target, the moment the prediction is made (and which columns are known then), the action that follows, and which error is worse.
6. Write the agreed question in one sentence and ask them to confirm or reword it. Fill in `QUESTION.md` and log the main choices in `docs/DECISIONS.md`.

Then suggest `/plan-analysis` in Plan mode in a new chat (or `/guided-ml` or their own prompt for a machine learning question).
