---
name: explore-data
description: Runs an exploratory data analysis (EDA) of any tabular dataset in a notebook, shows the learner what matters, lets them choose what to dig into, and writes data notes in the project folder. Use when the user runs /explore-data, or asks to explore, understand or get to know a dataset or CSV.
---

# Explore a dataset (EDA)

Goal: the learner knows the dataset well enough to choose a good question. You do the mechanics; **they choose what to dig into**. Follow `.cursor/rules/learning-mode.mdc`.

Do not suggest analysis questions here. If the learner mentions one, add it to "Things I'm curious about".

## 1. Overview (you do it, no questions)

1. Find the project folder from the open file or the message (ask only if unclear). Read its brief.
2. Create `eda.ipynb` next to `data/` and write a short overview, a few cells: load the data, shape, column types, missing values per column, a quick look at the main numeric and categorical columns.
3. Run it (or check it in the terminal) and give the learner a summary of 5 to 7 bullets: what one row is, size, the columns that matter, and the data quality issues you see (text that should be numbers, missing values, outliers, odd categories).
4. Write those facts into `DATA_NOTES.md` (Dataset, Columns that matter, Data quality issues). Create the file if it is missing.

## 2. Dig in (the learner chooses)

Ask: "What do you want to dig into?" with 3 or 4 **areas** that the overview made interesting (for example: the distribution of one column, a number broken down by a category, the relationship between two columns, where the missing values are), plus "something else (your idea)". Never offer questions to answer.

For each choice: a few cells, run them, give your read in two or three sentences, add anything worth keeping to "Patterns and surprises". Then offer the next areas. Stop after 3 or 4 digs, or when the learner wants to.

## 3. Close

Ask once: "What are you curious about now?" Add their answers to "Things I'm curious about". Suggest `/frame-question` in a new chat.

Do not clean the data here beyond what is needed to look at it. Cleaning decisions belong to the plan; keep them under "Data quality issues".
