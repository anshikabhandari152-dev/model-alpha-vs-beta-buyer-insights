# Model Alpha vs Model Beta: Why Buyers Choose What They Choose

A GenAI in Data Analytics case study on a survey of 251 commercial-vehicle owners across four Indian metro cities (Jan to Feb 2024). The project finds out why the same manufacturer sells two models in opposite proportions across regions.

> **Note:** Company, brand, product and model names have been anonymised. The survey data is confidential and **not included** in this repository.

---

## Business Problem

**Apex Motors** sells two models in the medium delivery vehicle segment: **Model Alpha** and **Model Beta**. Their sales mix differs sharply by region:

| Region | Model Alpha share of Apex owners |
| North | 25% (15 of 60) |
| South | 63% (64 of 101) |

The analysis answers three questions:

1. **North:** why do buyers choose Model Beta over Model Alpha?
2. **South:** why do buyers choose Model Alpha over Model Beta?
3. **Competition:** why do buyers choose Competitor 1 or Competitor 2 over Apex?
---

## Data

| Item | Detail |
| Source | Customer survey, Jan to Feb 2024 |
| Respondents | 251 vehicle owners (161 Apex, 90 Competitor 1/2) |
| Regions | North (2 cities), South (2 cities) |
| Raw shape | 251 rows × 116 columns, 2 header rows |
| Availability | Confidential, not shared. Available only under permission |
---
## Method

**Cleaning (8 business rules, every step logged, no rows dropped)**
- 2,221 placeholder values (such as "QNA") converted to blanks
- 764 text cells trimmed of extra spaces and line breaks
- 21 Hinglish answers translated to English
- 27 text answers moved out of rating columns
- 53 owners reporting ₹0 maintenance kept and flagged

**Validation:** 43 checkpoints against the brief (row counts, region and brand splits, logical checks such as laden weight ≤ unladen weight). All pass.

**Analysis**
- 9 KPIs (share, repeat intent, consideration, income, payback and others)
- Chi-square test with Cramér's V for region × model
- Welch t-test for payload, revenue and break-even
- Mann-Whitney test for 1 to 5 ratings
- Fisher exact test for small-sample counts
---
## Key Findings
- **Region, not the vehicle, explains the split.** Chi-square = 22.17, p < 0.001, Cramér's V = 0.37.
- **North buys Model Beta for payload.** Payload is the top buying factor for 27% of North owners, against 3% in the South.
- **Model Alpha misses the North shortlist.** Only 3 of 45 Model Beta owners considered it, and 8 were pitched it.
- **South buys Model Alpha for brand and cabin.** 86% of South buyers are first-time buyers.
- **Service is Model Alpha's weak spot.** 46% of its owners list service issues, against 22% for Model Beta.
- **Competitors win on parts, resale and finance.** Only 4 of 90 competitor owners plan to buy Apex next.

**Recommendation:** pitch Model Alpha in the North and fix its spare-parts supply. Fix Model Alpha service in the South.
---
## Tech Stack

Python · pandas · NumPy · SciPy · matplotlib / seaborn · Jupyter · GenAI tools for translation and analysis support

---
## Limitations

- Model Alpha owners in the North are few (n = 15), so those results are read as counts, not tested effects.
- 64 of 79 Model Alpha ratings come from the South, so some rating gaps reflect region rather than model.
- Mileage mixes km/l (diesel) and km/kg (CNG), so it is not compared across fuels.
- Vehicle prices are not in the data, so payback is compared without purchase cost.




## Disclaimer

This is an academic case study. All company, brand and product names are fictional placeholders. No confidential data is published here.
