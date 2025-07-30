## 🔍 Problem Statement
problem:
  objective: Predict whether a person is an Extrovert or Introvert
  based_on:
    - Time spent alone
    - Stage fear
    - Attendance at social events
    - Going outside frequency
    - Post frequency
    - Friends circle size
    - Responses to social fatigue

## 🧼 Data Preprocessing
data_preprocessing:
  imputation:
    numerical_columns: mean
    categorical_columns: mode

  encoding:
    binary_features_encoded:
      - Stage_fear
      - Drained_after_socializing
    target_encoding:
      variable: Personality
      method: label encoding
      mapping:
        Extrovert: 0
        Introvert: 1

  scaling:
    method: MinMaxScaler
    applied_to: social activity-related numeric columns

## 🧪 Feature Engineering
feature_engineering:
  derived_features:
    - name: social_energy_score
      description: Composite metric capturing social activity
    - name: introversion_ratio
      description: Ratio of time spent alone to size of friends circle
    - name: active_socializer
      description: Boolean flag based on thresholds
    - name: low_energy_flag
      description: Derived from drained social energy and stage fear

## 📈 Model Training & Evaluation
model_evaluation:
  models_tested:
    - model: Logistic Regression
      accuracy: 97%
      f1_macro: 96%
    - model: Random Forest
      accuracy: 97%
      f1_macro: 96%
    - model: Gradient Boosting
      accuracy: 97%
      f1_macro: 96%
    - model: XGBoost (Tuned)
      accuracy: 97%
      f1_macro: 96%
      selected: true

  final_model:
    name: XGBoostClassifier
    tuning: GridSearchCV
    evaluation_metric: F1 Score (macro)

## 🚀 Submission Pipeline
submission_pipeline:
  steps:
    - Apply same preprocessing to test data
    - Generate predictions
    - Inverse transform target encoding
    - Export to submission.csv

  sample_submission:
    format: id,Personality
    examples:
      - 1001,Extrovert
      - 1002,Introvert

## 📁 Files
files:
  - name: Notebook
    description: Kaggle notebook containing full pipeline and modeling
    path: https://www.kaggle.com/code/shivangi2k18/predict-the-introverts-from-extroverts

  - name: Data
    description: Dataset provided for the competition
    path: https://www.kaggle.com/competitions/playground-series-s5e7/data

  - name: Submission
    description: Final model predictions submitted to Kaggle
    path: https://www.kaggle.com/code/shivangi2k18/predict-the-introverts-from-extroverts/output


## 📬 Contact

Interested in collaborating or discussing the project? Connect with me on LinkedIn - https://www.linkedin.com/in/shivangigupta01
