# Macro, Volatility, and Stock Data Compiler

## Overview

This project fetches and compiles macroeconomic indicators, the stock market volatility index (VIX), and individual stock prices into a unified dataset. It enables data-driven analysis and modeling for forecasting or econometric research.

## Features

* Downloads GDP, unemployment rate, exchange rate, and federal funds rate from FRED
* Fetches VIX (Volatility Index) from Yahoo Finance
* Retrieves historical closing prices of specified stock tickers
* Merges all data sources on date
* Cleans dataset by forward-filling critical missing macro values and dropping rows with any remaining nulls
* Saves final merged dataset to CSV for further use in predictive models or financial analysis

## Prerequisites

* Python 3.8+
* pandas
* yfinance
* pandas\_datareader

## Installation

Clone this repository and navigate into it:

```bash
git clone https://github.com/youruser/macro-stock-data-compiler.git
cd macro-stock-data-compiler
```

Install required Python libraries:

```bash
pip install pandas yfinance pandas_datareader
```

## Project Structure

```
macro-stock-data-compiler/
├── macro_stock_compiler.py     # Main script to fetch and compile data
├── requirements.txt            # Required Python libraries
├── export/                     # Output directory for combined data files
│   └── AAPL_combined.csv       # Example of exported stock + macro + VIX dataset
└── README.md                   # This documentation
```

## Configuration

| Constant     | Description                                   | Default                                           |
| ------------ | --------------------------------------------- | ------------------------------------------------- |
| START\_DATE  | Start date for all data pulls                 | `1990-01-01`                                      |
| END\_DATE    | End date for all data pulls                   | `2022-01-01`                                      |
| EXPORT\_PATH | Directory path to save the final compiled CSV | `/home/student/suahmad/Richter_Final/Main_files/` |

## Usage

Ensure your environment is configured and then run:

```python
from macro_stock_compiler import save_data_for_ticker
save_data_for_ticker('AAPL')  # Replace 'AAPL' with any valid stock ticker
```

The script will:

1. Fetch macroeconomic, VIX, and stock data
2. Merge and clean it
3. Export a CSV to your defined EXPORT\_PATH

## Output

Each generated file will be named:

```
<TICKER>_combined.csv
```

Each CSV includes:

* **DATE**
* **GDP**
* **Unemployment\_Rate**
* **Exchange\_Rate** (USD to Euro)
* **Federal\_Funds\_Rate**
* **VIX**
* **Close\_Price**

### Example

```python
save_data_for_ticker('MSFT')
# Output file:
# /home/student/suahmad/Richter_Final/Main_files/MSFT_combined.csv
```

## Output Interpretation

This dataset is ideal for:

* Time series forecasting (e.g., LSTM, SARIMAX)
* Regression modeling with macroeconomic exogenous variables
* Volatility and price movement analysis

## Contributing

Contributions welcome! Submit pull requests to enhance features, support new indicators, or improve data handling.
