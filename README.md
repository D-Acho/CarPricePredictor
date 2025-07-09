# 🚗 Car Price Predictor

## 🎯 Objective
Develop a machine learning model capable of predicting the market value of a car, taking into account prediction quality, execution speed, and training time.

---

## 📊 Exploratory Data Analysis (EDA)

The following preprocessing steps were performed:

- Converted date columns to `datetime` format.
- Filtered out records with car prices equal to or less than 0.
- Removed extreme outliers in the price column.
- Filled missing values in categorical features.
- Dropped extracted date columns after feature engineering.
- Converted categorical variables using one-hot encoding.
- Removed `PostalCode` and `NumberOfPictures` due to low relevance.

---

## 🤖 Model Evaluation

Several regression models were tested to identify the optimal approach:

| Model            | RMSE    | Training Time |
|------------------|---------|----------------|
| Linear Regression | 1.2491 | 10.44 seconds  |
| Random Forest     | 0.5549 | 85.45 seconds  |
| LightGBM          | 0.5457 | 14.29 seconds  |

### 📌 Observations

- **Linear Regression** shows the highest error and serves as a baseline. It fails to capture nonlinear relationships.
- **Random Forest** significantly reduces error, but it’s computationally intensive when hyperparameter tuning is included.
- **LightGBM** achieves the **best RMSE** with **much faster training**—making it the most efficient and accurate model in this comparison.

---

## ✅ Conclusions

- Tree-based models outperform linear regression substantially, both in accuracy and robustness.
- LightGBM emerges as the best overall model by balancing precision and performance.
- Future work may explore feature selection, cross-validation, and deployment via an interactive dashboard.

---

## ⚙️ Technologies Used

| Purpose            | Tools & Libraries               |
|--------------------|----------------------------------|
| Data Preparation   | `pandas`, `numpy`               |
| Modeling           | `scikit-learn`, `lightgbm`, `xgboost` |
| Evaluation & Tuning| RMSE, GridSearchCV              |

---
