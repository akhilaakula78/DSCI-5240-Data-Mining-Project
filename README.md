# DSCI-5240-Data-Mining-Project: Roadway Crash Analysis and Prediction

This repository contains a comprehensive Jupyter Notebook that performs end-to-end analysis on two distinct datasets: one for predicting roadway crash clearance times (regression) and another for predicting revenue generation from e-commerce sessions (classification). The project covers data cleaning, feature engineering, exploratory clustering, and builds multiple predictive models.

---

### Overview

The project is divided into two main parts: **Regression Analysis** and **Classification Analysis**.

---

### Datasets

The repository includes four CSV files:

- **`Regression_train.csv`**  
  Training data for roadway crash analysis, containing fields like Crash ID, Crash Date, Crash Severity, Crash Time, Day of Week, Time Arrived, Time Notified, Time Roadway Cleared, Weather Condition, Autonomous Level Engaged, Vehicle Damage Rating, Vehicle Model Year, Person Age, Person Alcohol/Drug Test Results, Person Ethnicity, and Person Gender.

- **`Regression_test.csv`**  
  Test data for roadway crash analysis with the same features (excluding the target "Time to Clear Roadway").

- **`Classification_train.csv`**  
  Training data for e-commerce revenue prediction, including features such as VisitorType, Month, and various session and user metrics.

- **`Classification_test.csv`**  
  Test data for e-commerce revenue prediction with similar features.

Additionally, the `analysis_notebook.ipynb` Jupyter Notebook contains the complete analysis (data cleaning, feature engineering, clustering, model training, evaluation, and prediction) for both parts.

---

### Regression Analysis

##### **Objective:**  
Predict the "Time to Clear Roadway" after a crash.

##### **Workflow:**
- **Data Cleaning and Imputation:**  
  - Handling missing values via forward fill, backward fill, and group-based imputation (mode/median).
  - Dropping columns with excessive "No Data" entries.
  
- **Feature Engineering:**  
  - Converting date/time fields to proper datetime objects.
  - Computing "Time to Clear Roadway" by calculating the difference between crash time and roadway clearance time.
  - Deriving "Vehicle Age" by subtracting the vehicle model year from the current year.
  - Extracting additional date components such as crash month and crash day.
  
- **Categorical Transformations and One-Hot Encoding:**  
  - Mapping categorical features (e.g., Crash Severity, Weather Condition, Person Gender).
  - One-hot encoding multi-class features (e.g., Day of Week, Person Ethnicity).
  
- **Scaling:**  
  - Applying MinMaxScaler to bring all features into the range [0, 1].
  
- **Exploratory Clustering:**  
  - Using Agglomerative Clustering, KMeans, and PCA for visualization to explore data groupings.
  
- **Model Training:**  
  - Evaluating various regression models including:
    - Linear Regression
    - Polynomial Regression
    - Ridge Regression
    - Lasso Regression
    - SGDRegressor
    - Decision Tree Regressor
    - Bagging Regressor
    - Random Forest Regressor  
  - The Bagging Regressor demonstrated the best training performance.

---

### Classification Analysis

##### **Objective:**  
Predict whether an e-commerce session will generate revenue.

##### **Workflow:**
- **Data Cleaning and Preprocessing:**  
  - Dropping unnecessary index columns.
  - Handling missing values and mapping target values appropriately.
  - Converting boolean columns to integers.
  
- **Feature Transformation:**  
  - One-hot encoding categorical variables (e.g., VisitorType, Month).
  - Scaling features with MinMaxScaler.
  
- **Exploratory Clustering:**  
  - Applying clustering techniques to gain insights into underlying data groupings.
  
- **Model Training:**  
  - Building and evaluating multiple classification models such as:
    - Logistic Regression
    - Ridge Classifier
    - SGD Classifier
    - Decision Tree Classifier
    - Bagging Classifier
    - Random Forest Classifier

---
