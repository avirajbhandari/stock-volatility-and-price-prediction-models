# GARCH-Based Bitcoin Volatility Modeling Pipeline

## Overview

This project implements a pipeline to model and forecast the volatility of Bitcoin (BTC-USD) daily returns using the GARCH(1,1) model. The notebook performs data preprocessing, log return calculation, diagnostic testing (ADF, ARCH effects, normality), and conditional volatility estimation. It is designed to support academic econometrics research, particularly volatility modeling in crypto markets.

## Features

* Downloads historical BTC-USD price data using `yfinance`
* Computes daily log returns to stabilize variance
* Performs descriptive statistics and normality tests (kurtosis, skewness, Jarque-Bera)
* Conducts stationarity and ARCH-effect tests (ADF, KPSS, ARCH-LM)
* Plots price series, log returns, ACF and PACF
* Fits a GARCH(1,1) model using the `arch` package
* Visualizes conditional volatility over time
* Outputs summary statistics and model fit metrics

## Prerequisites

* Python 3.8+
* pandas  
* numpy  
* matplotlib  
* scipy  
* statsmodels  
* arch  
* yfinance

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/youruser/garch-bitcoin-pipeline.git
   cd garch-bitcoin-pipeline
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Project Structure

```
garch-bitcoin-pipeline/
├── GARCH_bitcoin_new_.ipynb      # Main notebook with full pipeline
├── bitcoin_2018_2022.csv         # Raw price data (optional export)
├── bitcoin_log_returns_2018_2022.csv  # Preprocessed returns data
├── requirements.txt              # Python dependencies
└── README.md                     # This documentation
```

## Configuration

You can modify the following settings directly in the notebook:

| Parameter         | Description                               | Default       |
|------------------|-------------------------------------------|---------------|
| `start_date`     | Beginning date for data download          | `'2020-01-01'`|
| `end_date`       | Ending date for data download             | `'2025-01-01'`|
| `p`, `q`         | GARCH model lag orders                    | `1, 1`        |
| `ticker`         | Ticker symbol for asset                   | `'BTC-USD'`   |

## Usage

1. Open the Jupyter Notebook:

   ```bash
   jupyter notebook GARCH_bitcoin_new_.ipynb
   ```

2. Run all cells to:
   - Download BTC price data  
   - Calculate and visualize log returns  
   - Perform normality and stationarity tests  
   - Fit a GARCH(1,1) model  
   - Plot conditional volatility  

## Output Interpretation

* **Log Return Plot:** Daily rate of return on BTC, capturing high-frequency price changes.
* **ACF/PACF Plots:** Show autocorrelation structures useful for ARIMA/GARCH modeling.
* **Diagnostic Test Results:** Confirm stationarity and presence of ARCH effects.
* **Model Summary:** Reports coefficient estimates and diagnostics.
* **Conditional Volatility Plot:** Illustrates time-varying volatility over the sample period.

## Contributing

Contributions welcome! You can help extend this project with:
- Additional GARCH-family models (e.g., EGARCH, TGARCH)
- Model comparison metrics (AIC, BIC, RMSE)
- Backtesting volatility forecasts
