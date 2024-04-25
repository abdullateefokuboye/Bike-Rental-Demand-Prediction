# Bike Rental Demand Prediction

## Project Overview
This project involves building a predictive model using a bike-sharing dataset to forecast the number of bike rentals based on various environmental and temporal features. The analysis utilizes multiple regression techniques to determine the most accurate model for predicting bike rental counts.

## Dataset Description
The dataset includes hourly rental data along with weather and seasonal information. Key features include:
- Temperature (F)
- Humidity (%)
- Wind speed (mph)
- Visibility (miles)
- Dew point temperature (F)
- Rainfall (in)
- Snowfall (in)
- Solar radiation (MJ/m2)
- Holidays
- Whether the day is functioning as a business day

## Key Objectives
- Preprocess and explore the data to understand the distribution and correlation of variables.
- Build various regression models and evaluate their performance using cross-validation.
- Select the best model based on the Root Mean Squared Logarithmic Error (RMSLE) metric.

## Technologies Used
- Python for data manipulation and modeling.
- Pandas and NumPy for data analysis.
- Scikit-learn for building and evaluating regression models.
- Matplotlib and Seaborn for data visualization.

## Model Evaluation
The performance of multiple regression models, including Linear Regression, K-Nearest Neighbors, Decision Tree Regressor, and Elastic Net Regression, was compared. Decision Tree Regressor was selected as the best model due to its lower RMSLE score.

