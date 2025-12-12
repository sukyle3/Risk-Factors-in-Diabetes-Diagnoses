# Clinical Risk Prediction: Diabetes Risk Modeling (BRFSS 2015)

## Overview
Diabetes and pre-diabetes affect tens of millions of adults in the United States. Early identification of high-risk individuals is critical for prevention and clinical intervention. This project models diabetes risk using **health, lifestyle, medical care, and demographic factors** from the CDC’s BRFSS 2015 survey, with the goal of identifying key predictors and evaluating model performance.

---

## Methods

### 1) Data Preparation & Variable Engineering
- Analyzed 21 predictors across comorbidities, health metrics, lifestyle, medical care, and demographics
- Recoded skewed variables (BMI, mental health, physical health) into ordinal categories for interpretability and stability
- Verified transformations using before/after distribution checks

### 2) Exploratory Data Analysis
- Used **stacked bar plots** and **boxplots** to examine relationships with diabetes status
- Ran **Chi-square tests** and **univariate logistic regressions** for initial screening
- Strong marginal signals appeared for cardiovascular comorbidities, BMI, general health, and mobility limitation

### 3) Model Building & Selection
- Fit multivariable **logistic regression** with stepwise selection (α = 0.05)
- Compared models across coding strategies (raw vs recoded predictors)
- Checked fit and influence using standard diagnostic outputs (ROC, GOF, leverage/influence)

---

## Results
- **Final model predictors:** HighBP, HighChol, BMI category, GenHlth, DiffWalk, CholCheck, Age  
- **Model performance:** ROC AUC ≈ **0.83** (see ROC figure)
- **Interpretability:** Odds ratios and directions aligned with established clinical understanding

<p align="center">
  <img width="444" alt="ROC curve" src="https://github.com/user-attachments/assets/6e15f9c5-44ba-453e-a538-57eb48abf7ac" />
</p>

<p align="center">
  <img width="838" alt="Odds ratio estimates" src="https://github.com/user-attachments/assets/c0c076a2-3f36-42cd-a160-1f1463c35302" />
</p>


---

## Key Findings
- Diabetes risk is strongly associated with **cardiovascular comorbidities**, **self-reported health**, and **BMI**
- Recoding decisions can materially change inference, emphasizing the value of careful feature engineering
- The final model showed strong discrimination and stable behavior under diagnostics


---

## Languages / Tools
- **Language:** SAS  
- **Environment:** SAS Studio  
- **Methods:** Logistic regression, stepwise selection, EDA, model diagnostics
