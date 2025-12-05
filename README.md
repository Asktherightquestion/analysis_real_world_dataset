# analysis_real_world_dataset
Real-World Dataset Github assignment

📊 Digital Gold vs. Big Tech: A Quantitative Volatility & ML Analysis

📌 Executive Summary
This project analyzes the 5-year historical relationship between Bitcoin (BTC) and the Nasdaq-100 (QQQ) to determine if crypto assets are merely a "high-beta" proxy for tech stocks or a distinct asset class. Using Python, I developed a pipeline that evaluates risk-adjusted returns, backtests a trend-following algorithm, and implements a Machine Learning model to predict daily price direction.

🔍 detailed Analysis & Findings
1. Market Correlation & Volatility
The analysis begins by visualizing the price action of Bitcoin against the Tech sector (QQQ) using interactive plots.

The "Risk-On" Correlation: The data reveal that Bitcoin and Tech stocks share a strong positive correlation, particularly during macroeconomic liquidity events.

Volatility Disparity: While the directional trends are similar, Bitcoin exhibits significantly higher volatility. The analysis quantifies this using the Sharpe Ratio (calculated in the notebook), which measures return per unit of risk.

Interpretation: A Sharpe Ratio > 1.0 indicates that Bitcoin's aggressive returns have historically compensated for its crashes. A ratio < 1.0 suggests the risk was "inefficient" compared to the safer Tech index.

2. Algorithmic Trading Performance (The "Golden Cross")
I backtested a classic technical strategy—buying when the 50-Day Moving Average crosses above the 200-Day Moving Average—against a standard "Buy & Hold" approach.

Strategy Logic: The Golden Cross is designed to capture major macro-trends while exiting the market during prolonged bear phases (preventing massive drawdowns).

Backtest Results:

Protection: The algorithm successfully avoided the deepest parts of bear market crashes by triggering a "Sell" signal as the trend broke.

Whipsaw Cost: In sideways or "choppy" markets, the strategy often underperformed "Buy & Hold" due to false signals (buying high and selling low repeatedly).

Conclusion: For a hyper-growth asset like Bitcoin, the Buy & Hold strategy generally yielded higher total cumulative returns over the 5-year period, though with significantly higher mental stress and drawdown depth.

3. Machine Learning Prediction (Random Forest)
A Random Forest Classifier was trained to predict whether Bitcoin's price would close Higher or Lower the next day.

Methodology: The model was trained on technical features, including:

Lagged Returns (1-day and 2-day prior performance)

30-Day Volatility (Rolling Standard Deviation)

Momentum (Price vs. 10 days ago)

Key Findings:

Feature Importance: The model identified Volatility and Momentum as the strongest predictors of future price direction, confirming that crypto markets are heavily driven by trend-persistence and fear/greed cycles rather than fundamental valuation.

Predictive Power: The model achieved an accuracy score that highlights the difficulty of predicting daily noise (Random Walk Hypothesis), suggesting that while ML can identify regimes, predicting specific daily candles remains statistically challenging.

🛠 Technologies Used
Data Processing: Pandas, NumPy, yfinance (ETL Pipeline)

Visualization: Plotly (Interactive Time-Series), Matplotlib, Seaborn

Machine Learning: Scikit-Learn (Random Forest Classifier, Train-Test Splitting)

Financial Math: Vectorized calculation of Sharpe Ratios, SMA Crossovers, and Cumulative Returns.
