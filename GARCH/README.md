# Bitcoin Volatility Forecasting with GARCH and AR-GARCH Models

## Overview

This project builds a volatility modeling pipeline using daily Bitcoin (BTC-USD) prices. It applies both GARCH(1,1) and AR(1)-GARCH(1,1) models to estimate and visualize conditional volatility. The notebook includes data preprocessing, statistical diagnostics (ADF, JB, ARCH test), and AIC/BIC comparison for model evaluation.

## Features

- Downloads BTC-USD data using `yfinance`
- Computes daily log returns from price data
- Plots historical prices and return series
- Conducts normality and stationarity tests (Jarque-Bera, ADF, KPSS)
- Tests for heteroskedasticity using ARCH-LM
- Visualizes ACF and PACF of log returns
- Fits both GARCH(1,1) and AR(1)-GARCH(1,1) models
- Plots conditional volatility over time
- Computes raw and per-observation AIC/BIC

## Prerequisites

- Python 3.8+
- pandas  
- numpy  
- matplotlib  
- scipy  
- statsmodels  
- arch  
- yfinance  

## Installation

```bash
git clone https://github.com/youruser/bitcoin-garch-volatility.git
cd bitcoin-garch-volatility
pip install -r requirements.txt
```

## Project Structure

```
bitcoin-garch-volatility/
├── GARCH_bitcoin_new_.ipynb      # Main notebook with modeling pipeline
├── bitcoin_2018_2022.csv         # Raw price data (optional export)
├── bitcoin_log_returns_2018_2022.csv  # Preprocessed log returns
├── requirements.txt              # Python dependencies
└── README.md                     # Project documentation
```

## Usage

Open the notebook:

```bash
jupyter notebook GARCH_bitcoin_new_.ipynb
```

Run each cell to:

1. Fetch historical BTC-USD price data
2. Calculate log returns and visualize price/return trends
3. Perform summary stats and diagnostics (JB, ARCH, ADF, KPSS)
4. Fit GARCH(1,1) and AR(1)-GARCH(1,1) models
5. Visualize conditional volatility and compare model AIC/BIC

## Configuration

The following settings can be adjusted in the notebook:

| Parameter         | Description                                 | Default         |
|------------------|---------------------------------------------|-----------------|
| `ticker`         | Ticker to download via yfinance             | `'BTC-USD'`     |
| `start_date`     | Start date for data download                | `'2020-01-01'`  |
| `end_date`       | End date for data download                  | `'2025-01-01'`  |
| `p, q`           | GARCH lag parameters                        | `p=1, q=1`      |
| `mean model`     | Type of mean model (`None`, `AR`)           | `'AR'` in AR-GARCH|

## Output Interpretation

- **Price and Return Plots**: Visual trend and volatility of BTC
- **Statistical Tests**:
  - **Jarque-Bera**: Tests normality of returns
  - **ADF / KPSS**: Test for stationarity
  - **ARCH-LM**: Tests for conditional heteroskedasticity
- **ACF/PACF**: Checks serial correlation patterns
- **Model Summary**: Includes coefficient estimates and significance
- **Volatility Plot**: Shows time-varying volatility estimated by GARCH
- **AIC/BIC**: Used for model comparison (raw and per observation)

## Contributing

Contributions are welcome! Add enhancements like:
- EGARCH / TGARCH comparisons
- Out-of-sample forecast evaluation
- Interactive dashboards with Plotly or Streamlit

---

Let me know if you'd like a `requirements.txt` auto-generated or want to publish this as a research repo.
