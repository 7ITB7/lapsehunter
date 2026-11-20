# LapseHunter

Sweeps forgotten US patent filings and ranks the ones one person could build and sell today, with no workshop and no factory.

**Live app:** https://7itb7.github.io/lapsehunter/

## What it does

1. **Sweep.** Pulls filing titles from the USPTO Open Data Portal across 18 product fields, in one of three modes:
   - **Term-expired**: filed 2001–2005, past the 20-year term. Patents still covered by a term extension are dropped automatically.
   - **Lapsed (fees)**: granted, then the owner stopped paying maintenance fees. Lapses from the last two years are flagged, because they can sometimes be revived.
   - **Never granted**: abandoned before a patent issued. Filings with a continuation that might still be alive are flagged.
2. **Triage.** Claude (Opus 5.5 by default) scores every title on how makeable it is, how much today's tech changes things, demand, and whether it's still unsold. Each card shows what likely held the idea back in its filing year and what makes it easy now.
3. **Build sheet.** On any card, Claude reads the actual patent page, searches whether it's already sold, and writes version 1, a parts list with costs, build steps, price, the rules to check (FCC, CPSIA and so on) and a 48-hour test.

## Setup

Open **Settings** in the app and paste:

- A **USPTO Open Data Portal key** (free) from https://data.uspto.gov/myodp
- An **Anthropic API key** from https://console.anthropic.com

The keys are stored only in your browser's local storage. They are never in this repository.

## Rough costs (Anthropic API)

- Quick sweep: about $0.60 with Opus 5.5
- Standard sweep: about $1.25
- Deep sweep: about $2.50
- Build sheet: about $0.15–0.30 each

The header shows what you've actually spent on the device.

## Caveats

The first score is a triage from the title alone. Before spending money on anything, open the Google Patents page and check **Legal status** and **Family**. This is not legal advice.

Single self-contained `index.html` with no build step and no external libraries.
