# Rocking M Crypto Screener
### Open source crypto screener built by a leather craftsman from Montana

*You don't have to be a master trader. You just need to know how to use the tools.*

A free, open source, multi-chain token screener built on GeckoTerminal's free API. No paywalls, no whale tools, no influencer noise — just hard numbers you set yourself.

---

## What It Does

The Rocking M Screener scans new liquidity pools across multiple blockchains simultaneously and filters results based on parameters you control. It returns real data — not rumors, not wishful thinking — so you can make more informed decisions about which tokens are worth researching further.

**Current features:**

- 13 blockchains available, scan up to 5 simultaneously
- Two-tier chain system — Tier 1 chains include GoPlus security scanning, Tier 2 chains return price data only
- GoPlus Security integration — automatic honeypot detection, buy/sell tax analysis, holder count, and creator wallet concentration on all Tier 1 chains. No API key required
- Composite risk scoring — HIGH RISK, CAUTION, LOW RISK, or UNSCORED based on combined GoPlus signals
- Filters for minimum liquidity, pool age, 1H price change, and 24H volume
- Color-coded chain identification in results
- Clickable GeckoTerminal links for deeper research
- Contract address copy to clipboard
- Optional trade journal for logging entries and exits
- CSV and JSON export for ElizaOS agent training data
- Auto-refresh with configurable intervals

---

## The Chain Tiers

**Tier 1 — Full GoPlus Security Scanning**
Solana, Ethereum, Base, BSC, Arbitrum, Optimism

**Tier 2 — Price Data Only**
Polygon, Avalanche, Sui, Tron, Blast, Berachain, Cosmos

Tier 2 chains return live price and liquidity data from GeckoTerminal but do not include GoPlus security data. Do additional manual research before trading any Tier 2 token.

---

## GoPlus Security

When scanning Tier 1 chains, the screener automatically queries the GoPlus Security API for each token found. GoPlus is completely free and requires no API key.

**What GoPlus checks:**
- Honeypot detection — can the token actually be sold
- Buy tax and sell tax percentages
- Holder count
- Creator wallet percentage of total supply

**Risk Score — what it means:**

| Score | Meaning |
|---|---|
| 🔴 HIGH RISK | Honeypot confirmed, sell tax over 10%, or creator holds over 50% of supply |
| 🟡 CAUTION | Sell/buy tax 5–10%, creator holds 20–50%, or under 10 holders |
| 🟢 LOW RISK | Passed all checks with sufficient data |
| ⬜ UNSCORED | Too new for GoPlus to have enough data — not a clean bill of health |

**Important:** The HP Check column shows the honeypot result only. HP: NO means the sell function works mechanically — it does not mean the token is safe. A token can show HP: NO and still score HIGH RISK if the creator holds 100% of supply. Always read the full Risk Score, not just the honeypot result.

---

## Meet Remi

Remi is the Rocking M AI trail guide, available at [rockingmscreener.com/remi.html](https://rockingmscreener.com/remi.html).

Powered by Groq's free API running Llama 3.1. Remi won't tell you what to buy — but she will help you learn how to read the numbers, understand the filters, spot rug pull patterns, and make better use of the screener. Plain spoken, no hype, patient with beginners.

Remi requires a free Groq API key from [console.groq.com](https://console.groq.com). Your key is stored only in your browser and never sent anywhere except Groq.

---

## Rocking M Paper Trader

The Paper Trader lets you simulate trades using real market data with no real money at risk. Available at [rockingmscreener.com/papertrader.html](https://rockingmscreener.com/papertrader.html).

**Features:**
- Real-time prices via GeckoTerminal across all 13 chains
- Configurable tiered stop loss (SL1 partial, SL2 full exit)
- Configurable take profit levels (TP1, TP2, TP3)
- Trailing stop with activation conditions (gain % and time)
- Liquidity collapse detection with emergency exit
- Slippage simulation with retry logic
- Remi event log tracking every automated action
- CSV and JSON export in ElizaOS training data format

Tier 2 chain trades include a warning in the Remi log — no GoPlus security data is available for those chains.

---

## How To Use The Screener

No installation required. Open `screener.html` in any modern browser.

1. Select one to five blockchains from the chain selector
2. Adjust filters to match your trading preferences or leave the presets as they are
3. Hit **RUN SCAN**
4. GoPlus security data populates automatically for Tier 1 chains after the scan completes
5. Click **VIEW** on any result to open it in GeckoTerminal for further research

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

Journal data can be exported as JSON in a format designed for ElizaOS agent training — building a dataset of real trade decisions and outcomes over time.

---

## Community Contributions

This project grows through honest community input. You are welcome to:

- Submit filter presets that have worked for you
- Contribute trade outcomes to the shared dataset
- Suggest additional blockchains or filters
- Report bugs or improvements via GitHub Issues
- Share the project with traders who would benefit from it

No experience required. Just be honest about what you learned — what worked, what didn't, and what broke the system.

---

## Roadmap

- ✅ Build and test the screener
- ✅ Secure rockingmscreener.com
- ✅ GitHub repo open for contributions
- ✅ Community contribution system
- ✅ Rocking M social media presence
- ✅ Remi — AI trail guide powered by Groq
- ✅ Rocking M Paper Trader — simulated trading with real market data, tiered stop loss and take profit automation, liquidity collapse detection, and ElizaOS compatible trade outcome export
- ✅ GoPlus Security integration — honeypot detection, tax analysis, holder concentration, and rug flags across Tier 1 chains
- ⬜ Smart money tracking *(research ongoing — no free-tier solution identified yet)*
- ⬜ ElizaOS agent integration — autonomous trading powered by on-chain data and Rocking M signals

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript — no frameworks, no dependencies
- GeckoTerminal free API — no key required
- GoPlus Security API — no key required, Tier 1 chains only
- Groq free API — key required for Remi (free at console.groq.com)
- Runs entirely in the browser — no server, no backend

---

## License

MIT License — free to use, modify and share. See LICENSE file for details.

See [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to contribute.

---

## About

Built by Edward, a small-town handyman and leather craftsman from Montana who got frustrated with the crypto tools available to regular traders and decided to build something better.

The Rocking M brand comes from Rocking M Leather Works — the inverted rocker arc in the logo represents the same skills applied in a new direction. Old school craftsmanship meets modern technology.

This project was developed with the assistance of Claude AI. The vision, writing, and direction are entirely human.

**[rockingmscreener.com](https://rockingmscreener.com)**
&nbsp;·&nbsp;
**[X / Twitter](https://x.com/Rockingmscreen)**
&nbsp;·&nbsp;
**[Discord](https://discord.gg/Z2VWxUcpy)**
