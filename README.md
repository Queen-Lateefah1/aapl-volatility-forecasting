# AAPL 30-Day Volatility Forecasting
Predicting Apple's 30-day realised volatility using HAR, Ridge, Random Forest, XGBoost and Ensemble models.


## Results (Test Year: 2024)

| Model         | R²     | MAPE  |
|---------------|--------|-------|
| HAR (Baseline)| 0.9024 | 4.26% |
| Random Forest | 0.8770 | 5.21% |
| XGBoost       | 0.8732 | 5.12% |
| Ensemble      | 0.8805 | 5.01% |
| Ridge         | 0.8439 | 6.06% |

## Models
- HAR (Heterogeneous Autoregressive) — academic benchmark
- Ridge Regression
- Random Forest (Optuna-tuned)
- XGBoost (Optuna-tuned)
- Ensemble (CV-weighted average)

## Tech Stack
Python, yfinance, scikit-learn, XGBoost, Optuna, pandas, matplotlib

## Key Insight
The single most powerful feature was `RV_30_lag1` (yesterday's 30-day realised vol).
Due to a 29/30-day rolling window overlap, adjacent volatility values have a correlation
of ~0.96 — making the lagged target the dominant predictor.

## Disclaimer
Educational purposes only. Not financial advice.

