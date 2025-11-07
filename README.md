# Trading Sentiment Analysis

This project analyzes trader performance and behavior across different market sentiments using real trading data.

## Overview
The notebook explores:
- Distribution of trader PnL across sentiments
- Average PnL by sentiment
- Trader activity patterns (long vs short bias)
- Correlation between sentiment and trading direction

## Files
- `notebook/sentiment_analysis.ipynb` → main Jupyter notebook
- `data/raw/fear_greed_index.csv` → dataset used
- `data/raw/historical_data.csv` → dataset used

## Results and Analysis

This analysis explores the relationship between trader performance, market sentiment (using the Fear-Greed Index), and the factors that predict profitability.

### 1. Exploratory Data Analysis (EDA)

The first four charts dig into the behaviors and outcomes of traders based on the prevailing market sentiment.

#### Graph 1: Distribution of Fear-Greed Scores
<img width="699" height="396" alt="image" src="https://github.com/user-attachments/assets/2b3c4e6c-f6fc-4880-bcb9-4206042be161" />

> **Insight:** The market's mood isn't a simple 50/50 split. There's a massive, dominant spike in the 'Greed' territory (around the 75-point mark), which is far larger than the smaller clusters in the 'Fear' zone. This suggests the market spends a substantial amount of its time in a 'Greed' state.

#### Graph 2: Average Trader PnL by Market Sentiment
<img width="699" height="473" alt="image" src="https://github.com/user-attachments/assets/b9017690-7c23-42f6-9091-2d150b632c57" />

> **Insight:** Profitability (PnL) is highest during 'Extreme Greed' and lowest during 'Extreme Fear.' Interestingly, the relationship isn't a perfect climb; PnL during 'Fear' is slightly *lower* than during 'Neutral' periods. The most significant profit jumps occur at the absolute extremes of sentiment.

#### Graph 3: Average Trader Win Rate by Market Sentiment
<img width="703" height="473" alt="image" src="https://github.com/user-attachments/assets/79e118e5-c9c6-4026-a0f7-f8c8224ae8f4" />


> **Insight:** Win rate doesn't perfectly mirror profitability. While 'Extreme Greed' has the highest win rate (around 38%) and 'Extreme Fear' the lowest (around 33%), the other three categories ('Fear,' 'Greed,' and 'Neutral') are all tightly clustered together in the middle.

#### Graph 4: Trade Direction Preference across Sentiments
<img width="699" height="562" alt="image" src="https://github.com/user-attachments/assets/1dc3fa42-35aa-49ca-9d71-c57a462d45d1" />


> **Insight:** This is the most surprising finding. The data shows that 'Short' positions (yellow bar) are dominant in *every single sentiment category*. This specific group of traders has an overwhelming and persistent bearish bias, shorting the market even during 'Extreme Greed.'

---

### 2. Machine Learning Model Results

A model was trained to predict profitability based on these and other factors.

#### Model Summary
* **Accuracy:** 96%

#### Feature Importance
1.  **Win rate:** (0.89 importance)
2.  **Avg trade size:** (0.07 importance)
3.  **Sentiment score:** (0.03 importance)

#### Interpretation
What this tells us is that **'Win rate' is by far the most important factor** in predicting profitability. The other features, 'Average trade size' and 'Sentiment score,' are basically just footnotes by comparison.

That said, the fact that 'Sentiment score' is in the top three at all (even at a tiny 0.03) is interesting. It means that while winning or losing is what *really* matters, the market's overall emotional state still has a small, subtle influence on the outcome.
