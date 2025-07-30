## 🧠 Introvert vs. Extrovert Personality Prediction – Binary Classification

This notebook builds a machine learning model to classify individuals as **Introvert** or **Extrovert** based on their behavioral and social activity features.

We'll explore:

- Data cleaning and preprocessing  
- Feature engineering  
- Model training and evaluation  

---

## ✅ Model Benchmarking Summary

We evaluated multiple classifiers using consistent preprocessing and stratified train-test validation. Here's the performance summary:

| Model                   | Accuracy | F1 Score (Macro) | Notes                                                                 |
|-------------------------|----------|------------------|-----------------------------------------------------------------------|
| **Logistic Regression** | **97%**  | **96%**          | Captured linear separation well. Simple yet effective.               |
| **Random Forest**       | 97%      | 96%              | Handled non-linear interactions. Slight overfitting observed.        |
| **Gradient Boosting**   | 97%      | 96%              | Performed consistently across folds.                                 |
| ✅ **XGBoost (Tuned)**   | 97%      | 96%              | Final model after `GridSearchCV` tuning. Robust and generalizable.   |

---

## 📌 Problem Statement

**Goal:** Predict whether a person is an **Extrovert** or **Introvert** using social interaction behavior and lifestyle patterns.

**Target Variable:**  
- `Personality`: 0 → Extrovert, 1 → Introvert

**Dataset Source:** [Kaggle - Playground Series S5E7](https://www.kaggle.com/competitions/playground-series-s5e7/data)

---

## 🧼 Data Preprocessing

- **Imputation**:
  - Numerical: Filled with mean
  - Categorical: Filled with mode

- **Encoding**:
  - Binary categorical features (`Stage_fear`, `Drained_after_socializing`) → One-Hot Encoding
  - Target (`Personality`) → Label Encoding (Extrovert = 0, Introvert = 1)

- **Scaling**:
  - Applied `MinMaxScaler` to social activity-related numeric columns

---

## 🧪 Feature Engineering

Created additional meaningful features to enhance predictive signal:

- `social_energy_score`: A composite metric aggregating overall social activity
- `introversion_ratio`: Time spent alone vs. number of close friends
- `active_socializer`: Boolean flag based on high activity thresholds
- `low_energy_flag`: Derived from responses to social fatigue & stage fear

---

## 📈 Modeling Strategy

- Models used:
  - Logistic Regression
  - Random Forest
  - Gradient Boosting
  - ✅ XGBoost with GridSearchCV (Best model)

- Evaluation Metrics:
  - Accuracy
  - F1 Score (Macro) — used due to slight class imbalance
  - Cross-validation for robustness

---

## 🏁 Final Results

- **Best Model:** ✅ **XGBoost Classifier (tuned)**
- **Accuracy:** 97%
- **F1 Score:** 96% (Macro)
- Demonstrated strong performance across metrics with consistent results

---

## 📌 Key Takeaways

- Social interaction features are highly predictive of personality types.
- Custom features like `introversion_ratio` improved model separation.
- Simple preprocessing and thoughtful feature engineering can yield strong performance.

---

## 🚀 Future Work

- Add SHAP-based interpretability visualizations
- Build a web-based personality prediction interface using Streamlit
- Explore time-based data or interaction logs if available

---

## 📁 Files

- [`predict-the-introverts-from-extroverts.ipynb`](https://www.kaggle.com/code/shivangi2k18/predict-the-introverts-from-extroverts) – Main notebook  
- [`data/`](https://www.kaggle.com/competitions/playground-series-s5e7/data) – Competition dataset  
- [`submission.csv`](https://www.kaggle.com/code/shivangi2k18/predict-the-introverts-from-extroverts/output) – Final model predictions

---

## 📬 Contact

Interested in collaborating or discussing the project?  
Connect with me on [LinkedIn](https://www.linkedin.com/in/shivangigupta01)
