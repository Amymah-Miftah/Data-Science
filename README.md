# Online Retail Analytics & Machine Learning Project

## Project Overview
This project analyzes a large-scale **online retail transaction dataset** to understand **customer behavior, revenue drivers, return patterns, and bulk purchasing behavior**, and to prepare the data for **machine learning models** such as churn prediction and revenue forecasting.

---

## Objectives
- Clean and preprocess transactional retail data
- Analyze revenue, returns, and cancellations
- Study customer, product, and country-level patterns
- Investigate seasonality and bulk purchasing behavior
- Prepare data for machine learning models

---

## Dataset Summary
- **Transactions:** 518,596  
- **Customers:** 9,618  
- **Countries:** 40  
- **Time period:** 2009–2011  

---

## Data Cleaning & Preprocessing
- Removed **6,865 duplicate rows**
- Imputed missing **Customer IDs (~20.5%)** using invoice-based grouping
- Filled missing product descriptions with `"Unknown"`
- Flagged invalid and return transactions instead of removing them

---

## Feature Engineering
- `Revenue = Quantity × Price`
- `IsReturn` (Quantity < 0)
- `IsCancelled` (Invoice starts with `C`)
- `Revenue_abs`
- Time features: `Year`, `Month`
- Bulk purchase indicator: `IsBulk`

---

## Revenue & Returns
- **Total revenue:** £9.51M
- **Revenue lost to returns:** £629,808
- **Return impact:** 6.63% of total revenue
- **Returned transactions:** 2.37%

---

## Bulk Purchase Analysis
- **Median quantity:** 3 units
- **Bulk threshold:** > 6 units
- **Bulk transactions:** 31.45%
- **Avg revenue (bulk):** £40.86
- **Avg revenue (normal):** £8.00
- **Bulk returns:** 0%

---

## Country-Level Insights
- **United Kingdom:** ~86% of total revenue
- Strong revenue concentration across a small number of countries

---

## Customer Insights
- **13.86% of customers generate ~80% of revenue**
- Top customers generate £75k+ each

---

## Seasonality
- **Peak month:** November
- Strong Q4 sales pattern
- Returns remain stable across months

---

## Machine Learning Readiness

### Churn Prediction
- Binary classification (churn after 180 days inactivity)
- Features: RFM + return behavior
- Metrics: Recall, F1-score, ROC-AUC

### Revenue Forecasting
- Monthly aggregation
- Lag & rolling features
- Limited monthly history → weekly forecasting recommended

---

## Key Takeaways
- Revenue is highly concentrated
- Bulk buyers are high-value & low-risk
- Returns cause disproportionate revenue loss
- Dataset is suitable for churn modeling

---

## Future Work
- Weekly revenue forecasting
- Customer segmentation
- Explainable ML (SHAP)
- Model deployment

---

## Tools
- Python, Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter / Google Colab
