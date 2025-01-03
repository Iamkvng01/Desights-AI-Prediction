# FOMC Interest Rate Prediction Challenge

## Overview
This project aims to predict Federal Open Market Committee (FOMC) interest rate adjustments using economic indicators. It builds a multi-class classification model to forecast rate changes during the December 17-18, 2024, FOMC meeting. The predicted rate adjustments include `-0.50%`, `-0.25%`, `0%`, `+0.25%`, and `+0.50%`.

By leveraging economic data and machine learning, the project provides actionable insights for economists, policymakers, and investors.

---

## Methodology

### Data Collection
Nine datasets representing key economic indicators were merged:
- Effective Federal Funds Rate (EFFR)
- Personal Consumption Expenditures (PCE)
- Gross Domestic Product (GDP)
- Unemployment Rate (UNRATE)
- Payroll Employment (PAYEMS)
- Consumer Price Index (CPIAUCSL)
- Retail and Food Services Sales (RSXFS)
- Housing Starts (HOUST)
- Federal Funds Rate (FEDFUNDS)

Missing values were handled via linear interpolation and forward/backward filling, and all features were normalized for model stability.

### Exploratory Data Analysis (EDA)
Key insights from EDA:
- Sharp increases in EFFR align with tightening monetary policies.
- Strong correlation (0.98) between EFFR and FEDFUNDS.
- Seasonal patterns in HOUST data reflect housing market cycles.
- The target variable, `EFFR_Change`, highlighted distinct periods of aggressive rate adjustments.

### Feature Engineering
- **EFFR_Change**: Derived as the difference between consecutive EFFR values.
- **Rate_Adjustment**: Categorized target variable based on `EFFR_Change`.

### Model Selection
The **Random Forest Classifier** was chosen for its robustness, interpretability, and ability to handle imbalanced datasets. Class weighting was applied to address class imbalance without oversampling.

---

## Model Performance
- **Accuracy**: 96%
- **Precision, Recall, F1-score**: ≥ 0.97 for all classes.
- Validated through cross-validation and a confusion matrix showing balanced predictions.

---

## Challenges and Solutions
1. **Class Imbalance**: Addressed using class weighting.
2. **Data Alignment**: Managed through interpolation techniques.
3. **Overfitting**: Resolved via grid search and regularization.
4. **Interpretability**: SHAP values analyzed feature importance to align with domain knowledge.
