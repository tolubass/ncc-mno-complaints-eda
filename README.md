# NCC Mobile Network Complaints — Exploratory Analysis

Cleaning, exploration, and visualisation of a 2024 customer complaints dataset from four Nigerian mobile network operators, built as a data skills exercise for a regulatory research role.

## Overview

This project works through a year of consumer complaints filed against MTN, Airtel, Glo, and 9Mobile between January and December 2024. The brief was to clean the data, explore it, and pull out findings that could inform a regulatory briefing on consumer protection — the kind of analysis a telecoms regulator might use to decide where to focus its oversight.

## Repository Structure

- `IPA_CPRI_Data_Skills_Assessment_TolulopeOlowolaju.ipynb` — the full analysis, already run end to end. Every table, chart, and statistical test result is saved in the notebook, so it renders directly on GitHub without needing to be re-executed.
- `charts/` — the six charts exported from the notebook:
  - `00a_univariate_distributions.png` — distributions of age, resolution time, satisfaction score, and monthly volume
  - `01_monthly_trend.png` — monthly complaint volume by provider, with spike months marked
  - `02_category_by_provider.png` — complaint category breakdown across the four providers
  - `03_resolution_dashboard.png` — a four-panel view of resolution performance (FCR rate, resolution time by category, status breakdown, satisfaction scores)
  - `04_geographic_distribution.png` — complaints by geopolitical zone and top states
  - `05_fraud_deepdive.png` — fraud complaints by hour of day and by month
- The raw dataset is not included in this repo (see note below).

## Methodology

The notebook follows a standard pipeline: import and inspect the raw data, standardise inconsistent provider names and remove duplicates, validate ages and dates and handle what doesn't check out, then move into analysis. That covers univariate distributions of the key variables, bivariate relationships (resolution time by category, satisfaction by provider, channel by outcome, and so on), complaint volumes against expected market share, resolution performance by provider and by channel, demographic and geographic patterns, and monthly trends. The last part of the notebook runs formal statistical tests (chi-square, Kruskal-Wallis, a one-proportion z-test) against the descriptive patterns found earlier, so the findings and recommendations rest on more than a visual read of the charts.

## Key Findings

- The raw file had 4,203 records. After removing 117 duplicates, nulling 89 impossible dates, and flagging 32 implausible ages, 4,086 clean records remained.
- MTN accounts for 45.3% of complaints against an assumed 40% market share, but Airtel's gap from its own expected share (+8.9pp) is actually larger than MTN's.
- Channel, not provider, is what drives resolution speed: Call Center resolves 48.7% of complaints within 15 minutes, versus 1–3% for every other channel (chi-square, p<0.001).
- Fraud complaints take the longest to resolve (34.1h median), followed by Device (26.9h) and Billing (25.5h).
- Female complainants make up 37.1% of the dataset against an assumed 50% subscriber base — a statistically significant gap (z-test, p<0.0001), though resolution speed doesn't differ meaningfully by gender.
- Complaint volume spiked in March (424) and May (449), both well above the monthly average of 340 — worth following up on with the providers directly.

## Tools and Libraries

Python, with pandas and numpy for data handling, matplotlib and seaborn for visualisation, and scipy.stats for the statistical tests. Built and run in a standard Jupyter notebook environment.

## How to Run

Clone the repo, place `ncc_complaints_2024.csv` in the root folder, open the notebook, and run all cells. Charts will save automatically to the `charts/` folder.

## Note on Data

The raw dataset isn't included in this repo, as it was supplied as third-party assessment material.
