# Seasonal Agriculture Performance Analysis



**VOIS AICTE Batch 1 (2026–2027) — Major Project | Data Analytics**

## Problem Statement

Agricultural activities are influenced by seasonal variations in environmental conditions, farming practices, resource availability, and market conditions. Raw agricultural data does not clearly explain how performance changes across seasons or what patterns emerge. This project analyzes a seasonal agriculture dataset to uncover meaningful patterns, trends, relationships, and variations in agricultural performance across the Kharif, Rabi, and Zaid seasons.

## Why This Matters

Understanding seasonal performance patterns helps stakeholders:

* Compare agricultural outcomes across periods
* Identify resource usage inefficiencies (e.g. water, irrigation method)
* Support evidence-based, season-specific agricultural planning
* Flag regional or crop-level exceptions to general seasonal trends

## Dataset

* **Source:** `seasonal\_agriculture\_performance\_dataset.csv`
* **Size:** 4,000 records × 28 columns
* **Coverage:** 8 Indian states, multiple crops, 3 seasons (Kharif, Rabi, Zaid)
* **Key fields:** environmental conditions (rainfall, temperature, humidity, soil health), farming inputs (fertilizer, irrigation, pesticide), and outcomes (yield, production, revenue, profit, water efficiency)

## Approach

1. **Data Cleaning** — Median imputation for missing values in `Rainfall\_mm`, `Soil\_Moisture\_pct`, and `Yield\_Tonnes\_Ha` (120 missing values total across 4,000 rows).
2. **Exploratory Data Analysis**

   * Seasonal comparison of yield and profit
   * Water usage by season and irrigation method
   * Correlation heatmap across all numeric features
3. **Statistical Testing** — One-way ANOVA to check whether yield and profit differences across seasons are statistically significant.
4. **Regional \& Crop-Level Breakdown** — State × Season and Crop × Season comparisons to check whether seasonal patterns hold consistently across regions and crop types.
5. **Predictive Modeling** — Random Forest Regressor to predict `Yield\_Tonnes\_Ha` from environmental and farming inputs, with feature importance analysis.

## Key Findings

* **Yield differences across seasons are not statistically significant** (ANOVA p = 0.214), but **profit differences are highly significant** (ANOVA p < 0.001) — suggesting seasonal profitability is driven more by cost/price dynamics than by raw productivity.
* **Regional patterns are not uniform**: most states peak in Kharif, but Punjab peaks in Rabi (8.61 t/ha) — a clear exception to the general trend.
* **Sugarcane yields dwarf all other crops** (38–53 t/ha vs. 1–3 t/ha for others), which also explains why it dominates the yield-prediction model's feature importance.
* **Flood irrigation consumes the most water** across all seasons, while rainfed methods are most water-efficient but likely yield-constrained.
* The Random Forest model achieved **R² = 0.9623**, **RMSE = 2.70**, **MAE = 0.77** in predicting crop yield.

## Recommendations

* Season-specific crop planning should account for state-level variation rather than a single national seasonal pattern.
* Investigate cost structures in Rabi and Zaid seasons to close the profit gap, since yield alone isn't the driver.
* Encourage adoption of drip/sprinkler irrigation over flood irrigation in water-stressed states.

## Tech Stack

* **Language:** Python 3
* **Libraries:** pandas, numpy, matplotlib, seaborn, scipy, scikit-learn
* **Model:** Random Forest Regressor (scikit-learn)
* **Environment:** Jupyter Notebook

## Repository Structure


├── seasonal\_agriculture\_performance\_dataset.csv   # Raw dataset
├── Seasonal\_Agriculture\_Data\_Analysis.ipynb       # Full analysis notebook
├── VOIS\_Major\_Project\_PPT\_Submission.pptx         # Project presentation
└── README.md                                      # Project overview (this file)


## How to Run


pip install pandas numpy matplotlib seaborn scipy scikit-learn
jupyter notebook Seasonal\_Agriculture\_Data\_Analysis.ipynb


## Author

Boora Prabhas Bhanu.

