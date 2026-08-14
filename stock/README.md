# 📈 Rocking M Stocks

Long-term capital preservation and active trading, screened and paper-traded
in one place — same free, open-source, no-BS philosophy as the rest of the
Rocking M suite, applied to equities and ETFs instead of crypto.

🔦 [Launch Lighthouse](https://rockingmsuite.com/stock/lighthouse.html) · 🏡 [Launch Homestead](https://rockingmsuite.com/stock/homestead.html)

## Why a Stock Module?

The original Rocking M suite (Cipher, Craftsman, Stormchaser, Forge) covers
crypto. This folder extends the same two-strategy philosophy — disciplined
capital growth kept separate from high-risk speculation — into stocks and
ETFs, for anyone who wants both in one toolkit instead of juggling separate
paywalled apps.

Built for two audiences at once: someone using these tools purely for
long-term capital preservation, and someone using the exact same tools to
day trade. Neither audience is the "real" one — the tools are designed to
serve both from a shared codebase, the same way the crypto side keeps a
lottery-style speculative portfolio separate from long-term holdings.

| Tool | Name | Tagline | Status |
|------|------|---------|--------|
| Screener | **Lighthouse** | Guides You to Steady Ground | ✅ Live |
| Paper Trader | **Homestead** | *(building next)* | 🚧 In development |

---

## Lighthouse — Guides You to Steady Ground

Browser-based stock/ETF screener built in vanilla HTML/CSS/JavaScript — no
build step, no framework, no install. Same single-file pattern as Cipher.

### Data Sources

- **Finnhub** *(required)* — real-time US quotes and fundamentals. Free tier,
  ~60 calls/minute. Get a key at [finnhub.io/register](https://finnhub.io/register).
- **Alpaca** *(optional)* — used only to flag which symbols support
  fractional-share orders, as groundwork for Homestead. Requires a free
  Alpaca account with paper-trading API keys. Alpaca's signup requires MFA
  through an authenticator app (Google Authenticator, Authy, etc.) — this is
  an Alpaca account requirement, not something Lighthouse adds.

Both keys are entered once and stored in your browser's `localStorage` only
— never transmitted anywhere except directly to Finnhub/Alpaca's own APIs.

### Scan Mode Families

**Preservation**
- *Quality & Value* — ranks on P/E, dividend yield, debt/equity, and low
  drawdown.
- *Dividend Growth* — surfaces dividend payers sorted by yield, with payout
  ratio shown to help screen out yield traps.
- *Low Volatility* — sorts by beta ascending, calmest names first.

**Momentum**
- *Top Volume* — sorts by relative volume vs. recent average.
- *Gap Scanner* — sorts by today's % change as a gap/momentum proxy.
- *Relative Strength* — sorts by today's % change within the selected
  universe.

### Universes

Instead of scanning the entire market (thousands of tickers, well beyond
free-tier rate limits), Lighthouse scans a selected universe:

- **S&P 500** (503 tickers)
- **Nasdaq 100** (~100 tickers)
- **Dow Jones Industrial Average** (30 tickers)
- **Dividend Aristocrats** (~62 tickers — 25+ years of consecutive dividend
  growth)
- **Popular ETFs** (15 tickers — SPY, VOO, QQQ, VTI, SCHD, and similar)
- **My Watchlist** — a custom, user-editable universe stored locally
- **Russell 2000** — reserved for a future release given its size (~2,000
  tickers)

A **Max Symbols to Scan** field lets you control scan time independent of
universe size, since Finnhub's free tier can't scan hundreds of tickers
quickly — the scan paces itself under the free-tier rate limit
automatically.

Sector filtering (AI, Utilities, Durable Goods, etc.) is pulled dynamically
from each data source's sector/industry field rather than hand-curated, to
keep the universe list low-maintenance.

### Output Fields

Symbol · Name · Sector · Price · Chg % · P/E · Dividend Yield · Beta ·
Relative Volume · Fractionable (✓/✗, requires Alpaca key) · Score · Research
link (opens the symbol's Yahoo Finance page)

### Scoring

A 0–99 composite score rewards a reasonable P/E, real dividend yield, low
debt/equity, and low beta — tuned toward the capital-preservation side, but
shown across both mode families so it's always available as a reference
point.

### Filters

Min Score · Min Dividend Yield (Dividend Growth mode) · Max P/E · Max Beta ·
Min Abs. Change % (Momentum modes) · Dividend Payers Only · Fractionable
Only

---

## Homestead — Two-Account Paper Trader *(in development)*

Homestead extends Craftsman's proven paper-trading pattern to stocks and
ETFs, with two structural differences driven by how this module needs to
work for both long-term and active-trading users:

### Two Separate Accounts, Not One Balance

Mirrors the lottery-portfolio-vs-long-term-holdings split already used on
the crypto side:

- **Lottery** — short-horizon paper account. Profits above a configurable
  threshold sweep automatically into Long-Term (mirroring a real $5
  profit-sweep rule). Simulates the Pattern Day Trader (PDT) rule: 4+ day
  trades within a rolling 5 business days requires the account to hold
  $25,000+ in simulated equity, or trading is restricted — same as a real
  margin account.
- **Long-Term** — capital-preservation account. No sweep, no PDT
  restriction. Tracked on CAGR vs. benchmark, drawdown, and dividend income
  rather than win rate.

Each account has fully separate buying power — a loss in one can't touch
the other.

### Persistent State

Unlike Craftsman (in-memory only, resets on page close), Homestead persists
both accounts to `localStorage`, since long-term holdings need to survive
across sessions. Includes JSON export/import for backup, and a
`schemaVersion` field so the storage format can evolve without breaking
existing saved data.

### Fractional Shares

Supports fractional-share paper positions, checked per-symbol against
Alpaca's `fractionable` flag (the same data Lighthouse's badge already
surfaces) — not every stock or ETF supports fractional orders in real
markets, and Homestead won't pretend otherwise.

### Broker Integration

Wired to Alpaca's Paper Trading API from the start — Alpaca uses the same
endpoint shapes for paper and live accounts, so enabling live trading later
is a configuration change, not a rewrite. Broker linkage is optional, not
required to use Homestead's simulation core.

### Not Yet Simulated

After-hours/extended-hours trading is intentionally out of scope for the
initial build.

---

## Data Contract

Lighthouse and Homestead share one asset shape and one position shape
(branching on a `family`/`horizon` field rather than forking into separate
codebases), so Ranch House will eventually be able to consume both through
a single, stable interface. See `stock-module-data-contract.md` for the
full field-level spec.

---

## Quick Start

No installation required. Open in any modern browser.

1. Open `lighthouse.html`
2. Click **⚙ Data Sources**, add your free Finnhub key (required) and
   optionally your Alpaca paper-trading keys
3. Pick a scan mode family (Preservation or Momentum) and a universe
4. Click **Scan Now**

---

## Roadmap

- [x] Lighthouse — stock/ETF screener
- [ ] Homestead — two-account paper trader
- [ ] Ranch House integration once both tools' data contracts are stable
- [ ] Live trading (Alpaca), gated behind the same code path Homestead's
      paper trading already uses
