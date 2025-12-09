# SMA Stock Trading Simulator

A Python-based command-line tool that simulates a stock trading strategy using historical data. This project uses the Simple Moving Average (SMA) crossover strategy to backtest how an initial deposit would have performed over the last year on major tech stocks.

## Features

- **Real-time Data Fetching:** Uses the `yfinance` library to retrieve the last 1 year of daily stock data.
- **Curated Stock List:** Supports analysis for major tech giants: AAPL, TSLA, GOOGL, MSFT, and AMZN.
- **Automated Strategy:** Logic implementation of the Golden Cross/Death Cross strategy.
- **Backtesting Engine:** Simulates buying and selling based on signals and calculates final profit/loss.

## Prerequisites

To run this project, you need Python installed along with the following libraries:

- pandas (Data manipulation)
- yfinance (Stock market data)

### Installation

Run the following command in your terminal to install the dependencies:

pip install pandas yfinance

## How to Use

1. **Run the script:**
   python your_script_name.py

2. **Select a Stock:**
   When prompted, type one of the available tickers (e.g., AAPL, TSLA). The program validates your input.

3. **Enter Deposit:**
   Input the amount of money (USD) you wish to simulate investing (e.g., 1000).

4. **View Results:**
   The script will output your initial balance, final balance after one year of algorithmic trading, and total profit.

## The Strategy: Moving Average Crossover

This bot utilizes a momentum strategy based on two rolling averages:

1. **Short Window:** 5-day Moving Average.
2. **Long Window:** 20-day Moving Average.

The Simple Moving Average (SMA) is calculated as the average of the closing prices over a specific number of days.

### Trading Logic

- **Buy Signal (Golden Cross):**
  Occurs when the Short term average (5 days) crosses ABOVE the Long term average (20 days). This indicates upward momentum. The bot converts all cash into stock.

- **Sell Signal (Death Cross):**
  Occurs when the Short term average (5 days) crosses BELOW the Long term average (20 days). This indicates downward momentum. The bot sells all stocks and converts back to cash.

- **Hold:**
  If no crossover occurs, the position remains unchanged.

## Disclaimer

This software is for educational purposes only. It does not constitute financial advice. The backtesting results rely on historical data, which is not a guarantee of future performance.
