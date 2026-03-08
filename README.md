# Trader Performance vs Market Sentiment Analysis

## Project Overview

This project analyzes the relationship between **Bitcoin market
sentiment (Fear vs Greed)** and **trader behavior on Hyperliquid**.\
The goal is to understand how sentiment influences trader performance,
risk-taking behavior, and trading activity.

The analysis combines: - Bitcoin Fear & Greed Index - Historical
Hyperliquid trader data

The results provide **data-driven insights and strategy
recommendations** for improving trading decisions.

------------------------------------------------------------------------

# Dataset Description

## 1. Bitcoin Market Sentiment Dataset

Contains daily sentiment classification.

Columns: - `date` - `classification` (Fear / Greed)

Represents the general **market psychology**.

------------------------------------------------------------------------

## 2. Historical Trader Dataset (Hyperliquid)

Key columns used in the analysis:

-   `Account` -- trader account ID
-   `Coin` -- traded asset
-   `Execution Price`
-   `Size Tokens`
-   `Size USD`
-   `Side`
-   `Direction` (Long / Short)
-   `Closed PnL`
-   `Fee`
-   `Trade ID`
-   `Timestamp IST`

This dataset contains **over 200k trades**.

------------------------------------------------------------------------

# Data Preparation

Steps performed:

1.  Loaded datasets using **Pandas**
2.  Checked dataset structure
    -   number of rows
    -   number of columns
3.  Identified:
    -   missing values
    -   duplicate rows
4.  Converted timestamps to datetime format
5.  Extracted **daily date**
6.  Merged datasets on date
7.  Created analytical features

Key engineered features:

-   `is_win` → profitable trade indicator
-   `risk_score` → trade risk exposure
-   `daily_pnl`
-   `win_rate`
-   `trade_frequency`
-   `long_short_ratio`

------------------------------------------------------------------------

# Exploratory Data Analysis

The following analyses were performed:

## Sentiment vs Performance

Analyzed differences in:

-   Trader PnL
-   Win rate
-   Trading activity

Visualization examples:

-   PnL distribution by sentiment
-   Trade frequency comparison
-   Position size comparison

------------------------------------------------------------------------

# Trader Behavioral Segmentation

Traders were segmented using behavioral metrics:

Features used:

-   Total PnL
-   Number of trades
-   Average position size
-   Win rate

K-Means clustering was used to identify **trader archetypes**.

Example clusters:

1.  Low Activity Traders
2.  Risky Traders
3.  High Performance Traders

This helps identify **different trading styles**.

------------------------------------------------------------------------

# Predictive Modeling (Bonus)

A **Random Forest classifier** was used to predict whether a trade will
be profitable.

Features used:

-   trade size
-   fee
-   sentiment

Target:

-   profitable trade (win / loss)

The model demonstrates how **trading behavior + sentiment can predict
outcomes**.

------------------------------------------------------------------------

# Key Insights

### Insight 1

Trading activity increases during **Greed sentiment**, indicating higher
trader confidence.

### Insight 2

Position sizes tend to be larger during **Greed periods**, suggesting
increased risk-taking.

### Insight 3

Frequent traders tend to achieve **higher win rates** compared to
infrequent traders.

------------------------------------------------------------------------

# Strategy Recommendations

## Strategy 1

Reduce trade size during **Fear sentiment** because market volatility
increases and performance becomes less stable.

## Strategy 2

Increase trading activity during **Greed sentiment** to capture strong
market momentum.

------------------------------------------------------------------------

# Optional Dashboard

A lightweight **Streamlit dashboard** can be used to explore:

-   PnL distributions
-   sentiment patterns
-   trader behavior

Run dashboard:

    streamlit run dashboard.py

------------------------------------------------------------------------

# Technologies Used

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   Scikit-learn
-   Streamlit

------------------------------------------------------------------------

# Project Structure

    trader-sentiment-analysis
    │
    ├── data
    │   ├── fear_greed_index.csv
    │   └── historical_data.csv
    │
    ├── analysis.ipynb
    ├── dashboard.py
    ├── README.md
    └── requirements.txt

------------------------------------------------------------------------

# Conclusion

This project demonstrates how **market sentiment impacts trader behavior
and profitability**.\
By combining sentiment signals with behavioral analytics, traders can
make **more informed and strategic decisions**.

Future improvements:

-   advanced predictive models
-   real-time sentiment signals
-   automated trading strategies
