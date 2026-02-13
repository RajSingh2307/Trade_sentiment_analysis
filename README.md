## Trader Performance vs Market Sentiment Analysis

## Objective --

This project analyzes how Bitcoin market sentiment (Fear vs Greed) relates to trader behavior and performance on Hyperliquid. The goal is to uncover behavioral patterns and derive actionable strategy insights.

Datasets --

Bitcoin Fear & Greed Index

Columns: Date, Classification

Daily sentiment label (Fear / Greed / Extreme variants)

Hyperliquid Historical Trader Data

Includes: account, execution price, size, side, timestamp, closed PnL, etc.

Both datasets were aligned at daily level using timestamp conversion and date normalization.

## Methodology--

1. Data Preparation

Converted timestamps to datetime format

Created daily date column

Merged trader data with sentiment data

Verified overlapping date ranges

Checked missing values and alignment correctness

2. Feature Engineering

Daily account-level metrics were created:

Daily PnL

Win rate

Trade frequency

Average trade size (USD)

Long/Short activity

3. Sentiment-Based Analysis

Compared Fear vs Greed regimes using:

Mean & median daily PnL

Win rate

Trade frequency

PnL volatility

4. Trader Segmentation

Accounts were segmented into:

Frequent vs Infrequent traders

Consistent Winners vs Others

Performance was analyzed across sentiment regimes.

5. Predictive Modeling (Bonus)

Built a Logistic Regression model to predict next-day profitability using:

Sentiment

Trade count

Win rate

Average trade size

## Model accuracy: 61% (above random baseline).

## Key Insights

Traders become more aggressive during Fear (higher trade count and position size), but win rate remains stable — suggesting volatility-driven behavior rather than improved accuracy.

Frequent traders outperform during Fear periods, while infrequent traders sometimes perform better during Greed.

Win rate alone does not guarantee higher profitability — trade frequency and risk exposure play a stronger role.

Behavioral features (trade count, win rate) have stronger predictive power than sentiment alone.

## Strategy Recommendations

Volatility-Adaptive Activity
Increase trading activity selectively during Fear periods for historically consistent accounts.

Behavior-Driven Risk Allocation
Use trade frequency and win rate as capital allocation signals rather than relying solely on sentiment indicators.

## How to Run --

Install dependencies:

pip install -r requirements.txt

Open and run:

notebooks/trader_sentiment_analysis.ipynb