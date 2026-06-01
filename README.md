# Predicting Cardiovascular Disease Using Machine Learning

**CardioDisease_Prediction** is a machine learning project aimed at predicting cardiovascular disease (CVD) risk using the publicly available cardio_train dataset. This project was completed as part of the **Foundations of Statistical Analysis and Machine Learning CSC1181** course project by **Team 52**.

---

## Project Overview

Cardiovascular disease is one of the leading causes of death worldwide. Early prediction of risk can guide timely interventions. This project uses the **cardio_train dataset** containing 70,000 anonymized patient records to build and compare machine learning models that predict cardiovascular disease status.

- `0` indicates healthy
- `1` indicates the presence of cardiovascular disease

---

## Project Structure

```text
CardioRisk_ML/
├── Dataset/
│   └── cardio_train.csv
├── outputs/
│   ├── eda_distributions.png
│   ├── feature_importance.png
│   ├── correlation_heatmap.png
│   ├── roc_curve.png
│   └── model_comparison.png
├── Predicting Cardiovascular Disease Using Machine Learning Techniques.ipynb
├── requirements.txt
└── README.md
```

---

## Workflow

### 1. Data Preprocessing

- Loaded dataset using pandas and inspected for missing values
- Removed physiologically unrealistic values for blood pressure, height, and weight
- Created new features: `age_years` from age in days and `BMI` from height and weight
- Split data into 80% training and 20% test sets using stratified sampling

### 2. Models Implemented

- **Logistic Regression** - baseline linear model
- **Random Forest** - ensemble model robust to noise and non-linear patterns
- **Gradient Boosting** - sequential ensemble, strong performance on tabular data
- **XGBoost (GPU)** - tuned with RandomizedSearchCV, trained on RTX 3050 with `device='cuda'`

### 3. Evaluation

- 5-fold stratified cross-validation on the tuned XGBoost model
- Metrics: accuracy, F1-score, confusion matrix, ROC-AUC

Final XGBoost (GPU) results on held-out test set:

- **Accuracy**: 0.7293
- **F1 Score**: 0.7140
- **ROC-AUC**: 0.795
- **Cross-validation F1**: 0.721 (std: 0.006)

### 4. Key Findings

- Top predictors: BMI, systolic BP, age, height, weight - all established clinical risk factors
- Boosting models outperformed the linear baseline
- Lifestyle features (smoking, alcohol) had the lowest predictive weight, likely due to low prevalence in the dataset

---

## Setup

```bash
pip install -r requirements.txt
```

Then open and run the notebook top to bottom. The dataset should be placed at `Dataset/cardio_train.csv`. Output plots are saved to the `outputs/` folder automatically.

---

## Ethical Considerations

- Dataset is anonymized with no personal identifiers
- Model is intended for academic purposes only and cannot replace clinical judgment
- Real-world deployment would require regulatory compliance and clear communication of model limitations

---

## Team Members

| Name | Role | Key Responsibilities |
| ---- | ---- | -------------------- |
| Achal Nanjundamurthy | Model Building, Cross-validation, Research | Implemented and trained models, performed cross-validation and hyperparameter tuning, produced final metrics and plots |
| Khushi Bijkal | Preprocessing, Visualization, Reporting | Handled data preprocessing, EDA visualizations, interpreted results, finalized the report |
| Suman Neupane | Model Building, Error Analysis, Research | Supported model building, performed error and metric analysis, gathered related research |
| Durga Prasad Narsing | Analysis, Reporting | Statistical and ethical write-up, helped interpret results and compile the final report |
