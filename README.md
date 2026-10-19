# Malaria funding tracker

**Live site:** https://health-funding-tracker.netlify.app

A country-by-country record of Global Fund allocations and US bilateral health agreements, built for anyone screening investments or programmes in malaria-endemic markets.

## Why I built it

Working on financing for health commodities in low- and middle-income countries, I kept needing the same answer: how much donor money is committed to a given country, and how much of it is for malaria? The figures exist, but they sit in different places, in different formats, and are often reported in ways that overstate what they show. Global Fund country totals get quoted as malaria figures. US agreement headlines mix US money with the partner country's own spending. Press releases round and hedge.

This tracker puts the published figures side by side and keeps them honest.

## What it shows

For every country with a Global Fund allocation in Grant Cycle 8 (2026-2028), and every country with a US health agreement:

- **Global Fund GC8 allocation**, split by HIV, TB and malaria, with the GC7 allocation for comparison
- **US bilateral health agreement** under the America First Global Health Strategy: US assistance, partner co-investment, signing date, programme areas, and whether malaria is named
- **US commitment against prior plan**: the agreement's five-year US figure next to planned US global health funding for FY2021-25

A malaria lens switches the main table to malaria components only.

## Rules

1. **Published figures only.** No estimates, no modelled values, no derived ratios.
2. **A blank means not published, not zero.**
3. **Different kinds of money are never added together.** A Global Fund allocation, a US appropriation and an agreement intention are different claims on future money.
4. **A country total is not a malaria figure.** The malaria component has its own column.
5. **Hedged figures are marked.** Where a source says "over" or "up to", the figure carries ≥ or ≤.
6. **Currency conversion uses the Global Fund's own published rate**, not one chosen here.
7. **Where a figure comes from another organisation's tracker, I take their published amounts and not their derived shares**, and credit them.

## Sources

| Source | What it provides |
|---|---|
| Global Fund GC8 allocation table | Allocations by country and disease component, GC8 and GC7 |
| KFF tracker of US bilateral health agreements | US and partner amounts, programme areas, signing dates, FY21-25 comparison |
| US State Department releases | Signed-country roster; amounts for agreements KFF has not yet added |
| Public Citizen | Agreement texts reported to Congress |

## Known limitations

- **US agreement amounts can't be split by disease.** Most cover HIV, TB, malaria, maternal and child health and health security together.
- **The GC7 comparison uses the allocation as communicated**, before any later reductions, so each fall is the largest available comparison.
- **Countries that left the Global Fund list between cycles** are marked either as moved into a multicountry programme or as having no allocation, rather than shown as a cut.

## How it's built

Two static files, no build step:

- `index.html`: the page layout and logic (React, loaded from a CDN)
- `data.js`: every figure, with its source

The site is hosted on Netlify and redeploys automatically whenever this repository changes.

## Updating

All data lives in `data.js`. Use `null` for anything not published; never `0`. Each row records its source.

Built and maintained by Pri. Last checked 19 October 2026.
