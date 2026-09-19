# Cryptocurrency Arbitrage Bot

> Automated pairwise and triangular arbitrage trading bot

This project explores automated cryptocurrency trading by identifying short-lived pricing inefficiencies across exchange pairs and within single-exchange asset cycles. It includes pairwise arbitrage logic, triangular arbitrage logic, market data collection scripts, and a custom Cryptsy API wrapper.

## What It Does

### Pairwise arbitrage
The bot compares the same asset pair across multiple exchanges and looks for a profitable spread.

Example:

- Exchange A: BTC/USD = $40,000
- Exchange B: BTC/USD = $40,100

If fees, slippage, and liquidity support it, the bot can buy on the lower-priced exchange and sell on the higher-priced exchange.

### Triangular arbitrage
The bot also searches for inefficiencies across a cycle of assets on the same exchange, such as:

- ETH → USD → BTC → ETH

When the relative prices create a profitable loop, it can attempt a triangular execution path.

## Project Components

- `main_pair.py` — pairwise execution and monitoring
- `main_pair_data.py` — market-depth collection for analysis
- `main_pair_backtest.py` — strategy backtesting and evaluation
- `main_tri.py` — triangular execution logic
- `main_tri_data.py` — triangular market-data collection
- `main_tri_backtest.py` — triangular strategy backtesting
- `config.py` — API keys and strategy settings
- `CryptsyPythonAPI/` — custom API wrapper for Cryptsy trading endpoints
- `analysis/` — reporting and trade analysis utilities

## Tech Stack

- Python
- Exchange APIs
- Order book analysis
- Backtesting logic
- Trading strategy research

## Setup

1. Clone the repository:

```bash
git clone https://github.com/becominggiant/cryptocurrency_arbitrage.git
cd cryptocurrency_arbitrage
```

2. Configure your exchange credentials in `config.py`.

3. Run a paper-trading strategy:

```bash
python main_pair.py --mode paper
python main_tri.py --mode paper
```

4. Collect data for historical analysis:

```bash
python main_pair_data.py
python main_tri_data.py
```

5. Run a backtest:

```bash
python main_pair_backtest.py
python main_tri_backtest.py
```

## Why This Project Matters

This project is a strong example of algorithmic trading and execution research. It requires thinking about:

- liquidity depth
- slippage and transaction costs
- market timing
- execution risk
- strategy validation through backtesting

## Important Considerations

This repository is educational and experimental. Arbitrage strategies can be profitable only in limited conditions, and they are sensitive to fees, latency, and unexpected market behavior. Do not run live trading without fully testing and understanding the risk profile.

## Learning Outcomes

- reading and processing live exchange data
- modeling trade execution costs
- building automated strategy loops
- validating assumptions using backtests
- handling API stability and failure modes

## Notes

The original codebase targeted older exchange APIs and is best viewed as a historical or educational project. It remains useful for understanding the structure of an automated trading bot and the practical concerns behind real execution systems.
