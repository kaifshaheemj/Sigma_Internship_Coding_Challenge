
# Sigma Internship Coding Challenge using APPLE Stock data

## Description

This QuantRocket project retrieves and analyzes daily Apple (AAPL) stock data for the year 2023, specifically focusing on the date and closing price. The project utilizes QuantRocket's data fetching capabilities to obtain historical data.

## Analysis and Model Building

This project focuses on the analysis and forecasting of time series data using various techniques. The main features implemented in the project include:

### Data Extraction using Quantrocket
```markdown
```python
import pandas as pd
from quantrocket.history import get_prices

# Define parameters for data extraction
sids = 'FIBBG000B9XRY4'
start_date = '2023-01-01'
end_date = '2023-12-31'
data_frequency = 'daily'
fields = 'Close'

# Get historical prices using QuantRocket Zipline
data = get_prices("usstock-free-1min",
                  data_frequency=data_frequency,
                  sids=sids,
                  start_date=start_date,
                  end_date=end_date,
                  fields=fields)

# Display the extracted data
print(data.head())
```

### Output of Model for Finding the Optimal Portfolio Value and Transition Probability

**Portfolio Analysis Results**

Final Portfolio Value: 17

**Optimal Buy Indices:** 
[6, 8, 12, 16, 21, 28, 30, 41, 50, 52, 59, 61, 69, 79, 85, 88, 94, 100,
103, 108, 110, 113, 117, 120, 123, 133, 142, 160, 164, 177, 187, 191,
207, 209, 212, 216, 218, 232, 234, 238]



### Transisition Distribution

|         | Bear       | Flat       | Bull       |
|---------|------------|------------|------------|
| Bear    | 0.14285714 | 0.74285714 | 0.11428571 |
| Flat    | 0.1402439  | 0.61585366 | 0.24390244 |
| Bull    | 0.12280702 | 0.66666667 | 0.21052632 |


### Visualizations

- Moving Average Plot
- Time Series Decomposition Moving Average Plot
- ARIMA Model Prediction Moving Average Plot
- XGBoost Forecasting Moving Average Plot
- Differenced Time series Moving Average Plot
- ADFuller Test

#### Stationarity Test Results

### ADF Test Results

- **Null Hypothesis:** The series has a unit root (non-stationary)
- **ADF-Statistic:** -2.4602738974983085
- **P-Value:** 0.34809993717024723
- **Number of lags:** 0
- **Number of observations:** 249

**Interpretation:**

With a test statistic of -2.5861 and a p-value of 0.0959, we fail to reject the null hypothesis of non-stationarity at the 5% significance level. This suggests that the time series is likely non-stationary.

### Forecasting for next n days from jan1 2024 (say 14 days) using ARIMA

#### Overview

The analysis is conducted in a Jupyter Notebook (sigma-forecasting_and_model.ipynb) and covers a comprehensive exploration of time series data. The main steps and findings are summarized below.

- Moving Average Plot
- Time Series Decomposition
- ADFuller Test
- Optimal Portfolio Value

#### Data Extraction with QuantRocket Zipline

QuantRocket Zipline is used for efficient data extraction, allowing seamless integration of financial data into the analysis.

#### Forecasted Values for the Next 15 Days

These are the forecasted stock prices for the next 14 days based on the ARIMA model. The table below provides the day index and the corresponding forecasted values.

- **Values:** 
  - 193.15
  - 193.58
  - 192.53
  - 192.13831001443083
  - 191.46161817753003
  - 191.69733396232434
  - 192.43813614537612
  - 191.69903166528383
  - 190.98688840014083
  - 191.02468596395883
  - ..
  - ..
## Conclusion

In this project, we applied time series analysis methodologies, notably employing the ARIMA model, to predict the future stock prices of Apple over the upcoming 15-day period. The process encompassed retrieving historical stock price data for the entirety of 2023, establishing and fine-tuning an ARIMA model, and presenting graphical representations of both the historical and projected stock prices.

Thank you for exploring this time series forecasting project!
