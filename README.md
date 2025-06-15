# 🏥 Tobacco Use and Mortality Prediction Project

This project predicts tobacco-related deaths in the UK using historical health and economic data, including smoking rates, affordability indices, and prescription usage.

---

## 📊 Dataset Overview

We used five datasets:

1. **admissions.csv** – Hospital admissions by year and diagnosis type  
2. **fatalities.csv** – Mortality data related to tobacco  
3. **metrics.csv** – Economic and affordability indices  
4. **prescriptions.csv** – Count of pharmacotherapy prescriptions  
5. **smokers.csv** – Smoking rate by year and gender

---

## 🔧 Steps Performed

### ✅ Step 1: Import Libraries  
Used essential libraries like `pandas`, `numpy`, `matplotlib`, `sklearn`, etc.

### ✅ Step 2: Load Data  
Loaded all five datasets and printed summaries.

### ✅ Step 3: Data Preprocessing  
- Converted year columns to numeric
- Cleaned column names
- Extracted average smoking rate
- Merged datasets on `Year`
- Dropped rows with missing data

### ✅ Step 4: Exploratory Data Analysis  
- Correlation heatmap was plotted to visualize dependencies between features and the target (`Total_Deaths`).

### ✅ Step 5 & 6: Model Training & Evaluation  
- Models Used:  
  - `LinearRegression`  
  - `RandomForestRegressor`
- Metrics Evaluated:  
  - R² Score  
  - RMSE (Root Mean Squared Error)

### ✅ Step 7: Model Interpretation  
- Feature importances were extracted from the Random Forest model.

---

## 🤖 Model Deployment (Step 8–10)

We deployed the trained `RandomForestRegressor` using a **Flask API**:

### API Details:

- **Endpoint:** `/predict`
- **Method:** POST
- **Request JSON format:**
```json
{
  "Avg_Smoking_Rate": 18.5,
  "Tobacco Price Index": 112.3,
  "Retail Prices Index": 107.9,
  "Tobacco Price Index Relative to Retail Price Index": 1.04,
  "Real Households' Disposable Income": 16000,
  "Affordability of Tobacco Index": 96.5,
  "Household Expenditure on Tobacco": 5200,
  "Household Expenditure Total": 40000,
  "Expenditure on Tobacco as a Percentage of Expenditure": 13.0,
  "All Pharmacotherapy Prescriptions": 780000
}
