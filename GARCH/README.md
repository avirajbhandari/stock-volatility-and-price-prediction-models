Bitcoin Volatility Analysis Using GARCH Family Models
Overview
This project analyzes the volatility of Bitcoin (BTC-USD) returns using advanced time series models. It includes stationarity testing, visualization of log returns, and fitting multiple GARCH-family models to understand volatility clustering and dynamic risk. The project is built around academic econometrics concepts and supports model comparison via AIC/BIC.

Features
Downloads daily Bitcoin prices from Yahoo Finance (yfinance)

Computes and visualizes log returns

Performs stationarity tests (ADF, KPSS)

Tests for ARCH effects (Engle's ARCH test)

Fits multiple GARCH-family models including:

GARCH (symmetric)

EGARCH (asymmetric)

TGARCH (threshold)

Visualizes conditional variance over time

Compares model fit using log-likelihood, AIC, and BIC

Prerequisites
Python 3.8+

yfinance

pandas

numpy

matplotlib

scipy

statsmodels

arch

Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/yourusername/bitcoin-volatility-garch.git
cd bitcoin-volatility-garch
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Project Structure
bash
Copy
Edit
bitcoin-volatility-garch/
├── GARCH_bitcoin_new_.ipynb     # Main notebook for data analysis and modeling
├── bitcoin_log_returns_2018_2022.csv  # Exported log return data
├── requirements.txt             # Python dependencies
└── README.md                    # Project documentation
Usage
Open the notebook:

bash
Copy
Edit
jupyter notebook GARCH_bitcoin_new_.ipynb
Run cells sequentially to:

Fetch Bitcoin data from Yahoo Finance

Compute log returns

Visualize trends and returns

Run statistical tests for stationarity and heteroskedasticity

Fit and compare multiple GARCH-family models

Plot conditional volatility estimates

Output Interpretation
Log Return Plot: Visualizes daily return fluctuations

ADF/KPSS Tests: Confirm data stationarity

ARCH Test: Validates presence of volatility clustering

Model Outputs: Includes estimated parameters and statistical significance

Volatility Plot: Shows how risk evolves over time

Model Ranking: Based on AIC/BIC for best fit comparison

Research Context
This work supports an undergraduate econometrics capstone project replicating and extending findings from:

Katsiampa (2017): Volatility Estimation for Bitcoin: A Comparison of GARCH Models

Gyamerah (2019): Modeling the Volatility of Bitcoin Returns Using GARCH Models

Contributing
Contributions are welcome! Feel free to open issues or pull requests for new models, features, or documentation improvements.
