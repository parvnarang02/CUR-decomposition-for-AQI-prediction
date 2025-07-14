

# Tensor CUR Decomposition for AQI Prediction

This project presents a robust machine learning pipeline integrating **Tensor CUR Decomposition** with **Gradient Boosting Regression** for accurate and interpretable **Air Quality Index (AQI) prediction**. The solution focuses on preserving semantic meaning while reducing dimensionality, making it highly relevant for real-world environmental monitoring.

---

## 📌 Objective

Develop a scalable, interpretable model to predict AQI using air pollution data from Indian cities. The system applies Tensor CUR decomposition to retain the most meaningful rows and columns before training the predictive model.

---

## 🧠 Key Features

- **Tensor CUR Decomposition** for dimensionality reduction while preserving data interpretability.
- **Gradient Boosting Regressor** (GBR) for accurate AQI forecasting.
- Support for multiple experimental variants including:
  - Raw data modeling
  - CUR with various levels of preprocessing
  - PCA and SVM for comparative benchmarks
- Evaluation using **RMSE**, **MAE**, and **R² Score**
- Visual diagnostics: true vs predicted plots, residual analysis, and CUR reconstruction error

---

## 🗂 Dataset

Collected from the **Central Pollution Control Board (CPCB)**:
- `city_day.csv`
- `city_hour.csv`
- `station_day.csv`
- `station_hour.csv`
- `stations.csv`

---

## 🛠️ Methodology

### 1. **Data Preprocessing**
- Missing value imputation (mean strategy)
- Outlier removal using Z-score
- Feature filtering and correlation analysis
- Standard scaling of features

### 2. **CUR Decomposition**
- Select top-k rows and columns based on variance
- Approximate the original matrix as `A ≈ C * U * R`
- Calculate **Frobenius norm relative error** for approximation quality

### 3. **Model Training**
- **Gradient Boosting Regressor** trained on CUR-reduced features
- Hyperparameter tuning for improved performance

### 4. **Evaluation Metrics**
- **RMSE:** Root Mean Square Error
- **MAE:** Mean Absolute Error
- **R² Score:** Coefficient of Determination

### 5. **Visualization**
- Scatter plots for prediction analysis
- Residual analysis
- CUR reconstruction error distribution

---

## 📊 Results Summary

| Experiment | RMSE  | MAE   | R² Score |
|------------|-------|-------|----------|
| Raw + GBR  | 86.87 | 67.00 | -        |
| CUR + GBR  | 62.00 | 46.00 | 0.78     |
| CUR + Preprocessing 2 | **39.70** | **22.96** | **0.9124** |

- CUR showed superior performance over PCA and raw baseline
- CUR decomposition achieved a Frobenius relative error of **~0.22**

---

## 📈 Use Cases

- Real-time AQI monitoring systems
- Government and municipal air quality dashboards
- Environmental research and academic studies
- Health risk analysis and alert systems

---

## 🏁 Future Scope

- Integrate meteorological and mobility data
- Extend to pollutant-level prediction (PM2.5, NO₂, etc.)
- Deploy as a real-time AQI monitoring API
- Apply **SHAP** or **LIME** for deeper model interpretability
- Explore **transfer learning** for multi-city generalization

---


