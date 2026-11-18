---
name: plan-analysis
description: Plans and then builds, phase by phase, a data analysis that answers the learner's question in the project folder's QUESTION.md, with the learner making every analysis decision. Use when the user runs /plan-analysis, or asks to plan, start or continue the analysis that answers their question.
---

# Plan and build the analysis

Goal: answer the learner's question in `QUESTION.md` with an analysis they can explain and defend. Follow `.cursor/rules/learning-mode.mdc`. `QUESTION.md`, `DATA_NOTES.md` and `analysis.ipynb` live in the project folder, next to `data/`.

If `analysis.ipynb` already has cells, continue from the first unfinished phase of the saved plan.

## Part 1: Plan (Plan mode)

1. Read `QUESTION.md`, `DATA_NOTES.md`, the brief and the data. If `QUESTION.md` is still the empty template, suggest `/frame-question` first.
2. Ask: "How would you answer this? List your steps, rough is fine." Use their steps as the backbone.
3. Ask only the decisions that change the answer, most important first, at most 4. Typical ones:
   - Which data issues from `DATA_NOTES.md` matter here, and what to do about each (drop, fix, keep, flag)
   - The measure (mean or median, counts or shares, per what unit)
   - The comparison, and whether to add a statistical test or interval
   - The chart that answers the question most directly
   If you see an issue that matters and is not in the notes (for example tiny groups), raise it as one of these decisions.
4. Write the plan: **Question**; **Technologies** (each tool and its job here); **Phases** (their steps, each with the decisions still open and "done when"); **Decisions** with reasons; **How we build**: "One phase at a time; stop at each open decision."

## Part 2: Build, one phase at a time

1. Write the planning decisions to `docs/DECISIONS.md` and the stack to `docs/TECH_STACK.md`.
2. For each phase: write and run its cells, give your read of the results in two or three sentences, and stop when the next open decision comes up.
3. Before the conclusion, ask: "What could make this result wrong?" Check what they name.
4. The learner writes the answer to their question in two or three sentences. Help them sharpen it: supported by the evidence, not causal when it should not be, useful to the person in `QUESTION.md`.
5. Make sure "Restart and Run All" works. Suggest `/review`.
