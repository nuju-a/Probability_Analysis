
# Certified Organic Livestock Analysis (2008 vs 2011)

Cleaning, probability, hypothesis testing and subsidy-cost analysis of certified organic livestock across 50 U.S. states, plus 59 certifying bodies. The work is done in Google Sheets from the raw file `certified_organic__livestock_analysis.xlsx`, which is kept untouched in `data/`.

* **Google Sheet (view only, anyone with the link):** [docs.google.com/spreadsheets/d/1KbtXJI5eFk9TWV6-FE9S1XlhsW5MI157ZnsMLZOtvwg/edit?usp=sharing](https://docs.google.com/spreadsheets/d/1KbtXJI5eFk9TWV6-FE9S1XlhsW5MI157ZnsMLZOtvwg/edit?usp=sharing)
* **Export date:** 2026-11-01
* **Full write-up:** analysis/findings.md
* **Cleaning decisions and formulas:** analysis/cleaning_log.md



## Repository structure

text

```text
certified_organic_livestock/
├── README.md             this file
├── data/                 raw workbook (untouched)
├── analysis/
│   ├── cleaning_log.md   every cleaning step, with formulas
│   └── findings.md       results and interpretation for each sheet
└── outputs/              CSV export of each tab, workbook snapshot
```


## Summary

| Question                                                  | Result                                                                                                                   |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| How much certified organic livestock is there?            | 475,829 (2008) and 492,353 (2011), up**3.5%** . Beef cows +66.7%, other cows -21.9%, sheep -20.7%.                 |
| Did the average state total change between 2008 and 2011? | **No evidence of a change**(paired t-test, t = 0.367, p = 0.715; p = 0.698 excluding the 4 no-data states).        |
| Is the data evenly spread?                                | **No.**California, Texas and Wisconsin hold 44.7% of 2011 livestock. Mean state total 9,847, median 2,187.               |
| West vs South, 2011 totals                                | t-test: no significant difference (p = 0.376). A rank-based test gives p = 0.037, so the result depends on the test.     |
| Empirical probabilities (50 states)                       | P(West) = 0.26, P(2011 total > 10,000) = 0.24, P(milk cows 1,000 to 10,000) = 0.26.                                      |
| Subsidy cost                                              | **$7.91 million (2008)**to**$19.02 million (2011)** , up 140.6%. Milk cows are about two-thirds of the cost. |
| Certifying bodies                                         | 59 bodies, 48 active and 11 inactive. Producers certified: 12,744 (2008) and 12,742 (2011).                              |

AI DISCLOSURE: I engaged the help of claude.ai with calculations, figuring out best logics to apply all through this project.