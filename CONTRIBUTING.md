# Contributing to Rocking M Screener

Thank you for considering contributing to Rocking M Screener!

This is an open-source, no-BS crypto trading suite built by a leather craftsman from Montana. We value honest input, practical improvements, and community-driven growth.

All contributions are welcome — code, documentation, filter presets, bug reports, design ideas, or just sharing what worked (or didn't) for you in the wild.

---

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [Ways to Contribute](#ways-to-contribute)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)
- [Submitting Code](#submitting-code)
- [Sharing Filter Presets](#sharing-filter-presets)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guide](#style-guide)

---

## Code of Conduct

Be honest, respectful, and constructive. We're building tools for regular traders in a noisy, sometimes scammy space — keep that spirit alive.

In short: **No hype, no toxicity, no shilling.** We're here to help each other make better trading decisions.

---

## Ways to Contribute

You don't need to be a developer. Here's how anyone can help:

### Non-Code Contributions (Highly Valued)
- **Share filter presets** — Found settings that consistently find good tokens? Export as JSON and share via Discussion or Issue
- **Trade journal outcomes** — Document what worked, what didn't, and why. This helps everyone learn
- **Bug reports** — Found something broken? Tell us exactly what happened
- **Real-world feedback** — Used the tools in live trading? What was confusing? What worked?
- **Documentation improvements** — Clearer explanations, typo fixes, better examples
- **Design & UI suggestions** — Colors, layout, usability improvements
- **Spread the word** — Tell traders you know about Rocking M

### Code Contributions
- New features or chain integrations
- UI/UX improvements
- Performance optimizations
- Bug fixes
- Tests or better error handling
- Documentation or comment improvements

---

## Reporting Bugs

Before submitting: Check existing issues to avoid duplicates.

When reporting a bug, include:

- **What you were doing** — Step-by-step reproduction
- **What happened** — The error or unexpected behavior
- **What you expected** — What should have happened
- **Environment** — Browser, OS, wallet, chain(s) affected
- **Screenshots** — If visual, grab a screenshot

**Example:**

> When running Forge in Trending mode with Min Liquidity set to $25K and Min Score set to 60, the scanner returns 0 candidates after 5 cycles even though GeckoTerminal shows active trending pools. No error message appears. Expected: candidates are found and scored, or a "no results" message is shown.

---

## Suggesting Features

Open a GitHub Discussion or Issue and tell us:

- **What problem does it solve?** — Why is this useful?
- **How would it work?** — Be specific
- **Any alternatives?** — Have you found workarounds?

**Example:**

> Feature: Price alert notifications
> Problem: I want to know when a watched token hits a target price without watching the screen
> How: Add a browser notification when a position hits TP1 or drops below stop loss
> Workaround: Currently I watch the event log manually

---

## Sharing Filter Presets

Found settings that work well in a specific mode? Share them!

1. Configure your settings in any tool (Forge, Cipher, Stormchaser, Craftsman)
2. Use the **Export** button to download your session as a JSON file
3. Share it in a Discussion with:
   - Name of the preset (e.g., "Forge Trending Conservative")
   - Which tool and scan mode you used
   - Your filter values (Min Liquidity, Min Score, Age settings, etc.)
   - Your results — Did this find good tokens? Any wins or losses?

---

## Development Setup

The entire suite is 100% client-side — vanilla HTML, CSS, and JavaScript. No build tools, no backend, no npm required.

### Tools in the suite:
| File | Tool | Description |
|------|------|-------------|
| `forge.html` | Forge V2.0 | Solana real-money trader |
| `cipher.html` | Cipher | Multi-chain token screener |
| `stormchaser.html` | Stormchaser | AI paper trader |
| `craftsman.html` | Craftsman | Paper trading environment |
| `ranch-house.html` | Ranch House | Suite dashboard |
| `trailguide.html` | Trail Guide / Remi | AI assistant |

### Getting started:

**Fork & clone the repo:**
```bash
git clone https://github.com/YOUR-USERNAME/rocking-m-screener.git
cd rocking-m-screener
```

**Open in your browser:**
```
Simply open any .html file directly in your browser
No npm install, no build step, no server needed
```

**Make your changes** in any text editor (VS Code, Sublime, etc.)

**Test locally** — Refresh your browser to see changes immediately

> Note: Forge requires a Cloudflare Worker proxy for Jupiter API access and a Helius RPC key for Solana transactions. See the README for setup details.

---

## Pull Request Process

1. **Create a feature branch:**
```bash
git checkout -b feature/your-feature-name
```

2. **Make focused commits:**
```bash
git commit -m "Add feature: X"
git commit -m "Fix: Y"
```

3. **Push to your fork:**
```bash
git push origin feature/your-feature-name
```

4. **Open a Pull Request with:**
   - Clear title — What does this do?
   - Description — Why? What problem does it solve?
   - Testing notes — How did you test this?
   - Screenshots — Before/after if UI changes
   - Link related issues — Use `Closes #123` to auto-link issues

5. **Respond to feedback** — We may ask questions or suggest changes

---

## Style Guide

### HTML/CSS/JavaScript:
- Use clear, descriptive variable names (`tokenAddress` not `ta`)
- Add comments for complex logic
- Keep functions focused and small
- No minification — keep code readable
- No external dependencies — vanilla JS only
- No frameworks — the suite runs without React, Vue, or any build step

### Commit messages:
- Use present tense: `"Add feature"` not `"Added feature"`
- Be specific: `"Fix honeypot detection threshold for micro-cap tokens"` not `"Fix bug"`
- Reference issues: `"Closes #42"`

### Comments:
- Explain **why**, not what — code shows what it does
- Keep them accurate — outdated comments are worse than no comments

---

## Questions?

- **How do I...?** → Start a [Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions)
- **Found a bug?** → Open an [Issue](https://github.com/RockingMScreener/rocking-m-screener/issues)
- **Follow updates** → [@Rocking M Suite llc](https://x.com/rockingmscreener) on X

---

Thank you for contributing to Rocking M. Every honest effort — code, feedback, or shared knowledge — makes these tools better for everyone.

— Edward & the Rocking M community
