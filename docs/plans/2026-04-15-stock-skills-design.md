# Stock Skills Design

## Goal

Create three English-language skills that preserve the practical `stockyy` stock-analysis workflow while making it reusable outside the original OpenClaw workspace.

## Approved Approach

Use a clean skills repository:

- `skills/company-deep-research/SKILL.md`
- `skills/sector-cycle-analysis/SKILL.md`
- `skills/kline-trend-analysis/SKILL.md`
- `skills/*/references/*.md` for heavier checklists and templates
- `harness/*/*.md` for pressure scenarios and expected behavior

## Source Workflow Requirements

The company research skill must preserve these `stockyy` rules:

- Clarify target, market, research purpose, horizon, risk tolerance, and existing position when missing.
- Prefer Claude/deep-research for research-grade work and 10+ source cross-checking.
- Use local search/data tools when available, especially searxng and AkShare-style latest-close retrieval.
- Every key claim must separate facts from inferences.
- Every report must include the latest completed trading-day close, date, source, and data method.
- Risk and disconfirming evidence must appear before final conviction.
- Output must be useful for research support only, not financial advice.

The sector-cycle skill must extend the existing `stockyy` cycle workflow into a reusable industry framework:

- Classify stage.
- Explain why with 1-3 evidence clusters.
- State what would disprove the call.
- Identify next indicators/events to monitor.
- Link the cycle call to position discipline and review cadence.

The K-line trend skill must turn visual chart reading into a repeatable process:

- Separate short-, medium-, and long-term horizons.
- Use price structure, moving averages, volume, momentum, support/resistance, and invalidation.
- Avoid deterministic predictions.
- Produce a probabilistic trend call with risk levels.

