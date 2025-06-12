# 📈 **LSTM MULTI-QUARTER STOCK PREDICTION PIPELINE**

## OVERVIEW

This project implements a pipeline to predict quarterly stock prices using an LSTM neural network model with exogenous macroeconomic variables. It evaluates prediction accuracy and compares an investment strategy based on top predicted movers against the S\&P 500.

## FEATURES

* Reads individual ticker CSVs with exogenous indicators and historical prices
* Resamples data to quarterly frequency and aligns on quarter-ends
* Scales features with `StandardScaler`
* Constructs an LSTM model with 10 previous quarters of data as input
* Forecasts the next quarter price and computes predicted vs. actual changes
* Ranks tickers by predicted change rate
* Compares investment returns of top N tickers vs. S\&P 500 for each quarter
* Summarizes overall directional prediction accuracy per ticker
* Optional bar chart visualization of returns

## PREREQUISITES

* Python 3.8+
* `pandas`
* `numpy`
* `matplotlib`
* `scikit-learn`
* `tensorflow` (includes Keras)

## INSTALLATION

Clone this repository:

```bash
git clone https://github.com/youruser/stock-lstm-pipeline.git
cd stock-lstm-pipeline
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## PROJECT STRUCTURE

```
stock-lstm-pipeline/
├── main.py                 # Entry-point script containing the pipeline
├── S&P500Data.csv          # Quarterly S&P500 closing prices
├── requirements.txt        # Python dependencies
├── export/                 # Directory containing <TICKER>_combined.csv files
│   └── AAPL_combined.csv   # Example ticker data with exogenous columns
└── README.md               # This documentation
```

## CONFIGURATION

In `main.py`, adjust the following constants to suit your environment and analysis:

| CONSTANT           | DESCRIPTION                                       | DEFAULT                                                  |
| ------------------ | ------------------------------------------------- | -------------------------------------------------------- |
| `EXPORT_PATH`      | Directory path for combined ticker CSV files      | `/home/jovyan/stock_data/`                               |
| `SNP_PATH`         | File path for S\&P500Data.csv                     | `S&P500Data.csv`                                         |
| `TARGET_COL`       | Column name for closing price in CSVs             | `Close_Price`                                            |
| `EXOG_VARS`        | List of exogenous column names                    | `['GDP','Unemployment_Rate','Federal_Funds_Rate','VIX']` |
| `N_PREV_QUARTERS`  | Number of past quarters to train on               | `10`                                                     |
| `NUM_DATES`        | Number of user-entered dates/quarters to evaluate | `4`                                                      |
| `TOP_N`            | Number of top tickers for investment comparison   | `5`                                                      |
| `INVEST_PER_STOCK` | Dollar amount to invest per ticker                | `10`                                                     |

## USAGE

Ensure your `export/` directory contains `<TICKER>_combined.csv` files, each with a `DATE` column, exogenous variables, and `Close_Price`.

Place `S&P500Data.csv` in the project root (must contain `DATE` and `Close_Price`).

Run the script:

```bash
python main.py
```

Enter each date in `YYYY-MM-DD` format when prompted. The script will output:

* Ranked prediction results for each quarter
* Investment comparison for top N tickers vs. S\&P 500
* Overall directional accuracy summary
* A bar chart comparing portfolio growth

## NON-INTERACTIVE INVOCATION

To bypass `input()` prompts, refactor `run_predictions_multiple_dates()` to accept a list of date strings:

```python
from main import run_predictions_multiple_dates

# Provide ISO date strings or datetime objects
dates = ['2021-01-01', '2020-01-01', '2019-01-01', '2018-01-01']
summary_df = run_predictions_multiple_dates(dates)
print(summary_df)
```

## OUTPUT INTERPRETATION

* **Predicted\_Change\_Rate vs Actual\_Change\_Rate**: Directional and magnitude accuracy
* **Investment Comparison**: Dollar value of `$TOP_N × INVEST_PER_STOCK` invested in top predicted tickers vs. same in S\&P 500
* **Accuracy Summary**: Fraction of correct direction predictions per ticker over all evaluated dates

## CONTRIBUTING

Contributions welcome! Please open issues or submit pull requests to improve functionality, add tests, or enhance documentation.
