# Pairs Trading Strategy — US Financial Sector (2016–2025)

# Overview
This project implements a statistical arbitrage (pairs trading) strategy on six large-cap US bank stocks: JPM, GS, MS, C, BAC, and WFC using daily price data from 2016 to 2025.

# Key Results
Metric 
- Best Pair: Citigroup (C) & Bank of America (BAC) 
- ADF p-value: 0.0012
- Half-life of Mean Reversion: 6.4 trading days
- Optimal Threshold (z score): 1.5
- Cumulative Return (2017–2025): 95.36%
- Sharpe Ratio: 0.4664
- Max Drawdown: -37.28%
- Number of Trades: 25

# Methodology
1. **Data**: Bloomberg Terminal daily close prices (2016–2025)
2. **Pair Selection**: Correlation matrix → OLS regression → ADF cointegration test
3. **Half-life Analysis**: Ornstein-Uhlenbeck model to quantify mean reversion speed
4. **Rolling Re-estimation**: 6-month rolling windows to avoid look-ahead bias
5. **Z-Score Strategy**: Enter at z* = ±1.5, exit at z = 0
6. **Threshold Sensitivity**: Tested z* = 1.5, 2.0, 2.5, 3.0
7. **Transaction Costs**: Verified robustness at 0.05% per trade

# Files
- `pairs_trading_financial_sector.ipynb` — Main notebook with full analysis
- `AI_project_financials.csv` — Raw price data for all 6 stocks

# Libraries Used
- pandas, numpy, matplotlib, seaborn
- statsmodels (OLS, ADF test, OU model)
- scipy

# What's Next
The low trading frequency (~3 trades/year) of this daily strategy motivates 
a transition toward high-frequency trading, where alpha opportunities are 
more abundant at the intraday and tick level.

# Requirements
```
pip install pandas numpy matplotlib seaborn statsmodels scipy
```
