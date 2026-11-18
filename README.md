# Cursor learning starter

Learn to work with an AI coding agent **without handing over your thinking**: one real dataset, one prompt, and you in charge of every decision.

```
DATASET.md          what the data is, where it comes from, what it can and can't tell you
PROJECT_BRIEF.md    the client and the deliverables
PROMPT.md           the prompt that makes the agent guide you (read it, adapt it, paste it)
data/               Airbnb listings in Barcelona
docs/DECISIONS.md   every decision you make, and why
docs/TECH_STACK.md  every tool and library you use, and why
.cursor/rules/      a safety net: always-on instructions that keep you in charge
```

## 1. Setup (once)

1. Install [Cursor](https://cursor.com/download) and sign in. Students: check [cursor.com/students](https://cursor.com/students) for the current student offer.
2. Install the extensions **Python** and **Jupyter** from the Extensions panel (`Cmd+Shift+X` / `Ctrl+Shift+X`). Check the publisher is `ms-python` / `ms-toolsai` before installing.
3. Create your own copy of this repo: click **Use this template** on GitHub, then clone your copy:

   ```bash
   git clone https://github.com/<your-user>/<your-repo>.git
   cd <your-repo>
   cursor .
   ```

4. Create a virtual environment and install the libraries (in Cursor's terminal, `` Ctrl+` ``):

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate        # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   ```

5. Open any `.ipynb`, click **Select Kernel** (top right) and pick `.venv`.

## 2. Run the project

1. Read [`DATASET.md`](DATASET.md) and [`PROJECT_BRIEF.md`](PROJECT_BRIEF.md).
2. Open [`PROMPT.md`](PROMPT.md), adapt it, paste it into a new Agent chat (`Cmd+I` / `Ctrl+I`).
3. The agent works in four stages: **explore, question, plan, build**. It stops at every decision; you choose.
4. Read every cell it writes. If you can't explain one, ask it.

## Data and licence

`data/barcelona_listings.csv`: a random sample (8,000 of 15,236 listings, seed 42, 31 columns) of the [Inside Airbnb](https://insideairbnb.com/get-the-data/) Barcelona snapshot from 2026-09-17. Licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) by Inside Airbnb.
