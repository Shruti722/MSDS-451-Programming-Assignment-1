# MSDS‑451 – Programming Assignment 1: Predicting Stock Returns (AAPL)

## 📈 Overview

This project implements a financial machine learning pipeline to predict the **direction of next‑day returns (up/down)** for a publicly traded asset using historical price and volume data.

While the jump‑start example focused on WTI crude oil, this project focuses on **Apple Inc. (AAPL)** and applies a similar pipeline for feature engineering, model selection, and evaluation. The objective is to test whether simple lag‑based features can capture useful signal in predicting daily market movements.

---

## ⚙️ Project Structure
```
├── AAPL_data.csv # Raw data from Yahoo Finance
├── AAPL_features_target.csv # Engineered features and binary target
├── aic_subsets_results.csv # Feature subset selection results (AIC)
├── confusion_matrix.png # Final confusion matrix plot
├── roc_curve.png # Final ROC curve plot (AUC)
├── xgb_pipeline.joblib # Trained XGBoost pipeline (joblib)
├── run_summary.csv # Summary of model + metrics
├── 451_pa1_shruti_aapl.ipynb # Python notebook/script (full pipeline)
├── report.pdf # Research‑style writeup
└── README.md # This file
```
---

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/msds451-pa1-aapl.git
cd msds451-pa1-aapl
2. Install Dependencies
Use a Python 3.8+ environment and install required packages:

pip install -r requirements.txt
Or install manually:
pip install pandas numpy yfinance xgboost scikit-learn statsmodels matplotlib joblib
3. Run the Pipeline
To download data, create features, perform model selection and evaluation:
python 451_pa1_shruti_aapl.py
This script will:

Download AAPL data

Generate 15 financial features

Select the best feature subset using AIC

Train XGBoost with time‑series cross‑validation

Evaluate the model and export outputs

Outputs
File	Description
aic_subsets_results.csv	AIC scores for all feature subsets
roc_curve.png	ROC curve plot with final model AUC
confusion_matrix.png	Confusion matrix from holdout test set
xgb_pipeline.joblib	Saved trained model for reuse
run_summary.csv	Summary of model settings and results

Report
A technical PDF report (report.pdf) is included and follows the structure of the reference 451_pa1_technical_report_v001.pdf. It explains:

Problem definition

Feature design

Subset selection

Model training + evaluation

Interpretation of results

Final AUC: 0.512 — indicates that predicting daily AAPL return direction using simple lag‑based features is difficult due to limited signal.

