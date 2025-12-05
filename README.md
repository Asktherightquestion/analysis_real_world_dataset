# analysis_real_world_dataset
Real-World Dataset Github assignment

# 📊 Digital Gold vs. Big Tech: A Quantitative Volatility & ML Analysis

## 📌 Executive Summary
This project applies quantitative finance and machine learning techniques to analyze the relationship between **Bitcoin (BTC)** and the **Nasdaq-100 (QQQ)** over a 5-year period. By evaluating risk-adjusted returns and backtesting a Random Forest Classifier, this analysis aims to determine if Bitcoin's daily price movements can be predicted using technical momentum and volatility indicators.

## 🔍 Detailed Analysis & Findings

### 1. Market Correlation & Volatility (Visual Analysis)
The interactive visualization reveals distinct "Risk-On" behavior:
* **Correlation:** Bitcoin acts as a "high-beta" proxy for the Tech sector. It tracks the directional macro-trends of the Nasdaq-100 (e.g., the 2022 downturn and 2023 recovery) but amplifies the moves.
* **Volatility Disparity:** While the trends are similar, Bitcoin's rolling volatility (standard deviation) is consistently 2-3x higher than the Nasdaq. This confirms that while the assets are correlated, the "cost" of holding Bitcoin is significantly higher variance.

### 2. Machine Learning Performance (Random Forest)
A Random Forest Classifier was trained to predict daily price direction (**Up** vs. **Down**) based on Lagged Returns, Momentum, and Volatility.

* **Model Accuracy:** **48.6%** (Test Set)
* **Classification Insight: The "Random Walk" Theory**
    The model's performance (~49%) is statistically equivalent to a random guess. This supports the **Efficient Market Hypothesis (EMH)** for the short term, suggesting that:
    1.  **Noise vs. Signal:** At a daily timeframe, Bitcoin's price action is dominated by stochastic noise rather than predictable technical patterns.
    2.  **Feature Insufficiency:** Basic technical indicators (like `Momentum` and `30-Day Volatility`) do not contain enough signal to predict daily candles for an asset as liquid as Bitcoin.

### 3. Feature Importance
Despite the low predictive accuracy, the model identified **30-Day Volatility** as the most significant feature. This indicates that while the *direction* of Bitcoin is hard to predict, the *magnitude* of its moves is its most distinct statistical property.

### 4. Risk-Adjusted Returns (Sharpe Ratio)
* **Analysis:** The Sharpe Ratio calculation helps quantify if Bitcoin's returns justify its risk.
    * *Observation:* Historically, Bitcoin's massive upside periods have compensated for its extreme drawdowns, often resulting in a Sharpe Ratio > 1.0 (considered "Good"). However, during bear markets, this ratio compresses significantly, highlighting the inefficiency of the asset during low-liquidity cycles.

### 5. Algorithmic Trading Strategy (The "Golden Cross")
I backtested a trend-following strategy (Buying when the 50-Day SMA crosses above the 200-Day SMA).
* **Verdict:** The strategy successfully protected capital during major crashes (by exiting the market), but suffered from "whipsaws" (false signals) during sideways markets. Over the 5-year period, a simple **Buy & Hold** strategy generally yielded higher total returns, proving that "time in the market" often beats "timing the market" for crypto assets.

## 🛠 Technologies Used
* **Data Pipeline:** `yfinance`, `Pandas`, `NumPy`
* **Visualization:** `Plotly` (Interactive), `Matplotlib`, `Seaborn`
* **Machine Learning:** `Scikit-Learn` (Random Forest, Train-Test Split)
* **Financial Metrics:** Sharpe Ratio, Rolling Volatility, Cumulative Returns
