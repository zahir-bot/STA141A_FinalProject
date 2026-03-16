# County-Level Wildfire Risk Forecasting Under Asymmetric Error Costs: Logistic Regression vs. XGBoost
**Author:** Zahir Sabbah  
**Date:** March 16, 2026

## View Report
**[Click here to view the report](https://htmlpreview.github.io/?https://github.com/zahir-bot/STA141A_FinalProject/blob/main/Wildfire_project_final.html)**

---

## Project Overview
This project develops a binary classification model to predict the monthly occurrence of notable wildfires (≥300 acres) across U.S. counties from 1992–2015. Using 1.88 million wildfire records aggregated to the county-month level, it engineers temporal, spatial, and lagged features and compares logistic regression to an XGBoost classifier. The central argument is that recall — not AUC — is the appropriate primary metric for hazard prediction tasks where false negatives and false positives carry asymmetric costs. XGBoost achieves 64.1% recall versus logistic regression's 8.4% through deliberate imbalance correction, while three NOAA nClimDiv climate variables (PDSI, temperature, precipitation) are integrated as external features with a bootstrapped AUC improvement of +0.0076 [95% CI: +0.0011, +0.0146].

## Repository Contents
* Wildfire_project_final.Rmd — source R Markdown script
* Wildfire_project_final.html — final knitted report (self-contained, open in any browser)
* wildfires_sample_100k.csv.zip — wildfire dataset, zipped for GitHub file size limits
* climdiv-pdsidv.txt — NOAA nClimDiv Palmer Drought Severity Index (1895–2026)
* climdiv-tmpc.txt — NOAA nClimDiv mean monthly temperature (1895–2026)
* climdiv-pcpn.txt — NOAA nClimDiv monthly precipitation (1895–2026)

## Instructions for Reproducibility
To reproduce the findings in this report:
1. Extract wildfires_sample_100k.csv.zip into the project folder.
2. Ensure all three climdiv-*.txt files are in the same folder as the .Rmd — the code auto-detects them by filename prefix. If absent, the model runs without climate features.
3. Open wildfire_project.Rmd in RStudio.
4. Knit to HTML. Runtime is approximately 3-5 minutes due to XGBoost training and 1,000-resample bootstrap.
