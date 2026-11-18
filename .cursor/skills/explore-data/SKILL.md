---
name: explore-data
description: Coaches a learner through exploratory data analysis (EDA) of any tabular dataset in a notebook, letting them choose what to look at and notice things first, and ends with written data notes in the project folder. Use when the user runs /explore-data, or asks to explore, understand or get to know a dataset or CSV.
---

# Explore a dataset (EDA)

Goal: the learner understands the dataset well enough to ask good questions about it. You write small cells; **they decide what to look at** and **they notice first**. Follow `.cursor/rules/learning-mode.mdc`.

Do not bring an analysis question to this step, and do not suggest one. If the learner jumps to a question, add it to "Things I'm curious about" and keep exploring.

## Setup

1. Find the project folder from the open file or the message; ask if unclear. Read its brief (if any) for context, then offer the CSVs in its `data/` folder.
2. Create `eda.ipynb` in the project folder, next to `data/`. Notes go in `DATA_NOTES.md` in the same folder; if it doesn't exist, create it with these sections: Dataset, Columns that matter, Data quality issues (to decide later), Patterns and surprises, Things I'm curious about.
3. First cell: load the file with a relative path. Ask them to guess something the brief does not say (for example, how many columns will load as text).

## The loop

1. **What to look at.** First time, ask openly: "What do you want to know first about this data?" After that, offer 3 options that make sense given what has been seen, plus "something else (your idea)". Typical options:
   - What one row represents (the grain) and whether ids are unique
   - Column types: which columns are text that should be numbers or dates?
   - Missing values: where, how many, whether they look random
   - The distribution of one column they pick
   - A breakdown of a number by a category
   - The relationship between two columns they pick
   - Duplicates, impossible values, outliers
2. **One small cell** for their choice. Say in one sentence what it computes.
3. **"What do you notice?"** in chat, no options. If the answer is vague ("looks fine", "idk"), point at one place without saying what is wrong ("Look at the type of that column and its first value. Is that what you expected?") and ask again. After their second answer, add at most two points, then give the next menu in the same message.
4. **Note it.** Add what they noticed to `DATA_NOTES.md` in their words. If the point was yours, ask them to say it in one line first.
5. Every two or three looks, ask "Anything you're curious about now?" and add the answer to "Things I'm curious about".

After about 5 looks, ask whether they want one more or to wrap up.

Do not clean or transform the data here beyond what is needed to look at it (for example, converting a column temporarily to plot it). Cleaning decisions belong to the plan; record them as "issues to decide later".

## Closing

Check each section of `DATA_NOTES.md` has at least one line in their words (only the 5 to 8 columns they care about). Ask them to pick their 2 or 3 favourite curiosities. Then suggest `/frame-question` in a new chat.
