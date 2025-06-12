# Bitcoin Volatility Modeling with GARCH Family Models

## Overview

This project implements a comprehensive volatility modeling pipeline on Bitcoin (BTC-USD) daily returns using a wide range of GARCH-family models. It includes data preprocessing, statistical testing, and model estimation using both built-in libraries and custom likelihood functions. The goal is to analyze and compare volatility dynamics across symmetric and asymmetric GARCH variants.

## Features

- Fetches BTC-USD data via `yfinance`
- Computes and visualizes daily log returns
- Performs descriptive statistics and tests:
  - **Jarque-Bera** for normality
  - **ADF / KPSS** for stationarity
  - **ARCH-LM** for heteroskedasticity
- Plots ACF and PACF of log returns
- Implements the following volatility models:
  - **GARCH(1,1)** using `arch`
  - **EGARCH(1,1)** (Exponential GARCH)
  - **TGARCH(1,1)** (Threshold GARCH, aka GJR-GARCH)
  - **APARCH(1,1)** (Asymmetric Power ARCH)
  - **CGARCH(1,1)** (Component GARCH — manually implemented)
  - **ACGARCH(1,1)** (Asymmetric Component GARCH — manually implemented)
- Plots conditional volatility for each model
- Computes AIC/BIC (raw and per observation) for model comparison

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
git clone https://github.com/yourusername/bitcoin-volatility-garch-family.git
cd bitcoin-volatility-garch-family
pip install -r requirements.txt
```

## Project Structure

```
bitcoin-volatility-garch-family/
├── GARCH_bitcoin_new_.ipynb       # Main notebook with full modeling pipeline
├── bitcoin_2018_2022.csv          # Exported BTC price data (optional)
├── bitcoin_log_returns_2018_2022.csv  # Log return series (optional)
├── requirements.txt               # Python dependencies
└── README.md                      # Project documentation
```

## Configuration

Adjust these parameters directly in the notebook:

| Parameter       | Description                                 | Example          |
|----------------|---------------------------------------------|------------------|
| `ticker`       | Asset symbol from yfinance                  | `'BTC-USD'`      |
| `start_date`   | Start date for historical data              | `'2020-01-01'`   |
| `end_date`     | End date for historical data                | `'2025-01-01'`   |
| `model`        | Volatility model name (GARCH, EGARCH, etc.) | `'EGARCH'`, etc. |

## Usage

Launch the notebook and run each section:

```bash
jupyter notebook GARCH_bitcoin_new_.ipynb
```

Notebook stages:

1. Load BTC data and compute log returns
2. Run statistical diagnostics (normality, stationarity, ARCH effects)
3. Fit and analyze:
   - GARCH(1,1)
   - AR(1)-GARCH(1,1)
   - EGARCH(1,1)
   - TGARCH(1,1)
   - APARCH(1,1)
   - CGARCH(1,1) [custom implementation]
   - ACGARCH(1,1) [custom implementation]
4. Visualize conditional volatility per model
5. Compare AIC/BIC for model selection

## Output Interpretation

- **Conditional Volatility Plot**: Captures periods of volatility clustering
- **Model Summary**: Coefficients, significance, diagnostics
- **AIC/BIC Scores**: Used to evaluate model performance
- **ACF/PACF**: Guide lag selection for mean/volatility equations
- **Custom Models**: CGARCH and ACGARCH estimated using `scipy.optimize`

## Research Context

This project is based on econometric studies of cryptocurrency volatility, including:

- Bollerslev (1986) – GARCH model
- Nelson (1991) – EGARCH
- Glosten, Jagannathan, Runkle (1993) – TGARCH
- Ding and Granger (1996) – ACGARCH
- Engle and Lee (1999) – CGARCH
- Katsiampa (2017) – *Volatility Estimation for Bitcoin: A Comparison of GARCH Models*

## Contributing

Pull requests are welcome! You can contribute by:

- Adding forecasting & backtesting for out-of-sample performance
- Extending to other assets (ETH, equities)
- Converting models into reusable classes/modules
- Adding interactive dashboards

---

Let me know if you'd like this README saved into a file or paired with an auto-generated `requirements.txt`.
