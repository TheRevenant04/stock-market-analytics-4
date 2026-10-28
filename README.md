# Stock Market Analytics

This project explores how to turn historical stock-market data into testable, risk-aware trading decisions. It focuses on predicting whether a stock will grow over the next 30 days, then evaluating whether those predictions could support a practical strategy after accounting for trade frequency, required capital, and transaction fees.

The analysis compares a Random Forest classifier and decision-tree models, tests how removing high-cardinality categorical features affects performance, and evaluates probability thresholds against both return and trading-efficiency goals. The aim is to distinguish a useful prediction model from a strategy that is realistically manageable to operate.

## Current findings

- Removing ticker and month-of-week dummy variables reduced the model feature count from 301 to 208. The Random Forest rule at a 0.55 probability threshold achieved a simulated CAGR of approximately 1.128.
- Among the tested Random Forest thresholds averaging fewer than five trades per day, 0.57 had the strongest simulated CAGR, at approximately 1.092.
- When a positive outcome was defined as 30-day growth above 1.022, the `pred5_clf_10` decision-tree predictor generated 7,337 test-set trades.

## Strategy direction

Rank stocks by predicted probability using thresholds selected on validation data, and trade at most the five highest-ranked candidates each day. Allocate capital equally with per-position limits, keep cash in reserve, include transaction fees, and define exit and loss limits in advance. Use walk-forward testing to assess whether the strategy remains robust over time.

These figures are historical simulation results, not investment advice or a guarantee of future performance. This repository currently documents the project and its findings; it does not include the underlying market dataset or executable analysis notebooks.
