# LapseHunter

Sweeps forgotten US patent filings and ranks the ones one person could build and sell today, with no workshop and no factory. Free to use.

**Live app:** https://7itb7.github.io/lapsehunter/

## What it does

1. **Sweep.** Pulls filing titles from the USPTO Open Data Portal across 18 product fields, in one of three modes:
   - **Term-expired**: filed 2001–2005, past the 20-year term. Patents still covered by a term extension are dropped automatically.
   - **Lapsed (fees)**: granted, then the owner stopped paying maintenance fees. Lapses from the last two years are flagged, because they can sometimes be revived.
   - **Never granted**: abandoned before a patent issued. Filings with a continuation that might still be alive are flagged.
2. **Score.** Claude scores every title on how makeable it is, how much today's tech changes things, demand, and whether it's still unsold. Each card shows what likely held the idea back in its filing year and what makes it easy now.
3. **Build sheet.** For any card, Claude reads the actual patent, checks whether it's already sold, and writes version 1, a parts list with costs, build steps, a price, the rules to check (FCC, CPSIA and so on) and a 48-hour test.

## Two ways to run Claude

- **Free: copy and paste (default).** The app queues the titles, most promising filers first. Tap **Copy batch**, paste it into a new chat in the Claude app, then paste Claude's reply back. Each round scores 40 titles. Build sheets work the same way; turn on web search in the Claude app so it can read the patent and check the market. Your Claude subscription covers this, with no extra cost.
- **Automatic: API key.** Hands-free, but Anthropic bills per use: about $0.65 for a Quick sweep with Opus 5.5, and $0.15–0.30 per build sheet. Switch to it in Settings.

## Setup

Open **Settings** and paste a free **USPTO Open Data Portal key** from https://data.uspto.gov/myodp. A brand-new key can take a few minutes to start working.

Keys are stored only in your browser's local storage. They are never in this repository.

## Caveats

The first score is a triage from the title alone. Before spending money on anything, open the Google Patents page and check **Legal status** and **Family**. This is not legal advice.

Single self-contained `index.html` with no build step and no external libraries.
