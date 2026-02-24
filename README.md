# Predicting Cardiovascular Disease Using Machine Learning

**CardioDisease_Prediction** is a machine learning project aimed at predicting cardiovascular disease (CVD) risk using the publicly available cardio_train dataset. This project was completed as part of the **Foundations of Statistical Analysis & Machine Learning CSC1181** course project by **Team 52**.

---

## Project Overview

Cardiovascular disease is one of the leading causes of death worldwide. Early prediction of risk can guide timely interventions. This project focuses on the **cardio_train dataset** containing 70,000 anonymized patient records and builds machine learning models to predict cardiovascular disease status, where:

- `0` indicates healthy  
- `1` indicates the presence of a cardiovascular disease  

The project workflow included:  

1. **Data Preprocessing**  
   - Loaded dataset using pandas and inspected for missing values and duplicates  
   - Removed physiologically unrealistic values for blood pressure, height, and weight  
   - Created new features: `age_years` from age in days and `BMI` from height and weight  
   - Standardized continuous variables (height, weight, blood pressure) using `StandardScaler`  
   - Split data into 80% training and 20% test sets using stratified sampling  

2. **Models Implemented**  
   - **Logistic Regression**: Baseline linear model providing feature influence interpretation  
   - **Random Forest Classifier**: Ensemble model robust to noise and capable of capturing non-linear patterns  
   - **Gradient Boosting (GB)**: Sequential ensemble improving predictive performance iteratively  
   - **Extreme Gradient Boosting (XGBoost)**: Optimized GB with GPU acceleration and hyperparameter tuning for efficiency and accuracy  

3. **Validation and Evaluation**  
   - Applied 5-fold stratified cross-validation on XGBoost to ensure stable performance  
   - Evaluated models using accuracy, F1-score, confusion matrices, and ROC-AUC  
   - Final test set metrics for XGBoost with GPU:  
     - **Accuracy**: 0.7293  
     - **F1 Score**: 0.7140  
     - **Confusion Matrix**:  
       ```
       [[5370 1562]
        [2152 4635]]
       ```  
   - Feature importance ranked top predictors as BMI, systolic and diastolic blood pressure, age, height, and weight  

4. **Insights**  
   - Boosting models outperformed simpler approaches, with XGBoost (using GPU) offering best performance and efficiency  
   - Feature importance aligns with known clinical risk factors, confirming model learned meaningful patterns  
   - The model generalizes well, with consistent cross-validation results (mean CV F1 ≈ 0.721, SD ≈ 0.006)  

---

## Ethical and Legal Considerations

- Dataset is anonymized and contains no personal identifiers  
- Model is intended for academic purposes only and cannot replace clinical judgment  
- Real-world deployment would require GDPR compliance, strong data security, and clear communication of model limitations  

## Team Members & Contributions

| Name | Role | Key Responsibilities | Gmail ID |
|------|------|---------------------|----------|
| Achal Nanjundamurthy | Model Building, Cross-validation, Research | Implemented and trained models, performed cross-validation and hyperparameter tuning, produced final metrics and plots | achalnm02@gmail.com |
| Khushi Bijkal | Pre-processing, Visualization, Reporting | Handled data preprocessing, exploratory data analysis (EDA) visualizations, interpreted results, and finalized the report | khushi.n.bijkal@gmail.com |
| Suman Neupane | Model Building, Error Analysis, Research | Supported model building, performed error and metric analysis, gathered related research papers and references | sumanneupane99@gmail.com |
| Durga Prasad Narsing | Analysis, Reporting | Provided statistical and ethical/legal write-up, helped interpret results and compile the final report | durgaprasadnarsing1728@gmail.com |


