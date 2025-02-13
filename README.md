# Binance Trade Data Analysis

This project provides a detailed analysis of trade data, including ROI (Return on Investment), Sharpe Ratio, Maximum Drawdown (MDD), and other trading performance metrics. It processes trade data from a CSV file, extracts trade details, and calculates key performance indicators for trading portfolios.

---

### Dataset Information
The dataset contains the following:
- **Port_IDs**: Unique identifiers for accounts.
- **Trade_History**: A nested column detailing trades with:
  - **timestamp**: Time of the trade.
  - **asset**: Asset being traded.
  - **side**: BUY or SELL.
  - **price**: Trade price.
  - **quantity**: Money involved in the trade.
  - **realizedProfit**: Profit or loss from the trade.

---

### Objective
The goal is to calculate key metrics for each account, rank them, and identify the top 20 performing accounts based on a composite score.

---

### Metrics to Calculate
1. **ROI (Return on Investment)**: Measures account profitability.
2. **PnL (Profit and Loss)**: Total profit or loss for the account.
3. **Sharpe Ratio**: Risk-adjusted return metric.
4. **MDD (Maximum Drawdown)**: Largest drop from peak portfolio value.
5. **Win Rate**: Percentage of profitable trades.
6. **Win Positions**: Total number of trades with profit.
7. **Total Positions**: Total number of trades.

---

### Steps to Complete
1. **Data Exploration and Cleaning**
   - Load the dataset.
   - Inspect for missing or invalid values.
   - Clean and preprocess the data.

2. **Feature Engineering**
   - Parse nested `Trade_History` for detailed trade information.
   - Create features like `win_positions` and classify positions using:
     - **Side** and **PositionSide** for trade type.
     - Calculate realized profit/loss.

3. **Metrics Calculation**
   - Compute the metrics listed above for each account.

4. **Ranking Algorithm**
   - Normalize the metrics to standardize values.
   - Assign weights to metrics to create a composite score.
   - Rank accounts based on the composite score.

---

### Additional Notes
- **Win Positions**: The number of trades with positive realized profit.
- **Position Identification**:
  - Combine `side` and `positionSide` to classify trades (e.g., long_open, long_close).
  - `quantity`: Money in the trade.
  - `qty`: Coin amount traded.
  - `realizedProfit`: Indicates trade profitability.

This task requires thorough data analysis and a ranking mechanism to identify top-performing accounts.
