---
name: plan-analysis
description: Plans and then builds, one cell at a time, a data analysis that answers the learner's question in the project folder's QUESTION.md, with the learner proposing the steps and making every method decision. Use when the user runs /plan-analysis, or asks to plan, start or continue the analysis that answers their question.
---

# Plan and build the analysis

Goal: answer the learner's question in `QUESTION.md` with an analysis they can explain and defend. Follow `.cursor/rules/learning-mode.mdc`. `QUESTION.md`, `DATA_NOTES.md` and `analysis.ipynb` live in the project folder, next to `data/`.

If `analysis.ipynb` already has cells, skip to Part 2 at the first unfinished phase of the saved plan.

## Part 1: Planning (Plan mode, read-only)

If you are not in Plan mode, ask them to switch (`Shift+Tab`); write no files until the plan is approved.

1. Read `QUESTION.md`, `DATA_NOTES.md`, the project brief and the first lines of the data. If `QUESTION.md` has only the template headings, suggest `/frame-question` first and stop.
2. Ask once, in chat: "List the steps you would take to answer your question, 3 to 6 bullets, rough is fine."
3. Their steps become the phases. If a data-preparation step, a robustness check or the written answer is missing, ask why before adding it.
4. Then ask only about decisions their steps leave open or get wrong, at most 4, most important first: which data issues matter and what to do about each; the measure (mean or median, counts or shares, per what unit); the comparison; descriptive only or also a test or interval; the chart. Put low-stakes ones (chart style, tools) in one form. Anything still open goes into its phase as an open decision.
5. If you see an issue that matters and is not in `DATA_NOTES.md`, point at it with a question ("How many rows does each group have?") instead of naming it and its fix.
6. Write the plan:
   - **Question**: copied from `QUESTION.md`.
   - **Technologies**: each tool and its job here (becomes `docs/TECH_STACK.md`). Use `requirements.txt`; if the evidence needs another library (for example scipy for a test), explain and ask; if they agree, the first build step adds it.
   - **Phases**: their steps, each with what we will do, the decisions still open (as questions) and "done when".
   - **Decisions**: the answers so far, with reasons.
   - **How we build**: "Build starts with phase 1 only. One cell at a time in `analysis.ipynb`; the learner runs every cell. Stop at the end of each phase for its checkpoint."
   - **To-dos**: one per phase, each worded "Phase N: one cell at a time; stop after each cell for the learner to run."
7. Tell them to read and edit the plan, save it to the workspace, and press Build only when they could explain every step to a classmate.

## Part 2: Building, one phase at a time

1. Write the planning decisions to `docs/DECISIONS.md` and the stack to `docs/TECH_STACK.md` (and `requirements.txt` if a library was added).
2. For each phase: restate its goal in one sentence, ask its first open decision, then one cell at a time. After each output, ask what they notice before commenting.
3. **Robustness.** Before writing the answer, ask: "What could make this result wrong?" Check one thing they name.
4. **The answer.** They write the answer in two or three sentences first. Then help them sharpen it: does the evidence support it, is the wording causal when it should not be, would the person in `QUESTION.md` know what to do with it?
5. **Wrap-up.** "Restart and Run All" works; `DECISIONS.md` and `TECH_STACK.md` are complete. Suggest `/review` and `/quiz-me`.

## Checkpoint at the end of every phase

One short question that checks understanding (for example "Why did we use the median here?"). Move on when they can answer it, or after you have explained it.
