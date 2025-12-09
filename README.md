# Simple Stock Trend Backtester

A Python-based algorithmic trading simulation tool. This script fetches historical stock data, applies a **Simple Moving Average (SMA)** crossover strategy, and calculates potential profits based on a user-defined initial deposit.

## 📋 Features

* **Real-time Data Fetching:** Uses `yfinance` to retrieve the last 1 year of historical data for major tech stocks (AAPL, TSLA, GOOGL, MSFT, AMZN).
* **Algorithmic Strategy:** Implements a classic SMA Crossover strategy (Short-term vs. Long-term trends).
* **Backtesting Simulation:** Simulates buying and selling based on historical signals to determine the performance of the strategy.
* **Profit Calculation:** specific logic to track portfolio balance from the initial deposit to the final valuation.

## 🛠️ Prerequisites

To run this project, you need Python installed along with the following libraries:

* `pandas` (Data manipulation)
* `yfinance` (Stock market data)

## 📦 Installation

1.  **Clone the repository** (or download the script):
    ```bash
    git clone https://github.com/tmaksymovych/simple-trading-algorith
    ```

2.  **Install the required packages:**
    ```bash
    pip install yfinance pandas
    ```

## 🚀 Usage

1.  Run the script in your terminal:
    ```bash
    python main.py
    ```

2.  **Select a Stock:** When prompted, type the ticker symbol of the stock you want to analyze (e.g., `AAPL` or `TSLA`).
3.  **Enter Deposit:** Input the amount of money ($) you wish to simulate investing.
4.  **View Results:** The script will output your initial balance, final balance, and total profit/loss.

## 📈 The Strategy Explained

This bot uses a **Moving Average Crossover** strategy to determine entry and exit points:

1.  **Short Window (5 days):** Reacts quickly to price changes.
2.  **Long Window (20 days):** Identifies the broader trend.

### Signals
* **BUY Signal (Golden Cross):** When the *Short MA* crosses **above** the *Long MA*. This indicates upward momentum.
* **SELL Signal (Death Cross):** When the *Short MA* crosses **below** the *Long MA*. This indicates downward momentum.
* **Execution:** The bot simulates a trade at the **Open price** of the *next day* following a signal.

## 🔮 Future Improvements

Here are a few ideas to expand this project:
* **Visualizations:** Add `matplotlib` or `plotly` to graph the stock price and draw the Buy/Sell markers.
* **Database Integration:** Save trade history to a generic SQL database for long-term analysis.
* **Extended Metrics:** Calculate Sharpe Ratio or Max Drawdown.

## ⚠️ Disclaimer

This software is for **educational purposes only**. It attempts to simulate a trading strategy using historical data. Past performance is not indicative of future results. Do not use this strictly for financial advice or real-world trading without further validation.
