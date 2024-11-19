# Predictive-Maintenance

### Summary and Recommendations

#### 1. Overview

Predictive maintenance involves forecasting machinery failures using historical sensor data. This project uses machine learning to classify failure events, addressing the challenges of class imbalance and ensuring the model generalizes well to real-world scenarios.

#### 2. Data

The dataset used for this project contains several sensor readings (metrics) recorded over time, along with a target variable (failure) that indicates whether the machinery failed or not. The dataset includes:

- Metrics: metric1, metric2, metric3, ..., metric9 — various sensor readings.
- Date: Timestamp of the readings.
- Failure: Target variable (1 if machinery failed, 0 otherwise).
- Device: Type of machinery/device.

The data includes historical sensor readings and failure information, which allows us to train machine learning models for predictive maintenance.

#### 3. Data Analysis Steps

1. Data Preprocessing
2. Data Splitting
3. Modeling
  - Built a Random Forest Classifier to predict machinery failures.
  - Conducted hyperparameter tuning using GridSearchCV to optimize the model.
4. Evaluation
5. Optimization to class weights and feature selection to improve recall on failure class.

#### 4. Key Findings
      
Evaluation Metrics:
- Accuracy: ~99.93%
- ROC-AUC: ~1.00

Test Set Evaluation:
- ROC-AUC Score: 0.766
- Improved recall and precision for the minority class after SMOTE and hyperparameter tuning.

Feature Importance: Top features driving model predictions:

- metric4
- metric2
- metric5
- metric6
- metric1

#### 5. Challenges

Severe Class Imbalance:
- Failures accounted for less than 0.1% of the dataset.
- Addressed using SMOTE and class weighting.

Model Overfitting:
- High cross-validation accuracy but struggled with minority class predictions.
- Addressed with feature engineering and hyperparameter tuning.

Feature Correlation:
- Some sensor metrics exhibited high correlation, requiring careful selection and scaling.

Future Improvements

- Exploration of Advanced Models: Experiment with gradient boosting models (e.g., XGBoost, LightGBM) for better handling of imbalanced data.
- Temporal Analysis: Incorporate temporal patterns in the dataset using sequence-based models like LSTMs.
- Explainability: Use tools like SHAP or LIME to interpret model predictions.

### Source

    
