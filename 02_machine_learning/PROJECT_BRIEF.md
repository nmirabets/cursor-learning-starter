# Project brief: predicting customer churn

## The client

A telecom company's retention team. Every month some customers cancel ("churn"). The team can call a limited number of customers each month and offer them a discount. They want a model that tells them **whom to call**, and they want to understand **why** those customers are at risk.

## How you will work

1. **Explore** (`/explore-data`): `eda.ipynb` and `DATA_NOTES.md`.
2. **Frame** (`/frame-question`): what exactly you predict, when, and what the team does with it, in `QUESTION.md`.
3. **Plan and build**: your own prompt (`prompts/my-ml-prompt.md`) in Plan mode. `/guided-ml` is the fallback if your prompt doesn't work.

## What you decide

This is your project. The agent will guide you, but these decisions are yours and must be in `docs/DECISIONS.md`:

- How to frame the problem, and what "a good model" means for a team that can only make a limited number of calls.
- Which metric(s) you optimise and report, and why.
- How you split the data and avoid leakage.
- What your baseline is.
- Which features you use, drop or create.
- Which models you compare, and which one you would ship.
- How you explain the result to a non-technical team.

## The data

`data/telco_churn.csv`: 7,043 customers, one row each (IBM sample dataset, Apache 2.0).

| Column | Meaning |
|--------|---------|
| `customerID` | Customer id |
| `gender`, `SeniorCitizen`, `Partner`, `Dependents` | Demographics |
| `tenure` | Months as a customer |
| `PhoneService`, `MultipleLines` | Phone services |
| `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies` | Internet services |
| `Contract` | Month-to-month, one year, two year |
| `PaperlessBilling`, `PaymentMethod` | Billing |
| `MonthlyCharges`, `TotalCharges` | Money |
| `Churn` | Did the customer leave? `Yes` / `No` |

## Deliverables

1. `eda.ipynb`, `DATA_NOTES.md` and `QUESTION.md` in this folder.
2. `prompts/my-ml-prompt.md`: the prompt you wrote to drive the agent.
3. The plan the agent produced, saved to the workspace (`.cursor/plans/`).
4. `model.ipynb`: runs top to bottom.
5. `docs/DECISIONS.md` and `docs/TECH_STACK.md`, updated.
6. `REFLECTION.md`: half a page. Which decisions did you make? Where was the agent wrong or too confident, and how did you notice?
