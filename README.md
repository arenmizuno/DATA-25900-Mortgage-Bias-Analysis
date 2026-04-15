# DATA 25900 – Machine Learning and Public Policy
## Final Project: Mortgage Bias and Discrimination Analysis

**University of Chicago**  
**Instructor:** Raul Castro Fernandez  
**Term:** Spring 2024  

**Team Members:**  
- Ryan Winston  
- Aren Mizuno  

---

## Overview

This repository contains my final project for *DATA 25900*, a course focused on applying machine learning and statistical methods to public policy and real-world decision-making.

The course emphasized identifying bias, evaluating fairness, and applying quantitative models to analyze disparities in outcomes across demographic groups. Students developed skills in regression modeling, model evaluation, and interpreting results in policy-relevant contexts.

---

## Final Project

**Description:**  
This project evaluates bias and discrimination in home mortgage loan origination and pricing in Illinois from 2018–2022. The goal is to determine whether differences in loan approvals and pricing can be explained by observable factors, or whether disparities persist across racial and ethnic groups.

The analysis uses HMDA mortgage-level data and applies machine learning and statistical modeling techniques to assess fairness in lending practices.

---

### Methodology

- Performed **data preprocessing and cleaning**:
  - Filtered for relevant loan types (home purchases) and outcomes  
  - Removed missing, redundant, and invalid observations  
  - Simplified race and ethnicity categories  
  - Removed outliers using IQR filtering  
  - Created dummy variables and multiple dataset variants to address collinearity  

- Built **loan origination model (classification)**:
  - Logistic Regression with L1 regularization  
  - 80/20 train-test split  
  - Cross-validation to tune regularization parameter  
  - Evaluated using accuracy, precision, recall, F1 score, and ROC-AUC  

- Built **loan pricing model (regression)**:
  - LASSO regression to model rate spreads  
  - Cross-validation for hyperparameter tuning  
  - Evaluated using MAE, MSE, and R²  

---

### Key Findings

- Logistic regression models showed **very strong predictive performance** (F1, precision, recall ≈ 0.98–1) across years  

- Evidence of **changing patterns of bias over time**:
  - Hispanic applicants showed favorable outcomes in 2018–2020, followed by less favorable outcomes in 2021–2022  
  - Black and Asian applicants exhibited shifting approval likelihoods across years  

- In loan pricing:
  - Black applicants consistently faced **higher rate spreads (0–1.3%)**  
  - Hispanic applicants generally faced **higher pricing (up to 2.1%)**, with variation in later years  
  - Asian applicants showed mixed trends over time  

- Key drivers of outcomes included:
  - Debt-to-income ratio  
  - Loan characteristics (LTV, loan amount, costs)  
  - Income and borrower attributes  

---

### Project Deliverables

- `Code/`  
  → Core notebooks for data cleaning, feature engineering, modeling, and coefficient analysis across multiple dataset variants  

  Includes:
  - Data cleaning and preprocessing:  
    `final_clean.ipynb`, `final_clean_rs.ipynb`  
  - Dummy variable creation:  
    `final_dummy.ipynb`, `final_dummy_rs.ipynb`  
  - Class imbalance analysis:  
    `final_classimbalances.ipynb`  
  - Correlation analysis:  
    `final_corrmatrix.ipynb`  
  - Regression models:  
    `final_regression_all.ipynb`, `final_regression_all_rs.ipynb`  
    `final_regression_derived.ipynb`, `final_regression_derived_rs.ipynb`  
    `final_regression_noderived.ipynb`, `final_regression_noderived_rs.ipynb`  
  - Coefficient analysis:  
    `final_coefficients_all.ipynb`, `final_coefficients_all_rs.ipynb`  
    `final_coefficients_derived.ipynb`, `final_coefficients_derived_rs.ipynb`  
    `final_coefficients_noderived.ipynb`, `final_coefficients_noderived_rs.ipynb`  

- `Classification Report/`  
  → Classification reports for loan origination models across 2018–2022 and dataset variants (`all`, `derived`, `noderived`)  

- `ROC curves/`  
  → ROC curve visualizations for each model and year  

- `Confusion Matrix/`  
  → Confusion matrices for each model and year  

- `CSV files/`  
  → Intermediate and final datasets, including:
  - Cleaned datasets (`clean_2018.csv` → `clean_2022.csv`, plus `_rs` versions)  
  - Dummy-variable datasets (`dummy_*.csv`)  
  - Coefficient outputs (`coefficient_df_*.csv`) across all model variants  

- `Final Report.docx`  
  → Main report summarizing methodology, findings, and conclusions  

- `Final Detailed Report.docx`  
  → Extended analysis with additional modeling details and diagnostics  

- `Data Ethics Literature Reviews.docx`  
  → Supporting literature review on fairness and discrimination  

- `Data Ethics Presentation.mp4`  
  → Presentation of results and ethical considerations  

---

## Skills & Concepts Demonstrated

- Supervised learning: classification and regression  
- Regularization: **L1 (Logistic), LASSO**  
- Model evaluation: ROC-AUC, F1, MAE, MSE, R²  
- Cross-validation and hyperparameter tuning  
- Bias and fairness analysis in ML models  
- Handling imbalanced datasets  
- Feature engineering and multicollinearity handling  
- Translating model outputs into policy insights  

---
