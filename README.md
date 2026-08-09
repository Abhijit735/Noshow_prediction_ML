# Healthcare Appointment No-Show Prediction

A machine learning project to predict whether a patient will **miss a scheduled healthcare appointment** using patient and appointment-related information.

## Project Overview

This project explores an end-to-end classification workflow, starting from data gathering and exploratory data analysis through data preprocessing, feature engineering, handling class imbalance, model training, evaluation, and hyperparameter tuning.

The dataset contains **110,527 appointment records with 14 features**. 

## Objectives

* Understand the factors associated with missed healthcare appointments.
* Perform exploratory data analysis and data cleaning.
* Engineer relevant features from appointment information.
* Handle class imbalance using different oversampling techniques.
* Train and compare multiple classification algorithms.
* Evaluate models using classification metrics.
* Perform hyperparameter tuning to improve model performance.

## Workflow

```text
Data Gathering
      ↓
Data Exploration
      ↓
Data Cleaning
      ↓
Feature Engineering
      ↓
Feature Selection
      ↓
Train-Test Split
      ↓
Class Imbalance Handling
      ↓
Model Training
      ↓
Model Evaluation
      ↓
Hyperparameter Tuning
```

## Key Steps

### 1. Data Exploration

The dataset was inspected using:

* Dataset shape and structure
* Descriptive statistics
* Target distribution
* Categorical and numerical feature analysis
* Missing-value analysis
* Visualization

The notebook confirms that the dataset contains no missing values.

### 2. Data Preprocessing

The preprocessing includes:

* Renaming columns for consistency
* Encoding categorical variables
* Checking missing values
* Exploring numerical and categorical features
* Feature selection using statistical analysis

Chi-square feature analysis was also performed to identify features with statistically significant relationships with the target.

### 3. Feature Engineering

An appointment lead-time feature, `LeadDays`, was created to represent the time difference between scheduling and the appointment.

The modeling dataset uses features including:

* Gender
* Age
* Scholarship
* Hypertension
* Diabetes
* Alcoholism
* Handicap
* SMS Received
* Lead Days

### 4. Handling Class Imbalance

Since the target variable is imbalanced, different oversampling techniques were experimented with:

* Random OverSampling
* SMOTE
* ADASYN

The training data was resampled while keeping the test set separate for evaluation.

### 5. Model Training

The notebook experiments with multiple classification algorithms, including:

* Logistic Regression
* Random Forest
* AdaBoost
* XGBoost

Hyperparameter tuning was performed using `RandomizedSearchCV` with cross-validation for selected models.

### 6. Model Evaluation

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* Matthews Correlation Coefficient
* ROC-AUC during hyperparameter tuning

Because the target is imbalanced, particular attention was given to precision, recall and F1-score rather than relying only on accuracy.

## Example Result

For the baseline Logistic Regression model, the test accuracy was approximately **79.5%**. However, the recall for the minority `NoShow = Yes` class was very low, demonstrating why accuracy alone is not sufficient for this problem.

After oversampling, the minority-class recall improved substantially in the experiments. For example, SMOTE-based Logistic Regression achieved approximately **46% recall** for the `NoShow = Yes` class on the test set.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Statsmodels
* Shap values
* Lazypredict


## Key Learning Outcomes

Through this project, I explored:

* End-to-end machine learning workflow
* Exploratory data analysis
* Feature engineering
* Feature selection
* Classification algorithms
* Imbalanced classification
* Oversampling techniques
* Model evaluation
* Cross-validation
* Hyperparameter tuning
* Model comparison


## Note
This project represents my first dedicated machine learning project(academic project-2024), focusing on understanding the complete predictive modeling workflow.
