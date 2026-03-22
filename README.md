# Macro-Data-Dashboard 

A library designed to monitor multi-asset data.
This project serves as the data backbone for developing systematic macro strategies and maintaining real-time market awareness.

---

## Project Objectives
* **Automated Data Pipeline:** Build a robust library of data across major asset classes.
* **Strategy Research:** Generate cleaned datasets optimized for backtesting.
* **Market Intelligence:** Monitor real-time shifts in macro regimes through automated data refreshes and key performance indicators.

---

## Asset Class Coverage & Implementation

| Asset Class | Status | Proxy / Instruments | Data Source |
| :--- | :--- | :--- | :--- |
| **Central Bank Policy** | Live | Fed Funds Rate, Dot Plots, Yield Curves | FRED / St. Louis Fed |
| **Fixed Income** | Live | Treasury Yields (2Y, 10Y, 30Y), HY/IG Spreads | yfinance / FRED |
| **Equity** | Live | Sector ETFs (XLK, XLE), Volatility (VIX), Factors | yfinance |
| **Commodities (TBD)** | *In Dev* | Gold (GLD), Crude Oil (CL=F), Agriculture | yfinance / Quandl |
| **FX (TBD)** | *In Dev* | G10 Pairs, Dollar Index (DXY) | yfinance |


---

## Data Engineering Workflow
The repository is structured to separate raw ingestion from signal-ready data:

1.  **Extraction:** Leverages `yfinance` for equity/ETF price action and `FRED` for macroeconomic fundamentals (CPI, Unemployment, Yield Curve).
2.  **Processing:** * Handling of missing values and outliers.
    * Alignment of disparate time-series frequencies (e.g., Daily Equity vs. Monthly Macro).
    * Calculation of derived metrics (e.g., Z-scores, rolling correlations, and term-premia).
    * Listing necessary data points and create functions to plot them to keep up with the market
3.  **Storage:** Processed datasets are stored in the `/Data` directory in parquet or CSV format for high-speed retrieval.

---


## Technical Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, SciPy
* **APIs:** Federal Reserve Economic Data (FRED), Yahoo Finance

---