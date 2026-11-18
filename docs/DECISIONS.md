# Decision log

One row per decision. The agent proposes the options; **you** choose and write (or approve) the reason. A reviewer should be able to read this table and understand why your project looks the way it does.

| # | Project | Phase | Question | Options considered | Decision | Why |
|---|---------|-------|----------|--------------------|----------|-----|
| 1 | example | Data understanding | What do we do with listings that have no price? | Drop them / impute the median / keep them for the non-price questions | Drop them for price analysis only | Imputing would invent prices; the other columns are still useful |
