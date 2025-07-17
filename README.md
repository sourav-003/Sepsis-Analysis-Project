# 🏥 Sepsis and Septic Shock Detection Using Machine Learning

## 📌 Problem Statement

Sepsis and septic shock are medical emergencies with high mortality. The aim of this project is to use machine learning to predict sepsis early using clinical features, minimizing false negatives to ensure timely treatment.

---

## 📊 Project Overview

Early detection of **sepsis and septic shock** is critical in reducing mortality rates in ICU patients. This project applies **machine learning algorithms** to predict sepsis status using patient-level clinical data. Due to the life-threatening nature of undiagnosed sepsis, the model development emphasizes **recall for the minority (sepsis) class**, ensuring as few false negatives as possible.

> 🎯 **Goal:** Build an interpretable, recall-optimized predictive model for sepsis, using electronic health record (EHR) data.

---

## 📂 Dataset Description

### 🔹 `sepsis_status.csv`
- **Rows:** 91,713 patient encounters  
- **Features:** 186 clinical variables  
- **Target:** `septic_shock` (`0` = non-septic, `1` = septic)

### 🔹 `Parameter_detail_Dictionary.csv`
- Contains detailed medical descriptions, units, and definitions for each parameter in the main dataset.

---

## ⚠️ Medical Relevance

- **False Negatives (missed sepsis)** are extremely dangerous.
- The project **prioritizes recall** over precision for the sepsis class.
- Feature selection and model interpretation align with **clinical scores** such as:
  - qSOFA
  - SOFA
  - SIRS criteria

---

## 🧠 Modeling Approach

### ✅ Models Trained:
- Random Forest
- XGBoost
- Support Vector Machine (SVM)
- Naïve Bayes

### ✅ Techniques Used:
- **Undersampling** to handle class imbalance
- **Oversampling** to handle class imbalance
- **Recall-focused metric optimization**
- **Cross-validation and stratified train-test split**
- **Hyperparameter-Tuning** to **optimize model performance**

---

## 🥇 Best Performing Model

### 🏆 Random Forest (with Undersampling)
- **Recall (Sepsis)**: **0.79**
- **Precision**: 0.63
- **F1 Score**: 0.70
- **Accuracy**: ~87% (not meaningful due to imbalance)

> This model achieved the highest recall for sepsis while maintaining acceptable precision, making it ideal for clinical alert systems.

---

### 🔬 Medically relevant features:
| Feature         | Description                            |
|----------------|----------------------------------------|
| `lactate_apache` | Indicates tissue hypoxia |
| `heart_rate_apache` | Elevated in systemic infection |
| `resprate_apache` | Used in qSOFA criteria |
| `wbc_apache` | Elevated/suppressed in infection |
| `creatinine_apache` | Indicates kidney dysfunction |

---

## 📈 Evaluation Metrics

| Metric     | Class 1 (Sepsis) Focus |
|------------|------------------------|
| Recall ✅   | **0.79** |
| Precision  | 0.63 |
| F1 Score   | 0.70 |
| Accuracy   | 87% (inflated due to class 0)

---

## 🛠 Installation

### 📦 Requirements
```bash
pip install pandas scikit-learn xgboost shap matplotlib
