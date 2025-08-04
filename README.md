# Home Energy Usage Prediction and Classification

This project aims to analyze and predict energy usage levels in households using the `home_energy_data.csv` dataset. A range of feature selection methods and classification/regression models were applied to improve predictive performance.

## 📦 Dataset Details

- **File**: `home_energy_data.csv`
- **Target Variable (Classification)**: `Appliances` categorized into:
  - High (> 30) → 1
  - Low (≤ 30) → 0
- **Target Variable (Regression)**: `Appliances` (continuous)
- **Initial Features**: T1-T9 (temperature), RH1-RH9 (humidity), windspeed, visibility, etc.

## 🔄 Data Preprocessing

- Outliers detected via IQR
- Categorical columns removed: `datetime`, `rv1`, `rv2`
- Normalization via Min-Max scaling
- Class distribution checked (binary target)

## 🎯 Feature Selection Methods

1. **Pearson Correlation**
2. **Forward Selection** (Sequential Feature Selector)
3. **Backward Elimination**
4. **Particle Swarm Optimization (PSO)**
5. **Genetic Algorithm (GA)**

## 🤖 Classification Models

- Logistic Regression (tuned with GridSearchCV)
- Naive Bayes (GaussianNB)
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM with different kernels)

### 🔍 Classification Performance Summary

| Method     | Best Accuracy |
|------------|----------------|
| **LogReg + GA** | 0.9153 |
| **SVM + Backward** | 0.9147 |
| **Naive Bayes + PSO** | 0.9093 |
| **KNN + Backward** | 0.9053 |

## 📈 Regression Models (Optional Phase)

- **Linear Regression**
- **KNN Regressor**
- **Support Vector Regression (SVR)**

### 📊 Regression Metrics

| Method          | Best R² Score |
|------------------|---------------|
| **Linear Regression + Forward/GA** | 0.86+ |
| **SVR (rbf)** | ~0.85 |
| **SVR (sigmoid)** | *Very poor performance* (negative R²) |

## 📌 Key Takeaways

- **Logistic Regression + GA** gave the highest classification accuracy.
- **Linear Regression** with Forward or GA-selected features showed best regression performance.
- **SVR (sigmoid kernel)** severely underperformed across all settings.
- **PSO** worked well for **Naive Bayes**.
- **Forward Selection & GA** yielded best feature sets.

## 📁 Files in the Repository

- `energy_classification.R` → Preprocessing, feature selection, classification models
- `energy_regression.R` → Regression modeling using selected features
- `visualizations.R` → Accuracy and error comparison plots

## 📊 Visuals

- Bar plots for model comparison
- Heatmaps for feature correlations
- Line charts for error metrics across models

## 🧑‍💻 Author

**Amna Amir**  
BS Data Science | Air University  
