# How to write a prompt for an agent that guides you

An agent does what the prompt makes easy. If the prompt says "build", it builds, and you end up with a notebook you cannot defend. If the prompt says "guide me, ask me, let me decide", you end up understanding your project.

## A weak prompt

```text
Build a churn prediction model with the telco data and tell me the best model.
```

What goes wrong:

| Problem | Consequence |
|---------|-------------|
| No context about you | It explains at the wrong level, or not at all |
| No process | It writes the whole notebook in one go |
| "Tell me the best model" | It makes every decision for you: metric, features, threshold |
| No definition of done | It stops when the code runs, not when you understand it |

## A strong prompt: the six parts

```text
## Role
Act as my senior data science mentor. I make the decisions; you guide me,
explain the options and write small pieces of code I can review.

## Context
I finished a data analytics bootcamp: pandas, EDA, statistics, and the basics of
scikit-learn. Project brief: @02_machine_learning/PROJECT_BRIEF.md
Data: @02_machine_learning/data/telco_churn.csv

## Goal
A churn model the retention team can use to decide whom to call each month,
and an explanation of it that a non-technical person understands.

## Process
- Before writing any code, inspect the data and ask me questions to build a plan
  together: framing, metric, validation, baseline, models, tools.
- Ask ONE question at a time. Give 2-3 options with one-line trade-offs.
  You may suggest one, but I choose.
- Then write the plan with phases, the technologies we use and why, and the
  decisions still open in each phase.
- During the build: one cell at a time (max ~15 lines), explain it before
  writing it, I run it and tell you the output.
- Every few cells, ask me to predict the output first.
- Log every decision in @docs/DECISIONS.md and every tool in @docs/TECH_STACK.md.

## Constraints
- Do not add libraries without asking me.
- Do not skip phases or write several cells at once, even if I get impatient.
- If I make a mistake, ask me questions that help me find it before fixing it.

## Done when
- The notebook runs top to bottom.
- DECISIONS.md explains every choice in my own words.
- I can explain to a classmate why we chose our metric and our threshold.
```

## Why each part matters

| Part | What it controls | Ask yourself |
|------|------------------|--------------|
| **Role** | Who the agent is and who is in charge | Did I say that *I* decide? |
| **Context** | What it knows about me and the project. Use `@` to attach files instead of pasting them | Would a new teammate understand the task from this alone? |
| **Goal** | The outcome, for whom, and why | Is it an outcome (a decision someone makes) and not just "a model"? |
| **Process** | How we work together: questions, plan, small steps | Did I describe the conversation I want, step by step? |
| **Constraints** | What it must never do | What has gone wrong before that I want to prevent? |
| **Done when** | When we stop | Is it about my understanding, not only about the code running? |

## Tips

- Run the prompt in **Plan mode** (`Shift+Tab`). The agent researches, asks, and writes a plan you can edit before any code exists.
- Attach files with `@` instead of describing them.
- If the result goes wrong, do not patch it with ten follow-ups. Improve the prompt or the plan and start a new chat.
- A prompt you reuse often belongs in a file: as a command (`.cursor/commands/`), a skill (`.cursor/skills/`), or a rule (`.cursor/rules/`). That is exactly how this repo is built.
