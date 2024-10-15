# Predictive-Maintenance

### Summary and Recommendations

#### 1. Overview

This project focuses on predicting machinery failures based on sensor data. By analyzing various metrics collected from machines, such as temperature, pressure, and other performance indicators, the model helps to identify early signs of potential failures. The goal is to implement machine learning models to forecast when a machine is likely to fail, allowing for proactive maintenance and reduced downtime.

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
  - Random Forest Classifier: A decision tree ensemble method that works well for complex datasets.
  - XGBoost: An optimized gradient boosting technique for better performance.
  - LSTM (Optional): A Long Short-Term Memory network was also considered for time-series data modeling, leveraging the sequential nature of the sensor readings.
4. Hyperparameter Tuning
5. Evaluation

#### 4. Key Findings
      
Class Imbalance:

- The confusion matrix and classification report show the model's difficulty in predicting the minority class (machinery failures). Despite high overall accuracy (0.9982), it struggles with recall and precision for failures (class 1).
- Precision for Class 1 (Failures) is very low, indicating that the model is not good at detecting failures without predicting many false positives.

Feature Importance:
- The Random Forest model provides feature importances that help you understand which sensor metrics and engineered features are most predictive of failure. This insight is valuable for improving the model and identifying key sensors to monitor in real-time.

ROC-AUC Score:
- The ROC-AUC Score (0.8842) is good, indicating that the model performs well when considering probabilistic predictions. This is better than raw accuracy because it takes into account the ability to rank predictions correctly, which is crucial in imbalanced classification problems.

Class Weights and Handling Imbalance:
- The class imbalance problem is clear from the output. By incorporating class weights in both Random Forest and XGBoost, the revised code attempts to address this by penalizing misclassifications of the minority class (failures).

#### 5. Further Improvements:

- Consider using SMOTE or other resampling techniques to address the severe class imbalance.
 - Fine-tune the decision threshold for classifying failures to increase the recall for the minority class, depending on the business requirements for detecting failures.

#### 6. Source

https://www.kaggle.com/datasets/hiimanshuagarwal/predictive-maintenance-dataset
