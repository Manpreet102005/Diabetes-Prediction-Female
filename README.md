# Diabetes Prediction for Females

A Flask web application that uses a trained machine learning model to predict diabetes based on health information provided by the user.

## Overview

The application evaluates information including:

- Age
- Number of pregnancies
- Glucose level
- Blood pressure
- Insulin level
- Weight and height, used to calculate BMI
- Diabetes history among first- and second-degree relatives

## Features

- Web form for entering health information
- Flask backend for processing inputs and returning a prediction
- Saved model, transformer, and scaler artifacts
- HTML and CSS frontend

## Tech Stack

- Python
- Flask
- Pandas
- NumPy
- scikit-learn
- XGBoost
- Joblib
- HTML and CSS

## How It Works

1. The user enters health information in the web form.
2. The application calculates BMI and derives a diabetes pedigree value from the family-history inputs.
3. The application transforms and scales the model inputs using saved artifacts.
4. The trained model produces a prediction probability.
5. The web application displays "Diabetic" or "Non Diabetic" based on a probability threshold.

## Live Demo

Visit the app here:
https://diabetes-prediction-female.onrender.com/

## Model Notes

The repository contains a trained model and saved preprocessing artifacts used by the application. The input-processing code applies the saved transformer and scaler before passing data to the model.

## Author

Created by Manpreet102005.
