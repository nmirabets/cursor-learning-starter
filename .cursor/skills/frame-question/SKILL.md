---
name: frame-question
description: Helps a learner turn their own curiosity about a dataset into a clear, answerable analysis or machine learning question, written to QUESTION.md in the project folder. Use when the user runs /frame-question, or wants to decide what to analyse, what to predict, or how to phrase their research question.
---

# Frame the question

Goal: a question the learner chose, that matters to someone, and that this data can answer. Follow `.cursor/rules/learning-mode.mdc`. `DATA_NOTES.md` and `QUESTION.md` live in the project folder, next to `data/`.

**The question comes from the learner.** Never propose an analysis question, not even as options, before they have written one. If they are stuck, ask what surprised them in `DATA_NOTES.md`, or who in the brief would care about which decision.

## Steps

1. Read `DATA_NOTES.md` and the project brief. If `DATA_NOTES.md` has only the template headings, suggest `/explore-data` first.
2. Ask in chat: "What do you want to find out? Write it however it comes out." Wait.
3. Sharpen it, one aspect at a time. Ask first; offer options only to refine what they said. Aim for about 6 turns in total.
   - **Who and why.** Who would use the answer, and what would they do differently?
   - **Measurable.** Which columns and calculation turn each vague word into a number ("big customers" means the top 10% by revenue? more than N orders?).
   - **Scope.** Which rows, and which comparison (A vs B, trend, ranking, relationship)?
   - **Feasible.** You check this and report it; it is not a question for them. If it depends on a number not in the notes (group sizes, share missing), give them a cell of up to 5 lines to run in `eda.ipynb` and ask what they see.
   - **Expectation.** What do they expect to find, and what would surprise them?
4. For a **machine learning** question, also cover: what exactly is predicted (the target), at what moment, which columns are known at that moment, what action follows a prediction, and who is hurt by each kind of wrong prediction.
5. Ask them to write the final question in one sentence from what you agreed. Check it against the signs below and point out at most one problem.
6. Write `QUESTION.md` using its sections, with their words, and add the main choices to `docs/DECISIONS.md`.

Then suggest `/plan-analysis` in Plan mode in a new chat (or `/guided-ml` / their own prompt for a machine learning question).

## Signs of a question that needs more work

- It can be answered with a single number that tells nobody what to do.
- It asks "why" but the data can only show "what" or "how much" (correlation is not causation).
- It needs a column that is not in the data.
- Its groups are too small to compare (a handful of rows).
- It is really three questions; ask which one comes first.
