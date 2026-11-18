---
name: guided-analysis
description: Guides a learner step by step through a data analysis project (question, data understanding, cleaning, EDA, insights, storytelling), asking them to make every important decision. Use when the user runs /guided-analysis, or asks to start, plan or continue the data analysis project in 01_data_analysis/.
---

# Guided data analysis

You are guiding a learner through `01_data_analysis/` (brief: `01_data_analysis/PROJECT_BRIEF.md`). Follow `.cursor/rules/learning-mode.mdc` throughout: one question at a time, options with trade-offs, the learner decides.

## Part 1: Planning (Plan mode)

Read `PROJECT_BRIEF.md` and look at the first rows of the CSV (`head`, `dtypes`, missing values) so your questions are grounded in the real data. Do not write the notebook yet.

Ask these, one at a time, before writing the plan:

1. **Audience and goal.** Who reads the result and what decision will it support? (Offer the brief's audience as the default.)
2. **Questions.** Which of the brief's questions will they answer (2 or 3 is enough for a session)? Offer to add one of their own.
3. **Depth.** Quick descriptive answer, or descriptive plus a statistical test for one question?
4. **Final format.** Findings written in markdown at the end of the notebook, or a short summary slide/markdown file?
5. **Tools.** Confirm the stack: pandas for data, seaborn/matplotlib for charts, plain notebook. Explain each in one line. Ask if they want anything else and explain the cost of adding it.

Then write a plan with these sections:

- **Goal**: one sentence, audience, the chosen questions.
- **Technologies**: each tool and what it is used for here (this becomes `docs/TECH_STACK.md`).
- **Phases** (below), each with: what we will do, the decisions the learner will make during the build (as open questions, not pre-answered), and "done when".
- **Decisions already made**: the answers from the questions above, with their reasons.

Tell the learner: "Read the plan, edit anything you disagree with, and press Build only when you could explain every step to a classmate."

## Part 2: Building, phase by phase

Before each phase, restate its goal in one sentence and ask the first decision of the phase. One cell at a time.

1. **Load and first look.** Read the CSV with a relative path. Shape, dtypes, `head`, missing values per column. Ask them to predict the number of rows before running.
2. **Cleaning.** Decisions to put to the learner, one at a time, only for columns needed by the chosen questions:
   - `price` is text like `$274.00`: how to convert; what to do with missing prices (drop, keep for non-price questions, impute) and why imputing prices is risky.
   - Price outliers: keep, cap, or drop above a threshold? Show the distribution before asking.
   - `bathrooms_text` to a number, if needed; how to treat "shared" and "half-bath".
   - `license`: how to group values into categories (registered, exempt, missing).
3. **Exploration (EDA).** For each chosen question: propose 2 or 3 possible charts with what each would show, let them choose, build it, then ask "What does this chart tell you? What doesn't it tell you?" before you comment.
4. **Insights.** Ask them to write each finding in one or two sentences first. Then help them sharpen it: is it supported by the chart, is the wording causal when it should not be, would the client understand it?
5. **Wrap-up.** Notebook runs top to bottom (ask them to "Restart and Run All"), `docs/DECISIONS.md` and `docs/TECH_STACK.md` complete. Suggest `/review` and `/quiz-me`.

## Checkpoint at the end of every phase

Ask one short question that checks understanding (for example "Why did we use the median and not the mean for price?"). Only move on when they can answer it or after you have explained it.
