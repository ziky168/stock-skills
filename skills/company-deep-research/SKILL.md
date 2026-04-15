---
name: company-deep-research
description: Use when producing a research-grade single-company stock memo, valuation report, or investment-style company analysis that requires multiple sources, financial quality, risk review, and an explicit fact-versus-inference split.
---

# Company Deep Research

## Overview

Use this skill to produce a research-support report for one listed company. The core rule is evidence discipline: every important claim must be sourced, labeled as `Fact` or `Inference`, and tied to what would disprove it.

This is research support only, not financial advice.

## Before Research

If missing, clarify or state assumptions for:

- Company name, ticker, exchange, and market.
- Research purpose: build position, add, hold, follow-up, or full report.
- Horizon: short term, medium term, long term, or value-investing deep dive.
- Risk tolerance and whether there is an existing position/cost basis.
- Required output length and destination.

Do not wait if the user explicitly asks for harness/autonomous execution. Make reasonable assumptions and label them.

## Tool Priority

- Prefer Claude/deep-research when the user requests deep research, research-grade output, or 10+ source cross-checking.
- Prefer local searxng search when available for web search, especially in environments that prohibit Brave-style web search.
- Prefer AkShare-style historical daily data, with fallback sources, for the latest completed trading-day close.
- Use local market-data tools when available for price, financial statement, and share-count data.
- Use official filings, annual reports, exchange announcements, company IR pages, and reputable data providers before media summaries.
- If a preferred tool is unavailable, say so briefly and use the best available fallback.

## Required Workflow

1. **Define scope.** Confirm ticker, market, report date, research purpose, and assumed horizon.
2. **Collect primary facts.** Gather filings, financial statements, segment revenue, share count, latest completed trading-day close, and corporate actions.
3. **Run deep research.** Cross-check industry, competition, governance, risks, and recent events. Target at least 10 sources for a full report.
4. **Separate facts and inferences.** Prefix important statements with `Fact:` or `Inference:`. Inferences need assumptions and reasoning.
5. **Analyze the business.** Cover industry, business model, moat, customers, pricing power, cyclicality, and management/governance.
6. **Analyze financial quality.** Use at least 5 years when available: revenue, profit, margins, ROE, operating cash flow, free cash flow, leverage, receivables, and inventory.
7. **Value the company.** Use DCF when cash flow is usable. If free cash flow is unstable or negative, explain why and use scenario/comparable/unit-economics methods instead.
8. **Build action bands.** Provide buy/watch/reduce/avoid bands only when the valuation anchor is supportable. Otherwise state what data is missing before bands are reliable.
9. **Lead with risk.** State key risks, disconfirming signals, and what would change the conclusion.
10. **Cite sources.** Include source names, dates, links or local file paths, and data methods.

## Output Contract

Full reports should follow `references/report-template.md`.

Minimum output:

- Conclusion and rating posture.
- Latest completed trading-day close: date, close price, source, and method.
- Business and industry thesis.
- Financial quality summary.
- Valuation anchor and sensitivity.
- Risks and disconfirming signals.
- Watchlist indicators.
- Bibliography or source list.

## Common Mistakes

- Do not use a live intraday quote as the required latest close.
- Do not present valuation bands if the cash-flow anchor is not credible.
- Do not mix facts and interpretations without labels.
- Do not bury major risks after a bullish narrative.
- Do not claim certainty; use scenarios and invalidation points.
