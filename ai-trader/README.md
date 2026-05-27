# Rocking M AI Trader (Experimental)

Autonomous paper trader for testing AI trading logic and decision-making before live integration.

## What It Does

- **Live token discovery** — Real feeds from GeckoTerminal across 4 chains (Solana, Base, Ethereum, BSC)
- **Automated entry logic** — Safety scoring based on real pool data (liquidity, volume, age, risk factors)
- **Smart exits** — TP1 (30%), TP2 (70% + 20% runner), trailing stops (15%), stop loss (25%)
- **Risk management** — Max positions, capital reserve, position sizing limits
- **Event logging** — REMI logs every decision for analysis
- **AI training data** — Exports trades in ElizaOS format

---

## Current Behavior (Phase 1)

### 🟢 Real Data (Live)
- **Token Discovery** — Pulls actual newly launched tokens from GeckoTerminal in real-time
- **Entry Decisions** — Based on real pool data (liquidity, volume, age, holder concentration)
- **Safety Scoring** — Analyzes actual on-chain metrics

### 🟡 Paper Trading (Simulated)
- **The Trade Itself** — Fully simulated paper trading
  - Virtual balance decrements on entry (no real money used)
  - Position tracking is in software only
- **Price Movement** — Currently randomized/simulated
  - Does NOT follow real token prices after entry
  - Generates synthetic price volatility for testing purposes
  - Useful for testing logic, but not realistic market conditions
- **Exits (TP/SL/Trailing)** — Calculated on simulated prices

### Example Flow
```
REAL: Scanner finds token with $50k liquidity, $10k volume, 45 minutes old
REAL: Safety score = 87 (meets entry threshold)
PAPER: Subtracts $5 from virtual balance, creates position
FAKE: Price randomly fluctuates ±25% per tick
PAPER: Exits trigger on fake price movements
```

---

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

---

## Configuration

Settings in the UI:
- **Starting Balance** — Simulated account size
- **Max Positions** — Never hold more than X at once
- **Max Entry Size** — Single entry limit ($)
- **Capital Reserve** — % held back (don't use for trading)
- **Min Liquidity** — Skip pools below this
- **Max Token Age** — Skip pools older than this

---

## Running It

1. Open `index.html` in your browser
2. Set account parameters
3. Click **Initialize Account**
4. Click **Start REMI Scanner**
5. Watch REMI log decisions in real-time

## Exports

- **CSV** — Trade history for spreadsheet analysis
- **JSON (ElizaOS)** — Trade data formatted for AI agent training
- **Remi Log** — All decision events with timestamps and reasons

---

## Status & Roadmap

### ✅ Phase 1: Live Discovery + Paper Trading (Current)
- [x] Real token discovery (GeckoTerminal)
- [x] Automated entry logic on real data
- [x] Simulated paper trading
- [x] Risk management framework
- [x] Trade logging & exports
- **In Progress:**
  - [ ] Add exit reasons to CSV & JSON exports
  - [ ] Comprehensive logging (why each trade closed)
  - [ ] Testing & validation

### ⬜ Phase 1.5: Real Price Tracking (Next Priority)
- [ ] Live price feeds for open positions
- [ ] Replace randomized prices with real token prices
- [ ] User-configurable TP/SL levels
- [ ] More granular exit reasons
- [ ] Accurate PnL based on actual market prices

### ⬜ Phase 2: Wallet Integration
- [ ] MetaMask/WalletConnect (read-only connection)
- [ ] Display real wallet balances
- [ ] Testnet trading with user approval
- [ ] Position confirmation before execution
- [ ] One-click position closing

### ⬜ Phase 3: Live Trading Bot
- [ ] Mainnet trading (with kill-switches)
- [ ] Gas optimization
- [ ] Slippage protection
- [ ] Multi-signature security
- [ ] Emergency stop mechanisms

### ⬜ Phase 4: ElizaOS Agent
- [ ] Full AI agent orchestration
- [ ] Multi-chain coordination
- [ ] Training from real trade history
- [ ] Autonomous decision-making with guardrails

---

## Immediate Action Items

**Now (Phase 1 Polish):**
- [ ] Update CSV export to include exit reasons (TP1, TP2, TRAILING STOP, STOP LOSS, MANUAL)
- [ ] Update JSON export to include full decision log
- [ ] Test with various market conditions
- [ ] Validate safety scoring accuracy

**Next (Phase 1.5 - Real Prices):**
- [ ] Integrate live price feeds from GeckoTerminal for open positions
- [ ] Replace random price generation with real market data
- [ ] Add user input UI for custom TP/SL levels
- [ ] Make exit reasons explicit in logs

---

## Known Limitations

- **Simulated prices** — Price updates are randomized, not real market data
- **No wallet integration** — Paper trading only, no real funds
- **Static TP/SL** — Hardcoded at 30%/70%/15%/25% (user config coming Phase 1.5)
- **No liquidity impact** — Doesn't account for slippage or liquidity depth
- **Single-threaded** — May lag with many positions

---

## Contributing

Want to help? Areas we need:
- **Real price tracking** — Integrate GeckoTerminal prices for open positions
- **Export enhancements** — Better CSV/JSON with complete decision logs
- **User configuration** — Custom TP/SL inputs in UI
- **Risk modeling** — Position sizing algorithms
- **Chain integration** — Support more chains
- **UI improvements** — Mobile optimization, charts, analytics

See [../CONTRIBUTING.md](../CONTRIBUTING.md) for details.

---

**Experimental status:** This is not production-ready. Use only for research, testing, and AI training data generation.
