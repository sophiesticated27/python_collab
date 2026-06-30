# 📊 A/B Testing Statistical Significance Calculator (Python)

## Project Goal

Analyze A/B testing results using statistical methods in Python and build a visualization
that highlights key conversion metrics, replacing manual calculator-based significance checks
with an automated, reusable Python pipeline.

---

## Task Description

**Stage 1 — Statistical Significance Calculation**

Calculate statistical significance for four conversion metrics using a Python script in Google Colab:

- `add_payment_info / session`
- `add_shipping_info / session`
- `begin_checkout / session`
- `new_accounts / session`

Significance is calculated dynamically through arrays and loops — not hardcoded per metric — 
so the approach scales to any number of metrics and breakdowns. Results are computed both
in total per test and across multiple breakdowns (by country, device, and test).

**Stage 2 — Visualization in Tableau**

The resulting dataset feeds into a Tableau dashboard built on top of the earlier
*Create Your A/B Testing Tool* project, extended with statistical significance results.

---

## Dataset

Source: A/B testing event-level dataset (same dataset used in the *Create Your A/B Testing Tool* project),
containing session and conversion event data across multiple A/B tests, countries, and devices.

---

## Approach

| Step | Description |
|---|---|
| Data loading | Load raw session/event data into a pandas DataFrame in Google Colab |
| Metric definition | Define conversion metrics as a flexible list rather than hardcoded variables |
| Breakdown loop | Iterate over test, country, and device combinations to calculate significance per slice |
| Statistical test | Apply a two-proportion z-test (or chi-squared test) to compare control vs. variant conversion rates |
| Output | Export a structured results file (CSV) containing all metrics, breakdowns, and p-values for Tableau |

---

## Key Techniques

| Technique | Usage |
|---|---|
| `pandas` | Data manipulation and aggregation |
| `scipy.stats` | Two-proportion z-test / chi-squared test for significance |
| Loops over metric arrays | Avoids hardcoding metrics, scales to any number of conversion events |
| Multi-level breakdowns | Calculates significance by test, country, and device simultaneously |
| CSV export | Produces a Tableau-ready output file |

---

## Output

A structured results file containing, for each breakdown (test / country / device) and each metric:
- conversion rate per variant
- p-value
- statistical significance flag

This file feeds directly into the Tableau dashboard for visualization.

---

## Tools

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=flat&logo=googlecolab&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)
