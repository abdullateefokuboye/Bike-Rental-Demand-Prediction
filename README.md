[Back](https://abdullateefokuboye.github.io/)

# Bike Rental Demand Prediction

![Bike Sharing Image](/image-s9ihjmnfa-transformed.png)

## Overview

Welcome to our Bike Rental Demand Prediction Project! This project aims to forecast the number of bike rentals based on various environmental and temporal features using a data-driven approach. We utilize machine learning algorithms to make accurate predictions that can help in efficient bike fleet management.

## Key Objectives
- Preprocess and explore the data to understand the distribution and correlation of variables.
- Build various regression models and evaluate their performance using cross-validation.
- Select the best model based on the Root Mean Squared Logarithmic Error (RMSLE) metric.

## Technologies Used
- Python for data manipulation and modeling.
- Pandas and NumPy for data analysis.
- Scikit-learn for building and evaluating regression models.
- Matplotlib and Seaborn for data visualization.

## Dataset

We use a rich dataset containing hourly rental data, along with weather and seasonal information. Here’s a glimpse into the data we use:

- Temperature (F)
- Humidity (%)
- Wind speed (mph)
- Visibility (miles)
- Dew point temperature (F)
- Rainfall (in)
- Snowfall (in)
- Solar radiation (MJ/m^2)
- Holidays
- Functioning days of the system

## Data Preprocessing

Our dataset captures the pulse of urban mobility, featuring:
- **Weather Conditions**: Temperature, humidity, wind speed, and more.
- **Time Metrics**: Hourly data including holidays and business operations.
- **Environmental Factors**: Solar radiation, dew point, and precipitation.

This comprehensive dataset allows us to analyze how various factors influence bike rental behaviors.

## Data Preprocessing: Crafting Quality Inputs

Quality data leads to quality insights. We meticulously cleaned and prepared our dataset, transforming raw data into a format suitable for analysis. Here’s how we tackled missing data and extracted new features:

```python
# Handling missing values and extracting the 'Hour' feature
train['DateHour'] = pd.to_datetime(train['DateHour'])
train['Hour'] = train['DateHour'].dt.hour
train.fillna(method='ffill', inplace=True)
```

## Insights from Exploratory Data Analysis (EDA)

Our EDA revealed fascinating trends:
- **Peak Hours**: Rentals spike during morning and evening rush hours.
- **Weather Impact**: Clear weather days significantly boost rental activities.

Visualizations from our EDA helped us understand the cyclical nature of bike rentals:

```python
# Plotting bike rentals over different hours of the day
sns.lineplot(x='Hour', y='RENTALS', data=train, marker='o')
plt.title('Impact of Hour on Bike Rentals')
plt.xlabel('Hour of the Day')
plt.ylabel('Number of Rentals')
```

## Choosing the Best Model

After experimenting with multiple models, the Decision Tree Regressor emerged as best due to its precision and ability to capture non-linear relationships without overfitting:

```python
# Model evaluation with Decision Tree
decision_tree = Decision TreeRegressor()
cv_scores = cross_val_score(decision_tree, X_train, y_train, scoring='neg_mean_squared_log_error', cv=5)
mean_rmsle = np.sqrt(-cv_scores.mean())
print(f"Optimized RMSLE: {mean_rmsle}")
```

## Unveiling the Final Model's Performance

Our chosen model was put to the ultimate test on unseen data, showcasing its robustness and accuracy:

```python
# Final evaluation on the test set
y_pred = decision_tree.predict(X_test)
final_rmsle = np.sqrt(mean_squared_log_error(y_test, y_pred))
print(f"Final Test RMSLE: {final_rmsle}")
```

This final RMSLE score reflects the model’s efficiency in predicting real-world scenarios, underscoring the practical value of our analytical rigor.

## Conclusion: Navigating the Future of Urban Mobility

Our predictive model not only forecasts bike rental demands but also illuminates the dynamics of urban transportation. Details of the code can be found in the repo:[Github repository](https://github.com/abdullateefokuboye/Bike-Rental-Demand-Prediction)

[Back to homepage](https://abdullateefokuboye.github.io/)
