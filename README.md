# 🏨 Hospitality Booking Predictions — Team 8A

> Predicting hotel booking outcomes (Completed, Cancelled, No-Show) using multi-class classification on real-world hospitality data.

**Course:** ADTA 5410 — Applications & Deployment of Advanced Analytics

---

## 👥 Team — Group 8A

| Name |
|------|
| Sumanjali Banjara |
| Sathvik Chava |
| Sravani Enuganti |

---

## 📊 Dataset

| Property | Value |
|----------|-------|
| **Records** | 200,000 bookings |
| **Features** | 25 columns |
| **Target Variable** | `target_class` — Cancelled / Completed / NoShow |
| **Source** | Synthetic hospitality dataset |

---

## 🔬 Project Pipeline

| Step | Stage | Details |
|------|-------|---------|
| 1 | **Data Loading** | Load raw synthetic hospitality CSV |
| 2 | **Data Cleaning** | Handle missing values — median for numerical, mode for categorical |
| 3 | **Outlier Detection** | IQR method + Z-score comparison across numeric columns |
| 4 | **Outlier Handling** | IQR capping applied to 10 key features |
| 5 | **EDA** | Distributions, boxplots, correlation heatmap, outcome analysis |
| 6 | **Feature Engineering** | `booking_value`, `discount_level`, `age_group` created |
| 7 | **Encoding** | Label encoding for categorical variables |
| 8 | **Class Balancing** | SMOTE applied to training set |
| 9 | **Modeling** | 5 classifiers trained and evaluated |
| 10 | **Hyperparameter Tuning** | RandomizedSearchCV on CatBoost and Logistic Regression |
| 11 | **Feature Importance** | Top predictors identified for overall class and cancellations |

---

## 🧠 Models Implemented

| # | Model | Notes |
|---|-------|-------|
| 1 | **Logistic Regression** | Baseline multi-class classifier (multinomial) |
| 2 | **Random Forest** | Ensemble of decision trees with balanced class weights |
| 3 | **XGBoost** | Gradient boosting with `multi:softprob` objective |
| 4 | **LightGBM** | Fast gradient boosting with multiclass objective |
| 5 | **CatBoost** | Gradient boosting with native categorical support |

---

## 📈 Results & Model Comparison

Models evaluated on **Accuracy**, **F1 Macro**, **Precision Macro**, and **Recall Macro**.

| Model | Metric Focus | Highlights |
|-------|-------------|------------|
| **CatBoost (Tuned)** | 🏆 Best overall | Top F1 Macro after hyperparameter tuning |
| **LightGBM** | Fast & strong | Competitive F1, fastest training time |
| **XGBoost** | Well-rounded | Strong precision across all three classes |
| **Random Forest** | Stable baseline | Reliable with balanced class weights |
| **Logistic Regression (Tuned)** | Interpretable | Best for explainability, lower raw performance |

> See the full comparison table and bar charts in `ProjectNotebook_Team8A.ipynb`

---

## 💡 Key Insights

- **CatBoost with hyperparameter tuning** delivered the best macro F1 score across all three outcome classes
- **SMOTE balancing** significantly improved model sensitivity to minority classes (NoShow, Cancelled)
- **Top predictors** of booking outcome include: `lead_time_days`, `loyalty_points`, `avg_daily_rate`, `discount_pct`, and `booking_value`
- **Discount level and weekend check-in** showed strong association with cancellation rates
- **Customer age group** influenced booking completion patterns — younger customers had higher no-show rates

---

---

## 🌍 Real-World Impact

| Domain | Application |
|--------|-------------|
| **Revenue Management** | Predict no-shows and cancellations to optimize overbooking strategy |
| **Customer Retention** | Identify at-risk bookings early for targeted intervention |
| **Marketing Optimization** | Allocate discounts and offers to segments most likely to complete |
| **Operational Planning** | Improve staffing and resource allocation based on predicted outcomes |

---

*Made with ❤️ by Team 8A · ADTA 5410 · Applications & Deployment of Advanced Analytics*
