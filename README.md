# GDP Forecasting for BRICS Countries

This repository demonstrates how to forecast GDP for BRICS countries (Brazil, Russia, India, China, and South Africa) using various time series models including SARIMA, Exponential Smoothing, VAR, Prophet, and LSTM. The workflow includes data preprocessing, feature engineering, model fitting, forecasting, and evaluation.

---

## Overview

- **Time Series Analysis:** A statistical technique that deals with time-ordered data to forecast future values based on previously observed values.

- **Models Used:**
  - **SARIMA (Seasonal AutoRegressive Integrated Moving Average):** A popular statistical method for analysing time series data that incorporates seasonality.
  - **Exponential Smoothing:** A time series forecasting method for univariate data that applies decreasing weights to past observations.
  - **VAR (Vector AutoRegression):** A statistical model used to capture the linear interdependencies among multiple time series.
  - **Prophet:** A forecasting tool developed by Facebook that handles seasonality and holidays well.
  - **LSTM (Long Short-Term Memory):** A type of recurrent neural network suited for sequence prediction problems.

---

## Code Explanation

- **Data Loading and Preprocessing:** The code reads GDP data from a CSV file, sets the index to country names, and processes it for analysis.

- **Feature Engineering:** Lag features and rolling statistics are added to the dataset to improve model performance.

- **Model Definitions:** Functions for fitting various forecasting models (SARIMA, Exponential Smoothing, VAR, Prophet, and LSTM) are defined.

- **Forecasting:** Separate functions are created for each model to generate forecasts for the next six years.

- **Ensemble Forecasting:** An ensemble method combines predictions from multiple models to produce a final forecast.

- **Evaluation:** Forecasts are evaluated against actual values using metrics like Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and Mean Absolute Percentage Error (MAPE).

---

## Usage Instructions

To run this code, you'll need the following libraries:

```bash
pip install pandas numpy matplotlib seaborn statsmodels pmdarima scikit-learn prophet tensorflow

```
## Example of Forecasting

Here's an example of how to load data and generate a forecast for Brazil.

```
# Load and preprocess the data
gdp_data = load_and_preprocess_data('BRICSGDP.csv')

# Fit models and generate forecasts for Brazil
country = 'Brazil'
data = engineered_data[country].iloc[:, 0]
sarima_model = fit_sarima(data)
forecast = forecast_sarima(sarima_model, steps=6)

print(f"SARIMA Forecast for {country}: {forecast}")

```

## Evaluation Results

The models were evaluated using the last six years of available data, and metrics were calculated for each model.

```
for country in brics_countries:
    metrics = evaluation_results[country]
    print(f"\nEvaluation metrics for {country}:")
    for model_name, metric_values in metrics.items():
        print(f"Metrics for {model_name}:")
        for metric, value in metric_values.items():
            print(f"{metric}: {value:.4f}")
```
---

This repository illustrates the application of various time series forecasting techniques to predict GDP, offering a robust framework for further analysis and research in economic forecasting.

