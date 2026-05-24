# 🏔️ Rocking M Crypto Screener

[![GitHub stars](https://img.shields.io/github/stars/RockingMScreener/rocking-m-screener.svg)](https://github.com/RockingMScreener/rocking-m-screener/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Language](https://img.shields.io/badge/Language-HTML%20100%25-blue.svg)](https://github.com/RockingMScreener/rocking-m-screener)
[![Live Demo](https://img.shields.io/badge/Demo-rockingmscreener.com-brightgreen)](https://rockingmscreener.com)

**Open source multi-chain crypto screener built by a leather craftsman from Montana.**

> *You don't have to be a master trader. You just need to know how to use the tools.*

**No paywalls. No signups. No influencer noise.** Just honest, filterable on-chain data you control.

**[🚀 Launch the Screener](https://rockingmscreener.com/screener.html)**  
**[📊 Paper Trader](https://rockingmscreener.com/papertrader.html)** · **[🤖 Remi AI](https://rockingmscreener.com/remi.html)**  
**[@Rockingmscreen on X](https://x.com/Rockingmscreen)** · **[Discord](https://https://discord.gg/aumVpSavB)**

---

## Why Rocking M?

I'm Edward, a small-town handyman and leather craftsman from Montana. I got tired of complicated or paywalled trading tools built for whales, not regular people. So I built something better — a **simple, powerful, fully open-source token screener** that runs 100% in your browser.

The Rocking M brand comes from my leather work. The inverted rocker in the logo represents taking old-school craftsmanship (patience, honesty, quality) into modern technology.

---

## What It Does

The Rocking M Screener scans new liquidity pools using **GeckoTerminal's free API**. You can scan up to **5 chains at once**, with support for a total of **13 blockchains**. You set the filters — it returns real data so you can decide what's worth deeper research.

### Key Features
- **Multi-chain scanning** — Select up to 5 chains at a time
- **Tier 1 + Tier 2 chains** with clear security differences
- **GoPlus Security** (Tier 1 only) — automatic honeypot, tax, holder, and creator concentration checks + composite risk score
- **Remi** — your plain-spoken AI trail guide (powered by Groq Llama 3.1)
- **Paper Trader** — realistic simulated trading with stop-loss, take-profit, trailing stops, and liquidity alerts
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

---

## GoPlus Security & Risk Scoring

For Tier 1 chains, the screener automatically checks every token after each scan:

- Honeypot detection — can the token actually be sold
- Buy and sell tax percentages
- Holder count
- Creator wallet concentration — high % means the dev can dump at any time

**Risk Score Meaning:**

| Score | Meaning |
|---|---|
| 🔴 HIGH RISK | Honeypot confirmed, sell tax over 10%, or creator holds over 50% of supply |
| 🟡 CAUTION | Sell/buy tax 5–10%, creator holds 20–50%, or under 10 holders |
| 🟢 LOW RISK | Passed all checks with sufficient data |
| ⬜ UNSCORED | Too new for GoPlus to have enough data — not a clean bill of health |

**Important:** The HP Check column shows the honeypot result only. HP: NO means the sell function works mechanically — it does not mean the token is safe. A token can show HP: NO and still score HIGH RISK if the creator holds 100% of supply. Always read the full Risk Score first.

---

## Meet Remi & the Paper Trader

**[Remi AI](https://rockingmscreener.com/remi.html)** — Plain spoken, no-hype AI trail guide. Helps you understand filters, spot rug pull patterns, interpret GoPlus results, and learn how to read the numbers. Can also draft social media posts and community updates in Edward's voice. Powered by Groq's free API — requires a free Groq key from [console.groq.com](https://console.groq.com). Your key is stored only in your browser.

**[Paper Trader](https://rockingmscreener.com/papertrader.html)** — Simulate trades using real market data across all 13 chains with no real money at risk. Features tiered stop loss, take profit levels, trailing stop with activation conditions, liquidity collapse detection with emergency exit, slippage simulation, and full Remi event logging. Trade outcomes export as CSV and JSON in ElizaOS training data format.

---

## Screenshots

![Screener Interface](screener.png)
*Five Tier 1 chains — GoPlus Risk Score, HP Check, and security columns visible*

![Remi AI](remi.png)
*Remi answering a question about the GoPlus risk scoring system*

![Paper Trader](papertrader.png)
*Paper Trader with open positions, automated level tracking, and Remi event log*

---

## Quick Start

No installation required. Open in any modern browser.

1. Go to [rockingmscreener.com](https://rockingmscreener.com) or open `screener.html` locally
2. Select up to 5 chains from the chain selector
3. Adjust filters or leave the presets as they are
4. Click **RUN SCAN**
5. GoPlus security data loads automatically for all Tier 1 results

---

## The Filters Explained

| Filter | What It Does |
|---|---|
| Min Liquidity | Weeds out low-value noise. Higher values return more established pools |
| Max Pool Age | Keeps results aligned to new pool discovery. Lower values find newer pools |
| Min 1H Change | Set higher for fast movers, lower for slow cookers |
| Min Volume 24H | Confirms trading activity behind the price movement |

---

## Trade Journal

The optional trade journal logs what you traded and why — token, contract address, entry price, exit price, and your reason for the trade. No dollar amounts are ever collected or requested. Your position size is your business.

Journal data exports as JSON in a format designed for ElizaOS agent training — building a dataset of real trade decisions and outcomes over time.

---

## Tech Stack

- Vanilla HTML, CSS & JavaScript — no frameworks, no dependencies
- GeckoTerminal free API — no key required
- GoPlus Security API — no key required, Tier 1 chains only
- Groq free API — key required for Remi (free at console.groq.com)

Runs entirely in the browser — no server, no backend, no tracking.

---

## Roadmap

- ✅ Create the screener and test it
- ✅ Secure the URL — rockingmscreener.com
- ✅ Build the GitHub repo and open it for contributions
- ✅ Create Rocking M social media (X/Twitter, Farcaster, Discord)
- ✅ Remi — AI trail guide powered by Groq
- ✅ Rocking M Paper Trader — simulated trading with real market data, tiered stop loss and take profit automation, liquidity collapse detection, and ElizaOS compatible trade outcome export
- ✅ GoPlus Security integration — honeypot detection, tax analysis, holder concentration, and rug flags across Tier 1 chains
- ⬜ Smart money tracking *(research ongoing — no free-tier solution identified yet)*
- ⬜ ElizaOS agent integration — autonomous trading powered by on-chain data and Rocking M signals
- ⬜ Community filter presets and shared learnings

---

## Contributing

This project grows through honest community input. You are welcome to:

- Share filter presets that have worked for you
- Contribute trade journal insights and outcomes
- Suggest new chains or features
- Report bugs or improvements via GitHub Issues
- Spread the word to traders who would benefit from honest tools

See [CONTRIBUTING.md](CONTRIBUTING.md) for details. No coding experience required — real trader feedback is extremely valuable.

---

## License

MIT License — free to use, modify, and share. See LICENSE file for details.

---

**Made in Montana with patience, real-world trading frustration, and AI assistance.**

Thank you for checking out Rocking M. I hope it helps you swing the hammer a little straighter.

— Edward  
Rocking M Leather Works · Montana
