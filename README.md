# 🏔️ Rocking M Crypto Screener

Open source autonomous investment suite built by a leather craftsman from Montana.
You don't have to be a master trader. You just need to know how to use the tools.
No paywalls. No signups. No influencer noise. Just honest, filterable on-chain data you control.

🚀 [Launch Cipher](https://rockingmscreener.com) · 📊 [Craftsman](https://rockingmscreener.com/papertrader.html) · 🤖 [Trail Guide](https://rockingmscreener.com/trailguide.html) · ⚡ [Stormchaser](https://rockingmscreener.com/stormchaser.html) ·[Forge](https://rockingmscreener.com/forge) . [@Rockingmscreen on X](https://x.com/Rockingmscreen) · [Discord](#)

---

## Why Rocking M?

I'm Edward, a small-town handyman and leather craftsman from Montana. I got tired of complicated or paywalled trading tools built for whales, not regular people. So I built something better — a completely free, no-BS crypto investment suite that runs right in your browser.

The Rocking M brand comes from my leather work. The inverted rocker in the logo represents taking old-school craftsmanship (patience, honesty, quality) into modern technology. Same philosophy: do the work right, or don't do it at all.

---

## The Remi Suite

**Remi — Rocking M Autonomous Investment Agent** is a two-strategy investment system built around a simple principle: keep disciplined capital growth and high-risk speculation completely separate. Each tool has a defined role.

| Tool | Name | Tagline |
|------|------|---------|
| Screener | **Cipher** | Decodes What the Market Is Saying |
| Paper Trader | **Craftsman** | Building with Precision |
| AI Trader (EVM) | **Stormchaser** | High Risk. High Reward. |
| Real Money (Solana) | **Forge** | Real Stakes. Real Execution. |
| Master Dashboard | **Ranch House** | Where Every Signal Comes Home |
| AI Assistant | **Trail Guide** | Here to Light the Way |

### Strategy 1 — Capital Growth (Cipher + Craftsman)
Disciplined scanning, filtered entries, tiered exits. Build and protect capital over time. Future: automated profit routing into long-term holds (BTC, ETH, SOL staking, ETFs).

### Strategy 2 — High Risk / High Reward (Stormchaser + Forge)
Disposable capital only. Autonomous discovery and execution on newly launched micro-cap tokens. Lottery ticket mentality — you know most tickets don't win.

---

## Cipher — Decodes What the Market Is Saying

Cipher is a browser-based DEX token screener built in vanilla HTML/CSS/JavaScript. It scans real-time on-chain pool data across eight major blockchains and scores tokens based on momentum, volume, liquidity, and buy/sell pressure.

### Data Source
Powered by the **CoinGecko Demo API** (GeckoTerminal onchain data). One free API key covers all scan modes. You enter and store your own key locally in the browser — it is never hardcoded or transmitted anywhere except CoinGecko's API.

### Scan Modes

**Trending** — Surfaces pools gaining momentum right now on the selected chain. Scored by multi-timeframe price movement, volume-to-liquidity ratio, and buy pressure.

**Top Volume** — Returns the highest 24h volume pools on the selected chain. Scored by raw volume strength, liquidity depth, and price momentum.

**New Tokens** — Scans the newest pools within a user-defined age window (default 0–60 minutes). Scored by freshness, early 5m/1h price momentum, and buy/sell ratio. Supports auto-scan with a configurable interval.

### Chains Covered
Solana · Ethereum · Base · BSC · Arbitrum · Optimism · Polygon · Avalanche · All Chains (global)

### Output Fields
Chain · Name · Symbol · Age · Price · Liquidity · 24h Volume · 5m% · 1h% · 24h% · Buys/Sells · Score · Link

### Scoring
Each mode uses a weighted composite score (0–99) tailored to that mode's signal. Trending weights momentum and buy pressure. Volume weights raw volume and liquidity. New Tokens weights freshness and early momentum. Results are sorted highest score first and capped at 40 per scan.

### Filters
Min Liquidity · Min Score · Min/Max Age (New Tokens mode only)

### Rate Limit Protection
Results are cached for 90 seconds. Auto-scan is restricted to New Tokens mode only to protect the free-tier API budget.

---

## Craftsman — Building with Precision

Simulate trades using real market data across all supported chains with no real money at risk.

- Tiered stop loss and take profit levels
- Trailing stops
- Automated level tracking
- Liquidity collapse detection
- Trade outcomes exported in ElizaOS format for agent training

---

## Trail Guide — Here to Light the Way

Your plain-spoken, no-hype AI assistant. Trail Guide helps you:

- Understand what each filter does and why
- Spot rug pull patterns and scam tactics
- Interpret on-chain data without drinking the Kool-Aid
- Navigate the full Remi suite

Powered by Groq's Llama 3.1. Requires a free API key from [console.groq.com](https://console.groq.com).

---

## Stormchaser — High Risk. High Reward.

Stormchaser is the automated ERC20 trading simulator in the Rocking M suite. It scans **seven major EVM chains** — Ethereum, Base, BSC, Polygon, Arbitrum, Optimism, and Avalanche — for new token pools using the GeckoTerminal API, scores candidates on liquidity, age, and volume, and simulates entries and exits against configurable risk parameters.

Discovered tokens are scored and filtered before entry. Positions are monitored in real time via DexScreener. Exits are managed through a three-tier take-profit ladder, a trailing stop, a hard stop loss, a max hold time, and a no-momentum timeout. A reserve floor tied to a high-water mark protects a configurable percentage of peak portfolio value.

**Realistic cost modeling** applies fixed slippage, buy tax, and sell tax percentages at execution — both entry and exit — so paper PnL reflects net returns rather than raw price movement. All unrealized PnL in the open positions display uses the same cost-adjusted calculation.

Completed trades export to CSV or ElizaOS-compatible JSON for trade journal analysis and future agent training.

> Stormchaser is paper-trading only. Real-money EVM execution is planned for a future phase.

---

## Forge V2.0 — Solana Real Money Trader

Real money trading tool for Solana tokens. Connects to **Backpack**, **Phantom**, and **Solflare** wallets. Executes swaps via the Jupiter Aggregator through a Cloudflare Worker proxy.

### Scan Modes

- **New Tokens** — Scans for brand new Solana pools. High risk, high reward.
- **Trending** — Established tokens with real momentum (up to 7 days old).
- **Volume Spike** — Tokens showing unusual 24h trading activity.
- **Manual Watchlist** — Paste token mint addresses to monitor and auto-enter.

### Safety Features

- Proportional honeypot detection
- GoPlus security checks
- Token cooldown blacklist
- Wallet spam detection
- Sell route verification before every buy

### Trade Management

- Configurable take profit levels (TP1 / TP2 / TP3)
- Trailing stop and hard stop loss
- Max hold time
- Partial close buttons (25% / 50% / 75% / 100%)

### ElizaOS Ready

JSON export includes entry score, entry reasons, hold time, and TP hit flags for agent training data.

---

## Quick Start

No installation required. Open in any modern browser.

1. Visit [rockingmscreener.com](https://rockingmscreener.com) or open `screener.html`
2. Enter your CoinGecko Demo API key when prompted (stored locally, never transmitted elsewhere)
3. Select a scan mode — Trending, Top Volume, or New Tokens
4. Choose a chain
5. Adjust filters or leave the presets
6. Click **RUN SCAN**

### The Filters Explained

| Filter | What It Does |
|--------|-------------|
| Min Liquidity | Weeds out low-value noise. $5K finds gems; $100K finds safer plays. |
| Min Score | Filters out weak signals before they clutter your results. |
| Min/Max Age | New Tokens mode only. Narrows the age window of pools returned. |

---

## Trade Journal

Logs token, contract address, entry price, exit price, and reason for the trade. No dollar amounts collected or requested.

Exports as JSON formatted for ElizaOS agent training — building a dataset of real trade decisions and outcomes so AI agents can learn your strategy.

---

## Tech Stack

- **Vanilla HTML, CSS & JavaScript** — no frameworks, no dependencies, no bloat
- **CoinGecko Demo API** — Cipher discovery and scoring (free key required)
- **DexScreener free API** — Stormchaser position monitoring, no key required
- **GoPlus Security API** — Forge safety checks, no key required
- **Jupiter Aggregator** — Forge real swap execution (via Cloudflare Worker proxy)
- **Groq free API** — Trail Guide AI assistant (free key at [console.groq.com](https://console.groq.com))

Runs entirely in the browser — no server, no backend, no tracking, no data collection.

---

## Code Architecture

### Cipher (`screener.html`)

| Module | Functions | Purpose |
|--------|-----------|---------|
| Filter Module | `getFilterConfig()`, `applyFilters()` | Reads UI values; tests each token against active filters |
| Scoring Module | `scorePool()` | Composite pool ranking per scan mode |
| Fetch Module | `fetchGecko()` | CoinGecko onchain API calls |
| Render Module | `renderTable()`, `updateStats()`, etc. | All DOM output |

### Forge (`forge.html`)

Cloudflare Worker proxy (`jupiter-proxy`) handles Jupiter swap routing and Helius RPC for wallet balance reads. The Worker sits between the browser and Jupiter's API to route around carrier-level API restrictions and keep keys off the client.

---

## Roadmap

### ✅ Complete

- Multi-chain screener — Cipher (8 chains + All Chains global mode)
- CoinGecko Demo API integration — three scan modes (Trending, Top Volume, New Tokens)
- Logarithmic scoring — prevents all-99 score saturation; results capped at 40
- 90-second result cache — free-tier API budget protection
- Auto-scan — New Tokens mode only
- Trail Guide — AI assistant powered by Groq
- Craftsman — tiered SL/TP, trailing stops, liquidity detection, ElizaOS export
- Trade Journal with CSV + JSON export
- Stormchaser — expanded to 7 EVM chains with realistic cost modeling (slippage, buy/sell tax)
- Forge V2.0 — real Solana swaps via Jupiter, three wallet providers, four scan modes, partial close buttons, Cloudflare Worker proxy infrastructure

### ⬜ Near Term

- Leaderboard — community paper trader leaderboard (launching Soon)
- Craftsman refactor — extract entry/exit logic, risk calculations, export functions
- Mobile optimization — full responsive layout across all tools

### ⬜ Phase 2 — Unification & Intelligence

- Ranch House — master dashboard, unified view of both strategies, combined performance metrics
- Unified logging — all tools write to the same structured log format
- `agent-core.js` — central decision engine reading data from all tools
- Profit allocation engine — rules-based routing of gains (Stormchaser → Craftsman → long-term holds)
- Configurable risk profiles — UI to adjust aggressiveness per strategy

### ⬜ Phase 3 — Automated Allocation & Rebalancing

- Allocation engine (stablecoins, yield-bearing, long-term crypto, traditional assets)
- Yield simulation module (staking/lending)
- Threshold-based rebalancing
- Backtesting framework
- Solana signal scoring — lightweight on-chain proxies as GoPlus alternative

### ⬜ Phase 4 — Real Money & Traditional Assets

- Read-only wallet connections
- Real balance tracking
- TradFi broker integration (Alpaca, Interactive Brokers, or Robinhood Agentic API)
- Yield farming / lending integration (Aave, Kamino)
- Human-in-the-loop approval system
- Emergency stop / kill switches

### ⬜ Phase 5 — Full Autonomous Agent (ElizaOS)

- Multi-agent system: Scanner · Risk · Allocator · Execution
- Memory and learning from real trade history
- Natural language interface
- Regular reporting
- Smart money tracking (research ongoing — no free-tier solution identified yet)

---

## Contributing

This project grows through honest community input. You are welcome to:

- Share filter presets that have worked for you
- Contribute trade journal insights — help us understand what works
- Suggest new chains or features — open an Issue
- Report bugs — [GitHub Issues](https://github.com/RockingMScreener/rocking-m-screener/issues) (no coding required)
- Spread the word — to traders who would benefit from honest tools

See `CONTRIBUTING.md` for details.

**Developers:** Vanilla HTML/CSS/JavaScript, no build process. Clone the repo, open `screener.html` in your browser, and start hacking.

---

## License

MIT License — free to use, modify, and share. See `LICENSE` for details.

---

## Support

- Questions? [Start a Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions)
- Found a bug? [Open an Issue](https://github.com/RockingMScreener/rocking-m-screener/issues)
- Want to chat? [Join us on Discord](#) or follow [@Rockingmscreen on X](https://x.com/Rockingmscreen)

---

*Made in Montana with patience, real-world trading frustration, and AI assistance.*

Thank you for checking out Rocking M. I hope it helps you swing the hammer a little straighter.

— Edward
*Rocking M Leather Works · Montana*
