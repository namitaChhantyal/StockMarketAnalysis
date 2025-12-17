## Algorithmic Trading Strategies & Backtesting Framework

---

## 1. Project Overview

This project was completed as part of the **Analytical Programming** course and focuses on the **design, implementation, and evaluation of algorithmic trading strategies** using historical stock market data.

The goal of this project is to:

- Implement multiple trading strategies using Python
- Backtest each strategy over a fixed historical period
- Compare strategy performance using financial metrics and visualizations
- Analyze strengths, weaknesses, and real-world applicability of each approach

All implementations and experiments are contained within a single Jupyter Notebook:

---

## 2. Objectives

- Apply analytical programming techniques to financial time-series data
- Simulate real-world trading constraints (capital limits, transaction costs)
- Evaluate algorithmic strategies under identical market conditions
- Develop clean, reproducible, and well-documented Python code

---

## 3. Data Description

### 3.1 Data Source

- **Yahoo Finance API** accessed via the `yfinance` Python library

### 3.2 Assets Analyzed

The project uses a diversified set of large-cap U.S. stocks:

| Ticker | Company        |
| ------ | -------------- |
| NVDA   | NVIDIA         |
| AAPL   | Apple          |
| TSLA   | Tesla          |
| NFLX   | Netflix        |
| META   | Meta Platforms |
| ADBE   | Adobe          |
| CRM    | Salesforce     |
| GOOGL  | Alphabet       |
| JPM    | JPMorgan Chase |
| AMZN   | Amazon         |

### 3.3 Time Period

- **Start Date:** January 1, 2015
- **End Date:** December 1, 2022

### 3.4 Data Features Used

- Adjusted Close Price
- Daily Returns
- Rolling Statistics (mean, standard deviation)
- Technical indicators (moving averages, Bollinger Bands)

---

## 4. Trading Assumptions

To simulate realistic trading conditions, the following assumptions were applied:

| Parameter        | Value                            |
| ---------------- | -------------------------------- |
| Initial Capital  | $10,000                          |
| Transaction Cost | 0.2% per trade                   |
| Slippage         | Included within transaction cost |
| Position Type    | Long-only                        |
| Rebalancing      | Strategy-specific                |
| Leverage         | None                             |

---

## 5. Trading Strategies Implemented

### 5.1 Momentum Strategy

- Buys assets that have demonstrated positive recent performance
- Assumes that price trends persist over short-to-medium horizons
- Portfolio is periodically rebalanced based on momentum signals

**Strength:** Performs well in trending markets
**Limitation:** Vulnerable during sideways or volatile markets

---

### 5.2 Trend Following Strategy (Moving Average Crossover)

- Uses short-term and long-term moving averages
- Buy signal when short MA crosses above long MA
- Sell signal when short MA crosses below long MA

**Strength:** Filters market noise and captures long trends
**Limitation:** Generates lagged signals and may miss reversals

---

### 5.3 Mean Reversion Strategy (Bollinger Bands)

- Assumes prices revert to their historical mean
- Buy when price drops below lower Bollinger Band
- Sell when price rises above upper Bollinger Band

**Strength:** Effective in range-bound markets
**Limitation:** Performs poorly in strong trending environments

---

### 5.4 Market Making Strategy (Simulated)

- Simulates capturing bid-ask spreads
- Assumes liquidity availability and continuous execution
- Simplified model without a real limit order book

**Strength:** Demonstrates microstructure-based strategy logic
**Limitation:** Highly simplified and not production-ready

---

## 6. Performance Evaluation

Each strategy is evaluated using:

- Portfolio value over time
- Total return
- Visual performance comparison
- Strategy-specific behavior across market regimes

Charts and tables are generated directly in the notebook using `matplotlib`.

---

## 7. Technologies & Tools

### Programming Language

- Python 3

### Libraries

- `yfinance` – Financial data retrieval
- `pandas` – Data manipulation
- `numpy` – Numerical computation
- `matplotlib` – Visualization
- `itertools` – Strategy combinations (built-in)

### Environment

- Jupyter Notebook

---

## 8. How to Run the Project Locally

### Step 1: Clone the Repository

git clone https://github.com/namitaChhantyal/StockMarketAnalysis.git


### Step 2: Create Virtual Environment (Recommended)

<pre class="overflow-visible! px-0!" data-start="4563" data-end="4594"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>python -m venv venv</span></span></code></div></div></pre>


Activate environment:

**Windows**

<pre class="overflow-visible! px-0!" data-start="4631" data-end="4664"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>venv\Scripts\activate
</span></span></code></div></div></pre>

**Mac/Linux**

<pre class="overflow-visible! px-0!" data-start="4680" data-end="4716"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>source</span><span> venv/bin/activate</span></span></code></div></div></pre>


### Step 3: Install Dependencies

<pre class="overflow-visible! px-0!" data-start="4751" data-end="4807"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>pip install yfinance pandas numpy matplotlib</span></span></code></div></div></pre>


### Step 4: Run Notebook

<pre class="overflow-visible! px-0!" data-start="4834" data-end="4862"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre! language-bash"><span><span>jupyter notebook</span></span></code></div></div></pre>


Open:

<pre class="overflow-visible! px-0!" data-start="4870" data-end="4907"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>StockAnalytics..ipynb</span></span></code></div></div></pre>


## 9. Project Structure

<pre class="overflow-visible! px-0!" data-start="4939" data-end="5040"><div class="contain-inline-size rounded-2xl corner-superellipse/1.1 relative bg-token-sidebar-surface-primary"><div class="@w-xl/main:top-9 sticky top-[calc(--spacing(9)+var(--header-height))]"><div class="absolute end-0 bottom-0 flex h-9 items-center pe-2"><div class="bg-token-bg-elevated-secondary text-token-text-secondary flex items-center gap-4 rounded-sm px-2 font-sans text-xs"></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="whitespace-pre!"><span><span>📦Final Project
 ┣ 📜 README.md
 ┣ 📓 StockAnalytics..ipynb</span></span></code></div></div></pre>


## 10. Key Takeaways

* No single trading strategy outperforms in all market conditions
* Strategy performance is highly sensitive to market regime
* Transaction costs significantly impact real-world profitability
* Backtesting assumptions must be clearly stated to avoid misleading conclusions

---

## 11. Limitations & Future Work

### Limitations

* No short selling
* Simplified execution model
* No risk-adjusted metrics (Sharpe, Sortino)

### Future Enhancements

* Add risk-adjusted performance metrics
* Implement portfolio optimization
* Introduce machine learning-based strategies
* Include real limit-order-book simulation

---

## 12. Team Members

**Team 10 – Young, Dumb & Broke**

* Saugat Sijapati
* **Namita Chhantyal**

---

## 13. Academic Disclaimer

This project was developed **solely for academic purposes** as part of graduate coursework. It does not constitute financial advice.

## 10. Key Takeaways

* No single trading strategy outperforms in all market conditions
* Strategy performance is highly sensitive to market regime
* Transaction costs significantly impact real-world profitability
* Backtesting assumptions must be clearly stated to avoid misleading conclusions

---

## 11. Limitations & Future Work

### Limitations

* No short selling
* Simplified execution model
* No risk-adjusted metrics (Sharpe, Sortino)

### Future Enhancements

* Add risk-adjusted performance metrics
* Implement portfolio optimization
* Introduce machine learning-based strategies
* Include real limit-order-book simulation

---

## 12. Team Members

**Team 10 – Young, Dumb & Broke**

* Saugat Sijapati
* **Namita Chhantyal**

---

## 13. Academic Disclaimer

This project was developed **solely for academic purposes** as part of graduate coursework. It does not constitute financial advice.
