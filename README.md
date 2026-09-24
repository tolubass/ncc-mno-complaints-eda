# ncc-mno-complaints-eda

Exploratory data analysis of 2024 mobile network operator (MNO) customer complaints data for Nigeria — data cleaning, resolution-time analysis, demographic/geographic patterns, and visualisations for regulatory reporting. Built with Python (pandas, numpy, scipy, matplotlib, seaborn).

## Contents

- `IPA_CPRI_Data_Skills_Assessment_TolulopeOlowolaju.ipynb` — the full notebook, already run end to end with all output included, so it's viewable directly on GitHub without needing to execute anything.
- `charts/` — the chart images exported from the notebook.

## What's covered

- Cleaning: deduplication, provider name standardisation, invalid age/date handling, missing-data checks
- Complaint volumes by provider vs. expected market share
- First-contact resolution rate by provider and by channel
- Resolution time by complaint category
- Gender and geographic patterns
- Monthly volume trends and a fraud deep-dive
- Chi-square, Kruskal-Wallis, and z-tests behind the descriptive findings

## Note on the dataset

The underlying complaints dataset isn't included here, since it was supplied as part of a third-party assessment. The notebook's saved outputs show the full analysis and results.
