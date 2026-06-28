# FearHarvester Skill

Autonomous DCA agent for extreme fear markets.

## Strategy
- Monitor Fear & Greed index continuously
- When F&G < 10 (Extreme Fear): DCA into BTC/ETH
- When F&G > 50 (Neutral/Greed recovery): rebalance into yield
- Removes human emotion from "buy the fear"

## Usage
```bash
# Backtest: optional positional args are [fg_threshold] [hold_days] (defaults: 10 90)
uv run python scripts/backtest.py 10 90

# Live signal check (no flags; prints current F&G + buy/hold signal)
uv run python scripts/signals.py

# Executor: --dry-run | --paper | --live | --status (plus --buy-threshold,
# --sell-threshold, --dca-amount, --max-capital). See executor.py --help.
uv run python scripts/executor.py --dry-run
```

## Historical edge (2018-2024)
Buying F&G < 10, holding 90d → 40-80% average return
