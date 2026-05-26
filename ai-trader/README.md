# Rocking M AI Trader (Experimental)

Autonomous paper trader for testing AI trading logic and decision-making before live integration.

## What It Does

- **Live scanning** — Pulls new pools from GeckoTerminal every 12 seconds across 4 chains
- **Automated entry logic** — Safety scoring (liquidity, volume, age, risk factors)
- **Smart exits** — TP1 (30%), TP2 (70% + 20% runner), trailing stops (15%), stop loss (25%)
- **Risk management** — Max positions, capital reserve, position sizing limits
- **Event logging** — REMI logs every decision for analysis
- **AI training data** — Exports trades in ElizaOS format

## How It Works

### Safety Score Calculation
Each pool gets scored 0-100 based on:
- **Liquidity** (+45 if >= min config) 
- **24h Volume** (+20 if >= $2,500)
- **Pool Age** (+25 if < max age config)
- **Safety factor** (+10 randomized)

**Auto-entry trigger:** Score >= 58 AND available positions < max

### Position Management
Once entered:
- **TP1 at +30%** — Sells 40% of position
- **TP2 at +70%** — Sells 80%, activates 20% runner with trailing stop
- **Trailing Stop** — Activated after +25% or TP2, exits on 15% drop from peak
- **Hard SL** — Exits on -25% loss

## Status & Roadmap

### ✅ Phase 1: Live AI Paper Trader (Current)
- [x] Live pool scanning
- [x] Automated entry/exit logic
- [x] Risk management
- [x] Trade logging & exports
- [ ] Backtesting framework

### ⬜ Phase 2: Wallet Integration
- [ ] MetaMask/WalletConnect connection
- [ ] Read real wallet balances
- [ ] Testnet trading (no real money risk)
- [ ] Position tracking from chain

### ⬜ Phase 3: Live Trading Bot
- [ ] Mainnet trading (with fail-safes)
- [ ] Gas optimization
- [ ] Slippage protection
- [ ] Wallet security

### ⬜ Phase 4: ElizaOS Agent
- [ ] Full AI agent orchestration
- [ ] Multi-chain coordination
- [ ] Training from real trade history

## Configuration

Settings in the UI:
- **Starting Balance** — Simulated account size
- **Max Positions** — Never hold more than X at once
- **Max Entry Size** — Single entry limit ($)
- **Capital Reserve** — % held back (don't use for trading)
- **Min Liquidity** — Skip pools below this
- **Max Token Age** — Skip pools older than this

## Running It

1. Open `index.html` in your browser
2. Set account parameters
3. Click **Initialize Account**
4. Click **Start REMI Scanner**
5. Watch REMI log decisions in real-time

## Exports

- **CSV** — Trade history for spreadsheet analysis
- **JSON (ElizaOS)** — Trade data formatted for AI agent training
- **Remi Log** — All decision events with timestamps

## Known Limitations

- **Live data only** — No historical backtesting yet (Phase future)
- **Simulated prices** — Price updates are randomized, not real
- **No wallet integration** — Paper trading only (Phase 2)
- **Single-threaded** — May lag with many positions

## Contributing

Want to help? Areas we need:
- **Backtesting framework** — Test strategies against historical data
- **Risk modeling** — Position sizing algorithms
- **Chain integration** — Support more chains
- **UI improvements** — Mobile optimization, charts, analytics

See [../CONTRIBUTING.md](../CONTRIBUTING.md) for details.

## Next: Backtest Framework

The next major feature is a backtesting system that runs the same AI logic against historical GeckoTerminal data. This will let you:
- Test different safety scores
- Validate TP/SL levels
- Measure win rate & Sharpe ratio
- Before spending real money

---

**Experimental status:** This is not production-ready. Use only for research and testing.
