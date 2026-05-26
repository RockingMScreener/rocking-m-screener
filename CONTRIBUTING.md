# Contributing to Rocking M Screener

Thank you for considering contributing to Rocking M Screener!  
This is an open-source, no-BS crypto screener built by a leather craftsman from Montana. We value honest input, practical improvements, and community-driven growth.

**All contributions are welcome** — code, documentation, filter presets, bug reports, design ideas, or just sharing what worked (or didn't) for you in the wild.

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

## Code of Conduct

Be honest, respectful, and constructive. We're building tools for regular traders in a noisy, sometimes scammy space — keep that spirit alive. 

**In short:** No hype, no toxicity, no shilling. We're here to help each other make better trading decisions.

## Ways to Contribute

You don't need to be a developer. Here's how anyone can help:

### Non-Code Contributions (Highly Valued)

- **Share filter presets** — Found a preset that consistently finds good tokens? Export as JSON and submit via [Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions) or [Issue](https://github.com/RockingMScreener/rocking-m-screener/issues)
- **Trade Journal outcomes** — Document what worked, what didn't, and why. This helps everyone learn.
- **Bug reports** — Found something broken? Tell us exactly what happened.
- **Real-world feedback** — Used the screener in live trading? What was confusing? What worked?
- **Documentation improvements** — Clearer explanations, typo fixes, better examples
- **Design & UI suggestions** — Colors, layout, usability improvements
- **Spread the word** — Tell traders you know about Rocking M

### Code Contributions

- New features or chain integrations
- UI/UX improvements
- Performance optimizations (especially multi-chain scans)
- Bug fixes
- Tests or better error handling
- Documentation or comment improvements

## Reporting Bugs

**Before submitting:** Check [existing issues](https://github.com/RockingMScreener/rocking-m-screener/issues) to avoid duplicates.

When reporting a bug, include:

1. **What you were doing** — Step-by-step reproduction
2. **What happened** — The error or unexpected behavior
3. **What you expected** — What should have happened
4. **Environment** — Browser, OS, chain(s) affected
5. **Screenshots** — If visual, grab a screenshot

**Example:**
> When I scan Solana with Min Liquidity set to $50K and Min Volume 24H set to $100K, the scan returns 0 results even though pools exist. No error message appears. Expected: scan completes and shows available pools or displays "no results found."

## Suggesting Features

Open a [GitHub Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions) or [Issue](https://github.com/RockingMScreener/rocking-m-screener/issues) and tell us:

1. **What problem does it solve?** — Why is this useful?
2. **How would it work?** — Be specific
3. **Any alternatives?** — Have you found workarounds?

**Example:**
> Feature: Export scan results to CSV  
> Problem: I want to save my scan results and analyze them in Excel for patterns  
> How: Add an "Export" button that downloads the current table as CSV with timestamp  
> Workaround: Currently I screenshot results manually

## Sharing Filter Presets

Found a filter preset that works well? Share it!

1. Open the screener and configure your filters
2. Right-click and select **"Inspect"** → **Console**
3. Copy the filter object from localStorage: `localStorage.getItem('presets')`
4. Paste it in a [Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions) with:
   - **Name** of the preset (e.g., "Solana Low Cap Gems")
   - **Chains** you used
   - **Filter values** (Min Liquidity, Max Age, etc.)
   - **Your results** — Did this find good tokens? Any wins or losses?

## Submitting Code

### Development Setup

The project is **100% client-side** (vanilla HTML, CSS, JavaScript) — no build tools or backend required.

1. **Fork & clone the repo:**
   ```bash
   git clone https://github.com/YOUR-USERNAME/rocking-m-screener.git
   cd rocking-m-screener
   ```

2. **Open in your browser:**
   - Simply open `screener.html`, `papertrader.html`, or `remi.html` in your browser
   - No npm install, no build step, no server needed

3. **Make your changes** in your favorite text editor (VS Code, Sublime, etc.)

4. **Test locally** — Refresh your browser to see changes immediately

### Pull Request Process

1. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make focused commits** — Keep related changes together
   ```bash
   git commit -m "Add feature: X" 
   git commit -m "Fix: Y"
   ```

3. **Push to your fork:**
   ```bash
   git push origin feature/your-feature-name
   ```

4. **Open a Pull Request** with:
   - **Clear title** — What does this do?
   - **Description** — Why? What problem does it solve?
   - **Testing notes** — How did you test this?
   - **Screenshots** — Before/after if UI changes

5. **Link related issues** — Use `Closes #123` to auto-link issues

6. **Respond to feedback** — We may ask questions or suggest changes

### Style Guide

**HTML/CSS/JavaScript:**
- Use clear, descriptive variable names (`tokenAddress` not `ta`)
- Add comments for complex logic
- Keep functions focused and small
- No minification (keep code readable)
- No external dependencies — vanilla JS only

**Commit messages:**
- Use present tense: "Add feature" not "Added feature"
- Be specific: "Fix honeypot detection for BSC" not "Fix bug"
- Reference issues: "Closes #42"

**Comments:**
- Explain *why*, not *what* — code shows what it does
- Keep them accurate (outdated comments are worse than no comments)

## Questions?

- **How do I...?** → Start a [Discussion](https://github.com/RockingMScreener/rocking-m-screener/discussions)
- **Found a bug?** → Open an [Issue](https://github.com/RockingMScreener/rocking-m-screener/issues)
- **Want to chat?** → Join our [Discord](https://discord.gg/aumVpSavB)

---

**Thank you for contributing to Rocking M.** Every honest effort — code, feedback, or shared knowledge — makes this tool better for everyone.

— Edward & the Rocking M community
