# Website Traffic Forecasting with ARIMA & Auto-ARIMA

## Project Overview

This project analyzes and forecasts website traffic using classical time series models, specifically **ARIMA** and **Auto-ARIMA**.

The main objectives were to:

- Explore the time series behavior
- Check for stationarity
- Apply transformations when necessary
- Build forecasting models
- Compare manual ARIMA vs automated model selection

---

## Data Exploration

The dataset contains **393 observations** of website traffic.

Initial visualization showed:
- A clear upward trend
- Increasing variability over time

Because the variance increased as traffic grew, a **log transformation** was applied to stabilize variance and improve model performance.

---

## Stationarity Analysis

Since ARIMA models require stationarity, the following methods were used:

- Visual inspection of the time series
- ACF and PACF plots
- Augmented Dickey-Fuller (ADF) test

Differencing was applied when necessary to achieve stationarity.

---

## Train–Test Split

The last **30 observations** were reserved as the test set.  
The remaining data was used for training.

This preserves time order, which is essential in forecasting problems.

---

## Models Implemented

###  Manual ARIMA

- Order selected using ACF/PACF interpretation
- Example result: `ARIMA(2,1,0)`

### Auto-ARIMA (pmdarima)

- Automatic model selection based on AIC
- Brute-force search (`stepwise=False`)
- Non-seasonal configuration (`seasonal=False`)

---

## Forecast Comparison

Both models were used to forecast the test period.  
Predictions were plotted alongside actual traffic values to visually compare performance.

The forecasts followed previous momentum, while actual traffic showed a temporary decline before recovering.

---

## Key Takeaways

- Log transformation helps stabilize variance in growing time series.
- ARIMA requires stationarity before modeling.
- Auto-ARIMA simplifies model selection but should be understood conceptually.
- Time order must always be preserved in forecasting tasks.

---

## Libraries Used

- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`
- `pmdarima`
- `sklearn`

---


