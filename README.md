# Stock Market Analytics Notes

Personal notes and results from exploring stock-market prediction and trading simulations.

## Results

- **Reduced-feature Random Forest:** Removing ticker and month-of-week dummy variables reduced the feature count from 301 to 208. The `pred10` rule at probability threshold 0.55 produced a CAGR of approximately 1.128 in the simulation.
- **Random Forest threshold comparison:** The 0.57 threshold averaged about 4.85 trades per day and was the strongest tested threshold below five average daily trades.
- **Redefined growth target:** With the positive-growth label set to 1 when 30-day future growth exceeds 1.022, `pred5_clf_10` generated 7,337 trades in the test set.

These are simulation outputs, not investment advice or a guarantee of future performance.

## Strategy idea

Rank candidates by predicted probability and, using thresholds selected on validation data, trade only the top five each day. Allocate equally with position-size limits, keep some cash in reserve, account for fees, and use a predefined exit and risk limit. Evaluate with walk-forward testing before changing the rules.

## Scope

This repository contains original notes and summaries only. Course notebooks and datasets are not included.
