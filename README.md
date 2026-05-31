# 🏔️ Rocking M Crypto Screener

[![GitHub stars](https://img.shields.io/github/stars/RockingMScreener/rocking-m-screener.svg)](https://github.com/RockingMScreener/rocking-m-screener/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Tech Stack](https://img.shields.io/badge/Stack-Vanilla%20JS%20%2B%20APIs-blue.svg)](https://github.com/RockingMScreener/rocking-m-screener/blob/main)
[![Live Demo](https://img.shields.io/badge/Demo-rockingmscreener.com-brightgreen)](https://rockingmscreener.com)

**Open source autonomous investment suite built by a leather craftsman from Montana.**
> *You don't have to be a master trader. You just need to know how to use the tools.*

**No paywalls. No signups. No influencer noise.** Just honest, filterable on-chain data you control.

**[🚀 Launch Cipher](https://rockingmscreener.com/screener.html)**  
**[📊 Craftsman](https://rockingmscreener.com/papertrader.html)** · **[🤖 Trail Guide](https://rockingmscreener.com/remi.html)**
**[Stormchaser](https://rockingmscreener.com/ai-trader/index.html)**
**[@Rockingmscreen on X](https://x.com/Rockingmscreen)** · **[Discord](https://discord.gg/aumVpSavB)**

---

## Why Rocking M?

I'm Edward, a small-town handyman and leather craftsman from Montana. I got tired of complicated or paywalled trading tools built for whales, not regular people. So I built something better — a completely free, no-BS crypto investment suite that runs right in your browser.

The Rocking M brand comes from my leather work. The inverted rocker in the logo represents taking old-school craftsmanship (patience, honesty, quality) into modern technology. Same philosophy: do the work right, or don't do it at all.

---

## The Remi Suite

**Remi — Rocking M Autonomous Investment Agent** is a two-strategy investment system built around a simple principle: keep disciplined capital growth and high-risk speculation completely separate. Each tool has a defined role.

| Tool | Name | Tagline |
|---|---|---|
| Screener | **Cipher** | *Decodes What the Market Is Saying* |
| Paper Trader | **Craftsman** | *Building with Precision* |
| AI Trader | **Stormchaser** | *High Risk. High Reward.* |
| Master Dashboard | **Ranch House** | *Where Every Signal Comes Home* |
| AI Assistant | **Trail Guide** | *Here to Light the Way* |

**Strategy 1 — Capital Growth (Cipher + Craftsman)**  
Disciplined scanning, filtered entries, tiered exits. Build and protect capital over time. Future: automated profit routing into long-term holds (BTC, ETH, SOL staking, ETFs).

**Strategy 2 — High Risk / High Reward (Stormchaser)**  
Disposable capital only. Autonomous discovery and execution on newly launched micro-cap tokens. Lottery ticket mentality — you know most tickets don't win.

---

## Cipher — Decodes What the Market Is Saying

Cipher scans new liquidity pools across multiple blockchains using **GeckoTerminal's free API**. Scan up to **5 chains simultaneously** across **13 blockchains**. Set your filters and Cipher returns what matches, ranked by composite score. For Tier 1 chains, every result is automatically checked for security red flags using GoPlus.

Think of it as a fishing net with adjustable mesh: cast it where you want, tune the holes, and see what swims up.

### Key Features

- **Multi-chain scanning** — Select up to 5 chains at a time
- **Tier 1 + Tier 2 chains** with clear security differences marked
- **GoPlus Security scanning** (Tier 1 only) — honeypot detection, tax analysis, holder and creator concentration with composite risk scoring
- **Composite Pool Score** — weighted ranking (momentum 40%, liquidity 25%, freshness 20%, volume 15%) so the best overall opportunities surface first
- **Trail Guide** — plain-spoken AI assistant powered by Groq Llama 3.1
- **Trade Journal** + CSV/JSON export (ElizaOS compatible)
- **Auto-refresh** and one-click GeckoTerminal links
- **100% client-side** — no backend, no tracking, no accounts

---

## Supported Chains

**Tier 1 — Full GoPlus Security Scanning**  
Solana, Ethereum, Base, BSC, Arbitrum, Optimism

**Tier 2 — Price & Liquidity Data Only**  
Polygon, Avalanche, Sui, Tron, Blast, Berachain, Cosmos

> **Note:** Always do extra research on Tier 2 tokens since GoPlus security data is not available.
>
> **Solana note:** GoPlus coverage for Solana is limited by design — their system was built around EVM chains first. UNSCORED on Solana reflects a data availability limitation, not a clean bill of health. Solana-specific signal scoring using on-chain proxies is on the roadmap.

---

## GoPlus Security & Risk Scoring

For Tier 1 chains, Cipher automatically checks every token after each scan:

- **Honeypot detection** — can the token actually be sold
- **Buy and sell tax percentages** — how much you'll lose on entry/exit
- **Holder count** — is the supply spread out or concentrated?
- **Creator wallet concentration** — high % means the dev can dump at any time

### Risk Score Meaning

| Score | Meaning |
|---|---|
| 🔴 **HIGH RISK** | Honeypot confirmed, sell tax over 10%, or creator holds over 50% of supply |
| 🟡 **CAUTION** | Sell/buy tax 5–10%, creator holds 20–50%, or under 10 holders |
| 🟢 **LOW RISK** | Passed all checks with sufficient data |
| ⬜ **UNSCORED** | Insufficient GoPlus data — not a clean bill of health |

**Important:** HP: NO means the sell function works mechanically — it does not mean the token is safe. A token can show HP: NO and still be rugpulled through liquidity pairs, creator dumps, or contract exploits. **Always verify contract code on Etherscan/Solscan before trading real money.**

---

## Composite Pool Score

After each scan, every token receives a 0–100 composite score used for the default sort order:

| Signal | Weight | Cap |
|---|---|---|
| 1H Momentum | 40% | 200% gain |
| Liquidity | 25% | $100K |
| Freshness (pool age) | 20% | 24h window |
| Volume 24H | 15% | $500K |

Newer, liquid, actively-traded tokens with strong 1H momentum rank at the top. You can still sort by any individual column — Score is just the default starting view.

---

## Craftsman — Building with Precision

Simulate trades using real market data across all 13 chains with no real money at risk.

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
- Interpret GoPlus security results
- Learn how to read on-chain data without drinking the Kool-Aid

Powered by Groq's Llama 3.1 (requires a free API key from console.groq.com).

---

## Stormchaser — High Risk. High Reward.

Autonomous paper trader for newly launched micro-cap tokens. Runs on DexScreener across Solana, Base, and BSC. Deploys small disposable capital, chases big movers, and generates ElizaOS training data from every decision.

See [ai-trader/README.md](ai-trader/README.md) for full documentation.

---

## Screenshots

![Screener Interface](screener.png)
*Cipher — Five Tier 1 chains with GoPlus Risk Score, HP Check, and Composite Score*

![Remi AI](remi.png)
*Trail Guide answering a question about the GoPlus risk scoring system*

![Paper Trader](papertrader.png)
*Craftsman with open positions, automated level tracking, and Trail Guide event log*

---

## Quick Start

No installation required. Open in any modern browser.

1. **Visit** [rockingmscreener.com](https://rockingmscreener.com) or open [screener.html](https://rockingmscreener.com/screener.html)
2. **Select chains** — up to 5 at a time
3. **Adjust filters** or leave the presets:
   - **Min Liquidity** — filters out dust, focuses on established pools
   - **Max Pool Age** — finds newly created pools (lower = newer)
   - **Min 1H Change** — targets fast movers or steady climbers
   - **Min Volume 24H** — confirms real trading activity
4. **Click RUN SCAN** — Cipher queries GeckoTerminal
5. **Results ranked by Composite Score** — GoPlus data loads automatically for Tier 1

---

## The Filters Explained

| Filter | What It Does |
|---|---|
| **Min Liquidity** | Weeds out low-value noise. $5K finds gems; $100K finds safer plays. |
| **Max Pool Age** | Lower values find brand-new pools. Higher finds more established tokens. |
| **Min 1H Change** | Set higher (+50%) for fast movers. Set lower (0–20%) for steady climbs. |
| **Min Volume 24H** | Confirms trading activity behind the price movement. No volume = nobody's interested. |

---

## Trade Journal

Logs token, contract address, entry price, exit price, and reason for the trade. No dollar amounts collected or requested.

Exports as **JSON formatted for ElizaOS agent training** — building a dataset of real trade decisions and outcomes so AI agents can learn your strategy.

---

## Tech Stack

- **Vanilla HTML, CSS & JavaScript** — no frameworks, no dependencies, no bloat
- **GeckoTerminal free API** — Cipher discovery, no key required
- **DexScreener free API** — Stormchaser position monitoring, no key required
- **GoPlus Security API** — no key required, Tier 1 chains only
- **Groq free API** — key required for Trail Guide (free at console.groq.com)

**Runs entirely in the browser** — no server, no backend, no tracking, no data collection.

---

## Code Architecture

### Cipher (screener.html)

Organized into focused modules after the v1.6 refactor:

| Module | Functions | Purpose |
|---|---|---|
| **Filter Module** | `getFilterConfig()`, `applyFilters()` | Reads UI values; tests each token against active filters |
| **Scoring Module** | `scorePool()`, `calcRiskScore()` | Composite pool ranking; GoPlus risk verdict |
| **Fetch Module** | `fetchGecko()`, `fetchGoPlus()` | GeckoTerminal and GoPlus API calls |
| **Render Module** | `updateTableHeaders()`, `getChainTag()`, `renderGpCells()`, `renderTable()`, `updateStats()` | All DOM output |

This modular structure prepares the codebase for Phase 2 — Ranch House and `agent-core.js` can call these functions directly without touching unrelated code.

---

## Roadmap

### ✅ Complete
- Multi-chain screener — Cipher (13 chains, max 5 per scan)
- GoPlus Security integration — honeypot, tax, holder concentration, composite risk scoring
- Trail Guide — AI assistant powered by Groq
- Craftsman — tiered SL/TP, trailing stops, liquidity detection, ElizaOS export
- Trade Journal with CSV + JSON export
- Stormchaser Phase 1 — autonomous paper trader
- Stormchaser Phase 1.5 — real DexScreener price tracking (45s refresh)
- Cipher refactor — modular filter, scoring, and render architecture (v1.6)

### ⬜ Near Term
- **Leaderboard** — community paper trader leaderboard (built, launching July 1)
- **Solana UNSCORED tooltip** — UI note clarifying GoPlus data limitation vs token quality
- **Craftsman refactor** — extract entry/exit logic, risk calculations, export functions
- **Stormchaser refactor** — extract safety scoring, position/exit logic
- **Mobile optimization** — full responsive layout across all tools

### ⬜ Phase 2 — Unification & Intelligence
- **Ranch House** — master dashboard, unified view of both strategies, combined performance metrics
- **Unified logging** — both tools write to the same structured log format
- **agent-core.js** — central decision engine reading data from both tools
- **Profit allocation engine** — rules-based routing of gains (Stormchaser → Craftsman → long-term holds)
- **ES module split** — break Cipher into `js/filters.js`, `js/scoring.js`, `js/render.js`, `js/fetch.js`
- **Configurable risk profiles** — UI to adjust aggressiveness per strategy

### ⬜ Phase 3 — Automated Allocation & Rebalancing
- Allocation engine (stablecoins, yield-bearing, long-term crypto, traditional assets)
- Yield simulation module (staking/lending)
- Threshold-based rebalancing
- Backtesting framework
- Stormchaser hybrid API — GeckoTerminal for discovery, DexScreener for position monitoring
- Solana signal scoring — lightweight on-chain proxies (pool %, liquidity depth, age) as GoPlus alternative

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
- **Smart money tracking** *(research ongoing — no free-tier solution identified yet)*

---

## Contributing

This project grows through honest community input. You are welcome to:

- **Share filter presets** that have worked for you
- **Contribute trade journal insights** — help us understand what works
- **Suggest new chains or features** — open an Issue
- **Report bugs** — GitHub Issues (no coding required)
- **Spread the word** — to traders who would benefit from honest tools

**[See CONTRIBUTING.md](https://github.com/RockingMScreener/rocking-m-screener/blob/main/CONTRIBUTING.md) for details.**

**Developers:** Vanilla HTML/CSS/JavaScript, no build process. Clone the repo, open `screener.html` in your browser, and start hacking.

---

## License

MIT License — free to use, modify, and share. See [LICENSE](https://github.com/RockingMScreener/rocking-m-screener/blob/main/LICENSE) for details.

---

## Support

- **Questions?** Start a [Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions)
- **Found a bug?** [Open an Issue](https://github.com/RockingMScreener/rocking-m-screener/issues)
- **Want to chat?** Join us on [Discord](https://discord.gg/aumVpSavB) or follow [@Rockingmscreen](https://x.com/Rockingmscreen) on X

---

**Made in Montana with patience, real-world trading frustration, and AI assistance.**

Thank you for checking out Rocking M. I hope it helps you swing the hammer a little straighter.

— Edward  
*Rocking M Leather Works · Montana*
