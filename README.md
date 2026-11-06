# Diabetes Prediction for Females

A Flask web application that uses a trained machine learning model to predict diabetes based on health information provided by the user.

## Overview

The project uses the Pima Indians Diabetes dataset, containing 768 records, to train and evaluate classification models. The web app accepts health information including age, number of pregnancies, glucose level, blood pressure, insulin level, weight, height, and family diabetes history.

## Model Development

The `Diabetes.ipynb` notebook explores the data, prepares model inputs, compares classifiers, and selects a stacking classifier.

### Data preparation

- The data is divided into training, validation, and test sets (60%, 20%, and 20%, respectively).
- Zero values in Glucose, BloodPressure, SkinThickness, and Insulin are treated as missing values.
- Missing values in those features are imputed with their median. The imputer is fitted on the training set and applied to the validation and test sets.
- A `MinMaxScaler` is fitted on the training features and applied to the training, validation, and test sets.

### Model selection

The notebook compares several classifiers and uses `GridSearchCV` with stratified 10-fold cross-validation to tune model parameters. The selected model is a `StackingClassifier` with Random Forest, XGBoost, and Ridge base estimators and an SGD classifier as the final estimator. The notebook reports a validation accuracy of about 79.2% for this model.

## How the Web App Works

1. The user enters health information in the web form.
2. The application calculates BMI from weight and height and derives a diabetes pedigree value from the family-history inputs.
3. The application applies its saved transformer and scaler to the input features.
4. The saved model produces a prediction probability, which the web form maps to “Diabetic” or “Non Diabetic” using a threshold.

## Tech Stack

- Python
- Flask
- Pandas and NumPy
- scikit-learn
- XGBoost
- Joblib
- HTML and CSS

## Live Demo

[Open the web app](https://diabetes-prediction-female.onrender.com/)

## Author

Created by Manpreet102005.
