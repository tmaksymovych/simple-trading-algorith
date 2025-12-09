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

1. **Short Window:** 5-day Moving Average (Faster line).
2. **Long Window:** 20-day Moving Average (Slower line).

The Simple Moving Average (SMA) is calculated as the arithmetic mean of the closing prices over a specific number of days. The mathematical formula used is:

$$SMA = \frac{A_1 + A_2 + ... + A_n}{n}$$

Where:
* **A** = closing price at a specific period
* **n** = number of days in the window (e.g., 5 or 20)

### Trading Logic and Visualization

Below is a visual representation of the strategy implemented in this bot. It shows how the intersection of the short-term line (e.g., Blue) and long-term line (e.g., Red) generates signals.

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/c9b48650-da63-46bb-b418-42bad8d88509" />


The bot follows these rules based on the crossover points shown in the chart above:

- **Buy Signal (Golden Cross):**
  Occurs when the **Short** term average crosses **ABOVE** the Long term average. This indicates upward momentum. The bot converts all available cash into stock.

- **Sell Signal (Death Cross):**
  Occurs when the **Short** term average crosses **BELOW** the Long term average. This indicates downward momentum. The bot sells all held stocks and converts them back to cash.

- **Hold:**
  If no crossover occurs compared to the previous day, the position remains unchanged.

## Disclaimer

This software is for educational purposes only. It does not constitute financial advice. The backtesting results rely on historical data, which is not a guarantee of future performance.
