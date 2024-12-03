# Survival Analysis: Appalachia vs. Non-Appalachia Populations

## Introduction
This dataset includes the following features:  
- **Age**  
- **Year of Diagnosis**  
- **Sex**  
- **Race**  
- **Ethnicity**  
- **Primary Cancer Site**  
- **Tumor Grade**  
- **Summary Stage**  
- **Marital Status**  
- **Appalachia (1: Appalachia, 0: Non-Appalachia)**  

I performed a survival analysis to observe the effect of living near Appalachia on survival outcomes.

---

## Working with Data
1. **Preprocessing**:
   - Standardized and scaled the data for both sets: Appalachia (data_A) and Non-Appalachia (data_NA).  
   - Split the data into a **70% training**, **20% testing**, and **10% validation** split.

2. **Model Building**:
   - Built three logistic regression models with different solvers: `newton-cg`, `liblinear`, and `lbfgs`.

---

## Machine Learning Models and Hyperparameter Tuning

### Goal
To predict the **Survival Recode** for individuals using:
- **Logistic Regression**  
- **XGBoost** (both default and optimized versions)

### Findings
- **Logistic Regression**:
  - Performs well for linear relationships between features.
- **XGBoost**:
  - Outperformed logistic regression by handling non-linear relationships.
  - Produced a higher number of true positives and true negatives while reducing false predictions.

### Hyperparameter Optimization (XGBoost)
After tuning, the best-performing XGBoost model had the following configuration:
- `max_depth = 5`: Limits tree depth to prevent overfitting.  
- `learning_rate = 0.1`: Determines the weight of each tree.  
- `n_estimators = 100`: Specifies the number of trees in the model.  
- `subsample = 0.8`: Reduces overfitting by using 80% of training samples for growing each tree.  
- `gamma = 10.0`: Controls node splitting to reduce overfitting.  
- `colsample_bytree = 0.8`: Introduces diversity of features in trees for reducing overfitting.  
- `reg_alpha = 10.0`: Adds a penalty to encourage accuracy.  

### Results
- XGBoost showed a **10% increase in accuracy** compared to logistic regression.
- A bias of **0.69** was identified using the **Disparate Impact Ratio** between Appalachia and Non-Appalachia datasets.

### Performance Metric: AUROC Score
The XGBoost model demonstrated superior performance, achieving a higher **AUROC (Area Under Receiver Operating Characteristic) score** compared to logistic regression models.

---

## Conclusion
The analysis revealed that the XGBoost algorithm, especially with hyperparameter tuning, was best suited for this dataset due to its ability to handle non-linear relationships and improve accuracy. The insights also highlighted the disparities between populations near Appalachia and those outside it, further emphasizing the importance of tailored interventions for improved survival outcomes.
