# chi_mu
Crypto trading AI skeleton:
- Data ingestion (CCXT -> parquet)
- Feature engineering
- Baseline SMA strategy
- ML training pipeline (XGBoost + scikit-learn preprocessing) with joblib model saving
- Backtesting with vectorbt
- Paper / live mode toggles (use paper mode for testing)

Quickstart (local)
1. python3 -m venv venv && source venv/bin/activate
2. pip install -r requirements.txt
3. Edit config/config.yaml
4. Run end-to-end (paper mode):
python scripts/run_pipeline.py

Train model only:
python scripts/train_model.py

Model artifacts saved to models/

Security
- Do NOT commit API keys. Use environment variables for secrets.
- This repo is a starting point. Do thorough testing before any live trading.

Structure
- src/data_pipeline: fetch & store OHLCV
- src/features: feature engineering and labeling
- src/ml: training and prediction utilities
- src/strategy: baseline and ML strategy implementations
- src/backtest: backtesting helpers
