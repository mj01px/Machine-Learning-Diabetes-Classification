# Pima Indians Diabetes Prediction

A Machine Learning project developed to analyze and predict diabetes cases among Pima Indian women, using clinical and biometric data from a public dataset.

---

## Overview

This project explores how different **cross-validation strategies** and **model choices** affect predictive performance in medical datasets — focusing mainly on **Support Vector Machine (SVM)** and **Random Forest** classifiers.

The main goal is to understand how model validation, feature importance, and feature engineering can influence accuracy, recall, and model generalization in health-related prediction tasks.

---

## Objectives

- Compare **KFold** vs **StratifiedKFold** cross-validation strategies  
- Evaluate model performance on key metrics (Accuracy, F1, Recall, ROC-AUC)  
- Identify **most relevant clinical variables** for diabetes diagnosis  
- Build a **reproducible pipeline** for future experiments  

---

## Dataset

**Source:** [Pima Indians Diabetes Database (Kaggle)](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

**Features:**
- Pregnancies  
- Glucose  
- BloodPressure  
- SkinThickness  
- Insulin  
- BMI  
- DiabetesPedigreeFunction  
- Age  
- Outcome → 1 = Diabetic, 0 = Non-Diabetic  

---

## Technologies

- Python 3.10+  
- pandas, numpy  
- scikit-learn  
- matplotlib, seaborn  
- jupyter notebook  

---

## Methodology

1. **Data Preprocessing**
   - Missing value imputation (median/mode)
   - Standardization with `StandardScaler`
   - Label encoding for categorical values  

2. **Modeling & Validation**
   - Models tested:
     - `SVC()`
     - `RandomForestClassifier()`
   - Validation strategies:
     - `KFold(n_splits=10)`
     - `StratifiedKFold(n_splits=3)`

3. **Evaluation Metrics**
   - Accuracy  
   - Recall  
   - F1-Score  
   - ROC-AUC  
   - Confusion Matrix  

---

## Key Results

| Comparison | Mean Accuracy | Validation Method |
|-------------|----------------|-------------------|
| SVM (KFold-10) | **≈ 75.3%** | KFold (10 folds) |
| SVM (StratifiedKFold-3) | **≈ 72.0%** | StratifiedKFold (3 folds) |

- **Performance difference:** ~3.2%  
- **Most important features:** `Glucose`, `BMI`, and `Age`  
- Some derived features had **neutral or slightly negative** effect on model accuracy.

---

## Insights

- Cross-validation choice **directly affects model reliability**, especially with unbalanced datasets.  
- In clinical contexts, **Recall** is more critical than Accuracy — missing a diabetic case (false negative) is worse than a false alert.  
- Feature engineering should be **guided by domain knowledge**, not only by statistical correlation.

---
