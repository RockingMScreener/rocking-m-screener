# ⚡ Stormchaser — High Risk. High Reward.

**Part of the Remi Suite · Rocking M Autonomous Investment Agent**

Stormchaser is an autonomous paper trader for newly launched micro-cap tokens. It discovers opportunities, enters positions, manages exits, and logs everything — all without manual input. This is the lottery ticket strategy: small disposable capital chasing big movers.

> ⚠️ **Research and AI training data generation only. Never deploy more capital here than you are fully prepared to lose entirely.**

---

## Philosophy

Most traders blur disciplined investing and high-risk speculation until neither works. The Remi suite keeps them architecturally and psychologically separate by design.

**Stormchaser — The Lottery Ticket**
Deploy only capital you have mentally already written off. Chase newly launched tokens with high risk and high reward potential. Losses are expected and acceptable — the goal is finding the occasional 10x that covers everything else.

**Craftsman — The Capital Builder**
Disciplined entries, tiered exits, hard stop losses. Slow steady account growth with downside protection. Completely separate tool, separate capital, separate mindset.

**Why both matter for ElizaOS training:**
Stormchaser generates high-risk autonomous discovery patterns. Craftsman generates disciplined risk management patterns. An agent trained on both datasets can eventually manage both strategies simultaneously with separate capital pools.

---

## What It Does

- **Token discovery** — Scans DexScreener for newly launched tokens across Solana, Base, and BSC
- **Automated entry** — Enters positions based on liquidity, age, and safety score thresholds
- **Smart exits** — TP1 (30%), TP2 (70% + runner), trailing stop (15%), hard stop loss (25%)
- **Real price tracking** — Open positions monitored via DexScreener every 45 seconds
- **Scanner pause logic** — Stops scanning for new tokens when max positions are filled; resumes automatically when a position closes
- **Risk management** — Max positions, capital reserve, per-position size limits
- **Event logging** — Every decision logged with timestamp and reason
- **ElizaOS export** — Trades exported in AI agent training format

---

## API Architecture

| Function | API | Why |
|---|---|---|
| Token discovery | DexScreener | No rate limit issues at 45s refresh; returns newly launched tokens |
| Position monitoring | DexScreener | Same API, consistent address format, reliable price feed |

> **Note:** GeckoTerminal returns genuinely newer pools and is used in Cipher (the screener). A hybrid architecture — GeckoTerminal for discovery, DexScreener for monitoring — is on the Phase 3 roadmap. Address mapping between the two APIs requires careful handling, particularly for Solana pool addresses.

---

## How It Works

### Scanner Logic
Stormchaser only scans for new tokens when open positions are below the max limit. Once full, scanning pauses and the tool monitors existing positions only. When a position closes, scanning resumes automatically. This prevents rate limit issues and keeps the tool focused.

### Safety Score
Each candidate token is evaluated on:
- Liquidity (primary filter — minimum configurable)
- Pool age (maximum configurable)
- Basic risk filters

Auto-entry triggers when score >= 58 and available positions < max.

### Position Lifecycle
1. **Entry** — Size limited by `maxEntry` and available capital after reserve
2. **TP1 at +30%** — Sells 40% of position
3. **TP2 at +70%** — Sells 80%, activates trailing stop on remainder
4. **Trailing Stop** — Activates after +25% or TP2; exits on 15% drop from peak
5. **Hard Stop Loss** — Exits full position on -25%
6. **Manual Close** — Available at any time via the UI

---

## Configuration

| Setting | Default | Description |
|---|---|---|
| Starting Balance | $1,000 | Simulated account size |
| Max Positions | 5 | Never hold more than this at once |
| Max Entry Size | $5 | Single position limit |
| Capital Reserve | 25% | Held back, never traded |
| Min Liquidity | $5,000 | Skip pools below this |
| Max Token Age | 180 min | Skip pools older than this |

---

## Running It

1. Open [rockingmscreener.com/ai-trader/](https://rockingmscreener.com/ai-trader/index.html) in your browser
2. Set account parameters
3. Click **Initialize Account**
4. Click **Start Stormchaser Scanner**
5. Watch the event log in real-time

**Keyboard shortcut:** Press `R` to manually trigger a price update.

---

## Exports

- **CSV** — Trade history for spreadsheet analysis
- **JSON (ElizaOS)** — Trade data formatted for AI agent training
- **Remi Log** — All decision events with timestamps and reasons

---

## Supported Chains

Solana · Base · BSC

---

## Roadmap

### ✅ Phase 1 — Live Discovery + Paper Trading
- Real token discovery via DexScreener
- Automated entry logic
- Simulated paper trading
- Risk management framework
- Trade logging and exports
- Exit reasons in CSV and JSON
- Comprehensive decision logging

### ✅ Phase 1.5 — Real Price Tracking
- Live price feeds for open positions (45s refresh)
- Real-time PnL based on actual market prices
- Scanner pause/resume logic on position limits
- Rate limit handling with backoff

### ⬜ Phase 1.6 — Polish
- User-configurable TP/SL levels in UI
- More granular exit reasons in logs
- Refactor — extract safety scoring logic
- Refactor — extract position and exit logic
- Testing and validation across market conditions

### ⬜ Phase 2 — Ranch House Integration
- Write to unified log format shared with Craftsman
- Feed data to agent-core.js decision engine
- Combined performance metrics in Ranch House dashboard
- Profit allocation rules — route Stormchaser gains to Craftsman capital bucket

### ⬜ Phase 3 — Hybrid API + Improved Discovery
- GeckoTerminal for token discovery (newer pools, fresher signals)
- DexScreener for position monitoring (stable, no rate issues)
- Address mapping: EVM chains use contract address directly; Solana stores pool address at discovery
- Expanded chain support

### ⬜ Phase 4 — Wallet Integration
- MetaMask / WalletConnect read-only connection
- Real wallet balance display
- Position confirmation before execution
- One-click closing

### ⬜ Phase 5 — ElizaOS Agent
- Full AI agent orchestration
- Training from real Stormchaser trade history
- Autonomous decision-making with guardrails
- Coordination with Craftsman agent

---

## Known Limitations

- Paper trading only — no real funds, no wallet integration
- TP/SL levels hardcoded (user config coming Phase 1.6)
- No slippage or liquidity impact modeling
- Solana address handling may require pool address vs token address

---

## Contributing

Areas where help is welcome:

- **User configuration** — Custom TP/SL inputs in UI
- **Risk modeling** — Improved position sizing algorithms
- **Chain support** — Additional chains beyond Solana/Base/BSC
- **UI improvements** — Mobile optimization, charts, analytics
- **Export enhancements** — More complete decision logs

See [../CONTRIBUTING.md](../CONTRIBUTING.md) for details.

---

**Part of the Remi Suite — Rocking M Autonomous Investment Agent**  
[rockingmscreener.com](https://rockingmscreener.com) · [@Rockingmscreen](https://x.com/Rockingmscreen) · [Discord](https://discord.gg/aumVpSavB)
