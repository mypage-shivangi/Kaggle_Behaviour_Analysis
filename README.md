
---

## 🔍 Problem Statement

Predict whether a person is an **Extrovert** or **Introvert** based on:
- Time spent alone
- Stage fear
- Attendance at social events
- Going outside frequency
- Post frequency
- Friends circle size
- Responses to social fatigue

---

## 🧼 Data Preprocessing

1. **Imputation**
   - Numerical columns: imputed using mean
   - Categorical columns: imputed using mode

2. **Encoding**
   - Binary categorical features (`Stage_fear`, `Drained_after_socializing`) were one-hot encoded
   - Target variable `Personality` was label-encoded (Extrovert=0, Introvert=1)

3. **Feature Scaling**
   - Applied `MinMaxScaler` on social activity-related numeric columns

---

## 🧪 Feature Engineering

Derived meaningful features:
- `social_energy_score`: composite metric capturing social activity
- `introversion_ratio`: time alone relative to friends circle size
- `active_socializer`: boolean flag based on thresholds
- `low_energy_flag`: derived from "Drained after socializing" & "Stage fear"

---

## 📈 Model Training & Evaluation

Evaluated multiple classifiers:

| Model                  | Accuracy | F1 Score (Macro) |
|------------------------|----------|------------------|
| Logistic Regression    | 97%      | 96%              |
| Random Forest          | 97%      | 96%              |
| Gradient Boosting      | 97%      | 96%              |
| ✅ XGBoost (Tuned)     | 97%      | 96%              |

- Final model: **XGBoostClassifier** with `GridSearchCV` hyperparameter tuning.
- Evaluation metric: **F1 Score (macro)** due to class imbalance.

---

## 🚀 Submission Pipeline

- Test data underwent the **same preprocessing pipeline**
- Final predictions were inverse-transformed and stored in `submission.csv`:

```bash
id,Personality
1001,Extrovert
1002,Introvert
...

## 📁 Files

- `predict-the-introverts-from-extroverts.ipynb` → https://www.kaggle.com/code/shivangi2k18/predict-the-introverts-from-extroverts
- `data/` → https://www.kaggle.com/competitions/playground-series-s5e7/data
- `submission.csv` → https://www.kaggle.com/code/shivangi2k18/predict-the-introverts-from-extroverts/output

---

## 📬 Contact

Interested in collaborating or discussing the project? Connect with me on LinkedIn - https://www.linkedin.com/in/shivangigupta01
