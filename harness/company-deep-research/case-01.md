# Harness Case: Company Deep Research

## Prompt

Research Zoomlion `000157.SZ` as a long-term value-investing candidate. Use deep research if available and produce a full company report.

## Required Behaviors

- The agent invokes `company-deep-research`.
- The report states ticker, exchange, report date, and latest completed trading-day close.
- Major claims are labeled `Fact` or `Inference`.
- The agent uses or attempts deep-research for multi-source validation.
- The report covers industry, business model, moat, financial quality, governance, valuation, safety margin, and risks.
- Valuation bands are only presented if the cash-flow anchor is supportable.
- Risks and disconfirming signals are explicit.
- The report says it is research support only, not financial advice.

## Failure Modes

- Uses intraday price as latest close.
- Produces a bullish conclusion without risk-first framing.
- Provides DCF price bands despite unstable or missing free cash flow.
- Mixes source facts and analyst interpretation without labels.
- Omits source list or data method.

## Expected Output Skeleton

```markdown
# 000157.SZ Zoomlion Company Deep Research

- Report date:
- Latest completed trading-day close:
- Research purpose:
- Disclaimer:

## Executive View
Fact:
Inference:
Disconfirming signals:

## Company Profile
## Industry Analysis
## Business Model and Moat
## Financial Analysis
## Governance
## Valuation
## Risks
## Watchlist
## Bibliography
```

