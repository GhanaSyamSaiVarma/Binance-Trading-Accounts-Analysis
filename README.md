# Binance Trade ROI Analysis

This project provides a detailed analysis of trade data, including ROI (Return on Investment), Sharpe Ratio, Maximum Drawdown (MDD), and other trading performance metrics. It processes trade data from a CSV file, extracts trade details, and calculates key performance indicators for trading portfolios.

---

## Features

- Import and preprocess trade data from CSV files.
- Parse nested JSON-like trade histories.
- Extract key trade details (e.g., time, symbol, side, price, quantity).
- Calculate essential metrics:
  - ROI (Return on Investment)
  - Sharpe Ratio
  - Maximum Drawdown (MDD)
  - Win Rate
  - Profit and Loss (PnL)
  - Composite Score for ranking accounts
- Normalize metrics and rank top-performing portfolios.

---

## Workflow Overview

### 1. Importing the Dataset
The project starts by importing a CSV dataset of trade data.

```python
import pandas as pd
df = pd.read_csv('BINANCE_TRADES_ROI_DATA.csv', on_bad_lines='skip')

---

### 2. Data Preprocessing
The trade history is cleaned, and invalid rows are dropped. Nested JSON-like structures in the `Trade_History` column are parsed for further analysis.

```python
import ast

# Drop rows with missing 'Trade_History' values
df_clean = df.dropna(subset=['Trade_History'])

# Parse JSON-like strings in the 'Trade_History' column
df_clean['Trade_History'] = df_clean['Trade_History'].apply(ast.literal_eval)

