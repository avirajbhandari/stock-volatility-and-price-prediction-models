# Stock-Price-Prediction
A team of three and I are developing stock price prediction models using GAARCH, Neural Networks, and Fourier Transform. This ongoing project currently features a dynamic Data Frame generator for any ticker symbol. We're also exploring new models like LSTM currently. 

# Stock Price Prediction Models: GAARCH, Neural Networks, and Fourier Transform

### Contributors:
- Abhyudaya Rajbhandari - Quantitative Researcher
- Arun Rajbhandari - Data Analyst
- Subhan Ahmad - Machine Learning Specialist
- Andrew Leahy - Project Manager

## Abstract:
This project aims to predict stock prices using advanced forecasting models such as GAARCH, Neural Networks, Fourier Transform, and LSTM. The current focus is on developing a dynamic DataFrame generator that processes data for any given stock ticker symbol, creating a versatile tool for stock market analysis. The project is ongoing, and we are exploring new techniques and improving model accuracy.

## Purpose:
The main objective of this project is to create an adaptable stock price prediction system that can incorporate multiple models, including GAARCH, Neural Networks, Fourier Transform, and LSTM, to provide accurate forecasting across different stock tickers.

## Technical Details:
### Methods:
The project leverages various forecasting models and machine-learning techniques:
- **GAARCH (Generalized Autoregressive Conditional Heteroskedasticity):** Used for modeling volatility and predicting stock price variability.
- **Neural Networks:** A deep learning approach applied to predict stock price movements based on historical data.
- **Fourier Transform:** Utilized to analyze and decompose stock price data for better feature extraction and forecasting.
- **LSTM (Long Short-Term Memory):** A specialized Recurrent Neural Network (RNN) designed for time series prediction, currently under exploration for improving model performance.

### Tools & Technologies:
- **Python:** Core programming language for data processing, model development, and prediction.
- **Pandas:** For handling and manipulating data.
- **TensorFlow/Keras:** For building and training Neural Networks and LSTM models.
- **Arch (for GAARCH modeling):** Python library to implement GAARCH models.
- **NumPy and SciPy:** For mathematical and statistical computations.
- **Matplotlib/Seaborn:** For data visualization.

### Data Sources:
- **Yahoo Finance API:** Used for collecting historical stock price data.
- **FRED:** Used for economic and financial data relevant to stock price predictions.

## Features:
- **Dynamic DataFrame Generator:** Automatically collects and processes data for any given ticker symbol, allowing for easy experimentation with different stocks.
- **Multiple Prediction Models:** The project currently supports GAARCH, Neural Networks, and Fourier Transform, with LSTM being explored for future model improvement.

## Results and Progress:
As of now, the team has developed the core DataFrame generator and is experimenting with various forecasting models. Preliminary tests show promising results for volatility prediction with GAARCH, and Neural Networks are being fine-tuned for more accurate price movement predictions.

## Installation:

### Prerequisites:
Make sure you have the following Python libraries installed:
- pandas
- numpy
- tensorflow
- keras
- arch
- yfinance
- matplotlib
- scipy

### Setup Instructions:
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/yourusername/stock-price-prediction.git

2. Navigate to the project directory
    ```bash
     cd stock-price-prediction
    
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt

  ## **Repository Structure**
```plaintext
├── data/                  # Raw and processed datasets
├── models/                 # Scripts for different prediction models
│   ├── gaarch_model.py     # GAARCH model for volatility prediction
│   ├── neural_network_model.py  # Neural Network model
│   └── lstm_model.py      # LSTM model (under development)
├── data_frame_generator.py # Script to generate dynamic data frame for any ticker
├── results/               # Generated results and plots
├── visuals/               # Visualizations (charts and graphs)
├── README.md              # Project documentation
├── requirements.txt       # Python dependencies
└── LICENSE                # Project license (MIT)
```
---

## **License**
This research and its associated code are made available under the MIT License. Feel free to use, modify, and share, provided proper attribution is given.

## **Acknowledgments**
Special thanks to Professor Leahy for his steadfast guidance and invaluable insights throughout this project. Additionally, we draw inspiration from the wealth of financial forecasting models and research that has shaped our approach

## Contact
-----------
For questions or collaboration, please reach out at:  
**Email**: avi.rajbhandari.joshi@gmail.com  
**Email**: rajbhandariabhyudaya@gmail.com



