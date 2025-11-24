LSTM Stock Price Predictor

📈 Project Overview

This project implements a stock price forecasting model using a Long Short-Term Memory (LSTM) Recurrent Neural Network (RNN). The model is trained on historical stock data and features calculated from technical indicators (Simple Moving Average, Relative Strength Index, and MACD) to predict the next day's closing price.

The workflow follows five core steps: Data Collection, Feature Engineering, Preprocessing, Model Training, Evaluation, and Visualization.

⚙️ Technology Stack

Language: Python

Data Handling: Pandas, NumPy

Data Source: yfinance (for historical stock data)

Technical Indicators: ta library

Modeling: TensorFlow / Keras (for LSTM architecture)

Visualization: Matplotlib

🚀 Getting Started

Prerequisites

You need Python installed. We recommend using a virtual environment.

Create a virtual environment (optional but recommended)
python -m venv venv

Activate the environment
Windows:
.\venv\Scripts\activate

macOS/Linux:
source venv/bin/activate

Installation

Install the necessary dependencies using pip:

pip install yfinance pandas numpy ta tensorflow keras matplotlib scikit-learn

Execution

The entire prediction pipeline is contained in a single script.

Run the script:

python stock_price_prediction.py

Review Output: The script will output the following metrics in the console:

Root Mean Squared Error (RMSE): Measures the average magnitude of the errors.

Directional Prediction Accuracy: Measures how often the model correctly predicted the up or down movement of the stock price.

Visualization: A plot will be displayed showing the Actual Price vs. Predicted Price for the test set.

📊 Methodology Highlights

Data Collection: Uses yfinance to download historical data for a specified ticker (default is AAPL).

Feature Engineering: Calculates 20-day SMA, 14-day RSI, and MACD components to enrich the input features.

Time Series Conversion: Data is scaled using MinMaxScaler and converted into sequences (lookback window of 60 days) to be suitable for LSTM training.

Model Architecture: A sequential Keras model with two LSTM layers and dropout regularization is used.

Evaluation: Metrics are calculated after inverse-transforming the normalized predictions back to the original USD price scale.

📝 Future Enhancements

Add Hyperparameter tuning using Keras Tuner or GridSearchCV.

Explore alternative RNN architectures (e.g., GRU).

Integrate fundamental data (e.g., P/E ratio, earnings reports) as additional features.

Implement a full trading strategy backtester using the prediction signals.
