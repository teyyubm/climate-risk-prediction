# Machine Learning for Climate Risk Prediction: Accuracy, Explainability, and Responsible Use

**A Wildfire-Risk Case Study on the Algerian Forest Fires Dataset**

Module: *Interdisciplinary Elective — AI, Power & Responsibility: Governing Intelligent Systems for Sustainability*
University of Europe for Applied Sciences (UE)
Author: Teyyub Malikov · Matriculation No. 20583466

---

## Overview

Wildfires are intensifying under climate change, threatening lives, ecosystems, and
infrastructure. Machine-learning early-warning systems can predict fire risk from
weather data, but to be deployed responsibly they must be **accurate**,
**explainable**, **robust** to noisy sensors, and **fair** across regions. A false
alarm erodes public trust; a missed warning can be fatal.

This project builds and audits wildfire-risk classifiers on the **Algerian Forest
Fires Dataset** across five research questions covering accuracy, explainability,
responsible use, robustness, and cross-region fairness.

## Dataset

**Algerian Forest Fires Dataset** (UCI / Kaggle) — publicly available, real data.

- 244 observations from 2 regions (Bejaia & Sidi-Bel Abbes)
- 10 features: Temperature, RH, Ws, Rain + Fire-Weather Indices (FFMC, DMC, DC, ISI, BUI, FWI)
- Binary target: `fire` / `not fire`

## Research Questions

| RQ | Focus | Question |
|----|-------|----------|
| RQ1 | Accuracy | How accurately can ML models (Logistic Regression, Random Forest, XGBoost) predict wildfire occurrence, and which gives the best accuracy–complexity trade-off? |
| RQ2 | Explainability | Which features most drive predictions, and do SHAP explanations align with fire-weather domain knowledge? |
| RQ3 | Responsible Use | How do false alarms vs missed warnings trade off across decision thresholds for responsible early warning? |
| RQ4 | Robustness | How robust are predictions to noisy / missing sensor data, and which features are most sensitive? |
| RQ5 | Fairness | Does performance differ between regions, and does a model trained on one region generalize to the other? |

## Repository Structure

```
.
├── README.md
├── notebooks/      # executed Jupyter notebooks (one per research question)
├── figures/        # publication-ready figures saved as PDF
└── tables/         # result tables saved as CSV
```

Each notebook is self-contained: it loads the raw dataset, preprocesses it,
runs the analysis for its research question, and saves the figure (PDF) and
table (CSV). Notebooks were executed on Kaggle.

## Methodology / Workflow

1. **Data Collection** — load the Algerian Forest Fires dataset
2. **Preprocessing** — clean, encode the target, scale features
3. **Model Training** — Logistic Regression / Random Forest / XGBoost
4. **Evaluation & Audit** — accuracy, SHAP, threshold analysis, robustness, fairness (RQ1–RQ5)
5. **Insights** — domain-aligned, responsible deployment

## Key Results

| RQ | Result |
|----|--------|
| RQ1 | Random Forest & XGBoost reach Accuracy 0.986, F1 0.988, AUC ≈ 1.00; Logistic Regression 0.918. |
| RQ2 | Top SHAP drivers are FFMC, ISI, FWI — all fire-weather indices, matching domain knowledge. |
| RQ3 | A threshold of ≈ 0.45–0.55 yields 0 missed fires and only 1 false alarm — the responsible operating point. |
| RQ4 | Predictions stay stable under moderate noise (F1 0.988 → 0.94 at 40% noise); only ISI & FFMC are sensitive. |
| RQ5 | Cross-region accuracy 0.975–0.992 — the model generalizes fairly across both regions. |

## How to Reproduce

1. Download the **Algerian Forest Fires Dataset** from Kaggle / UCI.
2. On Kaggle, add the dataset as input to a notebook.
3. Run each notebook in `notebooks/` (Run All). Figures (PDF) and tables (CSV)
   are written to the working directory.

**Requirements:** Python 3, pandas, numpy, scikit-learn, xgboost, shap, matplotlib
(all available by default on Kaggle).

## Tools Used

Analysis and code were developed with the help of AI tools (for research-question
generation, methodology, and initial code), then verified, corrected, and run by the
author. All results are produced from real data.

## Keywords

Climate Risk · Wildfire Prediction · Explainable AI · SHAP · Responsible AI · Fairness · Robustness
