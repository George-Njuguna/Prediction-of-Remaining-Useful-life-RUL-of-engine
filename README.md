
# Predictive Maintenance – Remaining Useful Life (RUL) Prediction

## Introduction

This project applies machine learning to predict the **Remaining Useful Life (RUL)** of engines using the **NASA CMAPSS dataset**. Accurate RUL prediction is crucial for predictive maintenance, helping reduce downtime, improve safety, and optimize costs.

We experimented with several models including **Linear Regression, Ridge Regression, Random Forest, XGBoost, and NGBoost**, followed by **hyperparameter optimization**.

---

## Dataset

* **Source:** NASA CMAPSS dataset
* **Datasets used:** FD001, FD002, FD003, FD004
* Each dataset contains **engine cycles, operational settings and  sensor measurements** until failure.
* **Target variable:** Remaining Useful Life (RUL)

---

##  Methodology

1. **Exploratory Data Analysis (EDA):** Identified distributions, correlations, and sensor behavior.
2. **Feature Engineering:**

   * Removed low variance features.
   * Applied scaling and log transformations where necessary.
   * Evaluated feature importance from tree-based models.
3. **Modeling:**

   * Linear Regression (baseline)
   * Ridge Regression
   * Random Forest
   * XGBoost
   * NGBoost
4. **Model Optimization:**

   * Hyperparameter tuning with **RandomizedSearchCV** for XGBoost.

---

##  Results

### Mean Performance Across All Datasets

| Model                   | Mean R²  | Mean MSE   |
| ----------------------- | -------- | ---------- |
| Linear Regression       | \~0.73   | \~631      |
| Ridge Regression        | \~0.73   | \~630      |
| Random Forest           | 0.764    | 561.67     |
| NGBoost                 | 0.765    | 556.00     |
| **XGBoost**             | **0.76** | **553.78** |
| **XGBoost (Optimized)** | **0.77** | **533.21** |

---

##  Key Insights

* **XGBoost outperformed all other models**, especially after hyperparameter tuning.
* **Cycle count** and **Sensor 11** consistently ranked as the most important predictors of RUL.
* Scatter plots revealed that all models struggle to extrapolate **higher RUL values** (newer engines).
* FD001 was the easiest dataset to predict, while FD004 was the hardest due to higher noise and complexity.

---

##  Conclusion

This project demonstrates the potential of machine learning for **predictive maintenance and RUL forecasting**. Optimized **XGBoost achieved R² ≈ 0.77 and MSE ≈ 533**, outperforming other models.

While the model successfully captures degradation trends, **further improvement is needed for high RUL predictions**. Future work could involve **deep learning architectures (LSTMs, Transformers)** to better capture temporal dependencies in sensor data.

---

##  Future Work

* Experiment with **deep learning models** for time-series prediction.
* Incorporate **survival analysis or probabilistic modeling** for uncertainty estimation.
* Deploy as a **real-time predictive maintenance system**.

---
