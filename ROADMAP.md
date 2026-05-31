# 🗺️ Rocking M — Remi Suite Roadmap

**Remi — Rocking M Autonomous Investment Agent**

This document tracks the full development roadmap across all tools in the Remi suite. Individual tools maintain their own README files with implementation detail. This file is the single source of truth for phase planning and progress across the whole project.

---

## The Suite

| Tool | Name | Strategy | Status |
|---|---|---|---|
| Screener | **Cipher** | Discovery | ✅ Live |
| Paper Trader | **Craftsman** | Capital Growth | ✅ Live |
| AI Trader | **Stormchaser** | High Risk / High Reward | ✅ Live |
| Master Dashboard | **Ranch House** | Unified Command | ⬜ Phase 2 |
| AI Assistant | **Trail Guide** | Education & Support | ✅ Live |

**Two-strategy architecture:**
- **Strategy 1 — Capital Growth:** Cipher finds opportunities, Craftsman builds the stake with disciplined entries and tiered exits. Future: automated profit routing into long-term holds.
- **Strategy 2 — High Risk / High Reward:** Stormchaser runs autonomously on disposable capital, chasing newly launched micro-cap tokens. Lottery ticket mentality — kept architecturally separate from Strategy 1 by design.

---

## ✅ Complete

### Foundation
- [x] Cipher — multi-chain screener, 13 chains, max 5 per scan
- [x] GoPlus Security integration — honeypot detection, tax analysis, holder concentration, composite risk scoring (Tier 1 chains)
- [x] Composite Pool Score — weighted ranking (momentum 40%, liquidity 25%, freshness 20%, volume 15%)
- [x] Trail Guide — AI assistant powered by Groq Llama 3.1
- [x] Craftsman — tiered SL/TP, trailing stops, liquidity detection, slippage simulation, ElizaOS export
- [x] Trade Journal with CSV + JSON export (ElizaOS compatible format)
- [x] Stormchaser Phase 1 — autonomous paper trader with live token discovery
- [x] Stormchaser Phase 1.5 — real DexScreener price tracking (45s refresh), scanner pause/resume logic
- [x] Community leaderboard — built, launching June 1

### Refactors (v1.6)
- [x] Cipher — modular filter architecture: `getFilterConfig()`, `applyFilters()`
- [x] Cipher — modular scoring: `scorePool()`, `calcRiskScore()`
- [x] Cipher — modular render: `updateTableHeaders()`, `getChainTag()`, `renderGpCells()`, `renderTable()`, `updateStats()`
- [x] Stormchaser — `SCORE_CONFIG` object + `scoreCandidate()` function (issue #16)
- [x] Stormchaser — `EXIT_CONFIG` object + `evaluatePositions()` + clean `closePartial()` (issue #18)

### Documentation & Identity
- [x] Suite naming — Cipher, Craftsman, Stormchaser, Ranch House, Trail Guide
- [x] Main README updated with suite names, two-strategy philosophy, full roadmap
- [x] Stormchaser README fully rewritten
- [x] Unified ROADMAP.md (this file)

---

## ⬜ Near Term Polish

### All Tools
- [ ] **Mobile optimization** — full responsive layout across Cipher, Craftsman, Stormchaser (issue #15)
- [ ] **Solana GoPlus tooltip** — UI note clarifying UNSCORED on Solana reflects data availability limitation, not token quality

### Craftsman (Paper Trader) Refactors
- [ ] **Extract entry/exit logic** — dedicated entry and exit functions with clear boundaries
- [ ] **Extract position risk calculations** — position sizing and risk math as standalone module
- [ ] **Extract export functions** — CSV, JSON, log exports separated from render logic

### Stormchaser (AI Trader) Refactors
- [ ] **User-configurable TP/SL** — expose `EXIT_CONFIG` values in the UI (Phase 1.6)
- [ ] **More granular exit reasons** — detailed reason strings in log and exports
- [ ] **Testing and validation** — confirm behavior across various market conditions

---

## ⬜ Phase 2 — Unification & Intelligence
*Target: 6–10 weeks*

**Goal:** Create a single control layer that can see and manage both strategies simultaneously.

### Ranch House — Master Dashboard
- [ ] Side-by-side portfolio view (Craftsman + Stormchaser)
- [ ] Combined performance metrics — win rate, profit factor, max drawdown across both strategies
- [ ] Real-time overview with unified event feed
- [ ] Suite navigation hub — links to all tools with status indicators

### Unified Data Layer
- [ ] Unified logging format — both Craftsman and Stormchaser write to the same structured log schema
- [ ] Shared position object standard across tools
- [ ] Performance analytics module — win rate, profit factor, max drawdown for both tools

### agent-core.js — Central Decision Engine
- [ ] Reads data from both Craftsman and Stormchaser
- [ ] Basic profit allocation rules — when Stormchaser profits hit threshold, route to Craftsman capital bucket
- [ ] Configurable risk profiles — UI to adjust aggressiveness per strategy
- [ ] Example rule: "When realized gains exceed $X, move Y% into Capital Growth bucket"

### Code Architecture
- [ ] ES module split for Cipher — `js/filters.js`, `js/scoring.js`, `js/render.js`, `js/fetch.js`
- [ ] Shared utility library — formatters, chain metadata, common helpers used across tools

---

## ⬜ Phase 3 — Automated Allocation & Rebalancing
*Target: 8–12 weeks after Phase 2*

**Goal:** Make profit movement semi-autonomous with simulation and backtesting.

### Allocation Engine
- [ ] Route profits to configurable buckets:
  - Stablecoins (USDC/USDT)
  - Yield-bearing (staking / lending simulation)
  - Long-term crypto (BTC, ETH, SOL)
  - Traditional assets (ETFs / dividend stocks)
- [ ] Threshold-based triggers — "When balance exceeds $X, allocate Y% to Z bucket"
- [ ] Monthly or event-based rebalancing rules

### Yield Simulation Module
- [ ] Track simulated staking and lending yields
- [ ] Model compounding over time
- [ ] Compare yield strategies side by side

### Backtesting Framework
- [ ] Test allocation rules on historical trade data
- [ ] Scenario modeling — what would Strategy 1 look like with different SL/TP configs

### Stormchaser — Hybrid API Architecture
- [ ] GeckoTerminal for token discovery (newer pools, fresher signals)
- [ ] DexScreener for position monitoring (stable, no rate limit issues)
- [ ] Address mapping: EVM chains pass contract address directly to DexScreener
- [ ] Solana: store pool address at discovery time, pass to DexScreener pair endpoint
- [ ] Expanded chain support beyond Solana/Base/BSC

### Solana Signal Scoring
- [ ] Lightweight on-chain proxies as GoPlus alternative for Solana tokens
- [ ] Signals: pool percentage, liquidity depth, pool age, price action consistency
- [ ] Clearly labeled as Rocking M Signal Score — not GoPlus data
- [ ] GoPlus columns remain EVM-only

---

## ⬜ Phase 4 — Real Money & Traditional Assets
*Target: 3–6 months after Phase 3*

**Goal:** Move from paper trading toward real execution with strong safety layers.

### Wallet Integration
- [ ] Read-only wallet connections (multiple wallets)
- [ ] Real balance tracking for crypto side
- [ ] Separate wallets enforced — Stormchaser capital and Craftsman capital never mixed

### TradFi Integration
- [ ] Broker API integration — Alpaca, Interactive Brokers, or Robinhood Agentic API
- [ ] ETF and dividend stock execution for capital preservation bucket
- [ ] Yield farming / lending integration (Aave, Kamino)

### Safety Systems (Critical)
- [ ] Human-in-the-loop approval — all real-money transactions require confirmation
- [ ] Emergency stop / kill switches per strategy
- [ ] Maximum drawdown limits per strategy
- [ ] Daily loss limits
- [ ] Separate wallet enforcement with balance monitoring

---

## ⬜ Phase 5 — Full Autonomous Agent
*Target: 6–12+ months*

**Goal:** ElizaOS (or equivalent) based full AI investment agent trained on real trade history.

### Multi-Agent Architecture
- [ ] Scanner Agent — Cipher-powered discovery
- [ ] Risk Agent — GoPlus + Rocking M signal scoring
- [ ] Allocator Agent — profit routing and rebalancing decisions
- [ ] Execution Agent — trade placement with human approval tier

### Intelligence Layer
- [ ] Memory and learning from real Craftsman and Stormchaser trade history
- [ ] Natural language interface — "Explain why you allocated 40% to stables"
- [ ] Regular reporting — weekly summaries, performance breakdowns
- [ ] Advanced planning — scenario modeling and strategy suggestions

### Research Items (No Free Solution Found Yet)
- [ ] **Smart money tracking** — wallet following and on-chain signal detection
- [ ] **Cross-chain arbitrage signals** — price discrepancies across chains
- [ ] **Social sentiment integration** — X/Farcaster signal layer

---

## Locked Architecture Decisions

These decisions are finalized and should not be revisited without strong reason:

| Decision | Detail |
|---|---|
| Two-strategy separation | Stormchaser and Craftsman capital pools never mixed |
| API split (Phase 3) | GeckoTerminal for discovery, DexScreener for monitoring |
| EVM address mapping | Contract address passed directly to DexScreener |
| Solana address mapping | Pool address stored at discovery, passed to DexScreener pair endpoint |
| GoPlus scope | EVM (Tier 1) chains only — Solana gets Rocking M signal score in Phase 3 |
| Solana UNSCORED | UI tooltip explains data limitation — not a reflection of token quality |
| ES module split | Phase 2 — not before, natural fit with agent-core.js integration |
| Framework choice | Vanilla HTML/JS through Phase 2; evaluate Node.js/ElizaOS at Phase 3 entry |
| TradFi routing | Robinhood Agentic API primary candidate — revisit when Phase 4 begins |

---

## GitHub Issues Tracking

| Issue | Tool | Status |
|---|---|---|
| #15 — Mobile optimization | All tools | Open |
| #16 — Stormchaser: Extract safety scoring | Stormchaser | ✅ Complete |
| #18 — Stormchaser: Extract position/exit logic | Stormchaser | ✅ Complete |
| #20 — Cipher: Extract filter logic | Cipher | ✅ Complete |
| #21 — Cipher: Extract pool scoring | Cipher | ✅ Complete |
| #22 — Cipher: Extract render module | Cipher | ✅ Complete |
| Pending — Craftsman: Extract entry/exit logic | Craftsman | Planned |
| Pending — Craftsman: Extract risk calculations | Craftsman | Planned |
| Pending — Craftsman: Extract export functions | Craftsman | Planned |
| Pending — Solana signal scoring | Cipher | Phase 3 |

---

## Study & Build Plan Alignment

Edward's 12-week self-study plan runs parallel to this roadmap:

| Phase | Study Focus | Build Focus |
|---|---|---|
| Weeks 1–4 | JavaScript refresher (javascript.info) + active trading | Near term polish, Craftsman refactor |
| Weeks 5–8 | Maestro Bot + Node.js + ElizaOS GitHub exploration | Phase 2 — Ranch House + agent-core.js |
| Weeks 9–12 | Running ElizaOS locally + customizing plugins | Phase 3 entry — allocation engine |

Trade documentation (entry reason, exit reason, result) collected in both Craftsman and Stormchaser is the primary ElizaOS training dataset. The more trades logged with clear reasons, the better the eventual agent performs.

---

*Last updated: May 2026*  
*Maintained by Edward — Rocking M Leather Works, Montana*  
*[rockingmscreener.com](https://rockingmscreener.com) · [@Rockingmscreen](https://x.com/Rockingmscreen) · [Discord](https://discord.gg/aumVpSavB)*
