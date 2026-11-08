# Hawk

AI-driven high-frequency cryptocurrency trading system: market data collection, model training, backtesting and a web dashboard.

## Features

- Market data sync and indicator calculation
- Model training and backtesting with visualization
- Trading and position management
- React dashboard

## Tech stack

Python 3.9+, Poetry, python-binance, FastAPI; React and TypeScript frontend

## Getting started

```bash
git clone https://github.com/elanchou/hawk.git
cd hawk/backend
poetry install
```

Edit `backend/config.yaml` for your data source and keys, then:

```bash
poetry run python scripts/sync_market_data.py       # fetch market data
poetry run python scripts/train_and_backtest.py     # train and backtest
poetry run python src/main.py                       # API service
cd ../frontend && yarn install && yarn start        # dashboard
```

`scripts/start.sh` starts backend and frontend together.

## Troubleshooting

`KeyError: "None of ['timestamp'] are in the columns"`: the data source must return a `timestamp` column. Check `get_market_data` in `backend/src/services/market_data_service.py`.

## Project structure

```text
backend/src/    api, data, ml, models, backtesting, trading, services
backend/scripts/ sync, train, backtest, visualize
frontend/src/   components, services, types
```
