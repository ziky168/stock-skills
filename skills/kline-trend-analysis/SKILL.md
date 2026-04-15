---
name: kline-trend-analysis
description: Use when judging short-term, medium-term, or long-term stock trend from K-line/candlestick charts, price structure, moving averages, volume, support/resistance, momentum, or breakout/failure patterns.
---

# K-Line Trend Analysis

## Overview

Use this skill to convert K-line/candlestick evidence into a probabilistic trend call across short, medium, and long horizons. The core rule is multi-timeframe confirmation: a short-term signal is weak if it fights the medium and long trend without a clear catalyst or reversal structure.

This is research support only, not financial advice.

## Required Inputs

If missing, infer and label assumptions:

- Ticker, exchange, market, and adjustment method.
- Data frequency: daily, weekly, monthly, or intraday.
- Lookback window and latest completed bar date.
- User horizon: short, medium, long, or all three.
- Whether the analysis is for entry, exit, risk control, or monitoring.

## Horizon Defaults

- **Short term:** 5-20 trading days, daily K-line, 5/10/20-day averages.
- **Medium term:** 1-3 months, daily plus weekly confirmation, 20/60-day averages.
- **Long term:** 6-12 months or more, weekly/monthly chart, 120/250-day averages.

Adjust these for market, liquidity, and user horizon.

## Required Workflow

1. **Validate data.** Use completed bars only. Note adjustment method, missing data, suspension, split/dividend effects, and unusual volume.
2. **Read structure first.** Identify higher highs/higher lows, lower highs/lower lows, range, gap, base, or failed breakout.
3. **Check moving averages.** Inspect slope, alignment, price position, and whether averages act as support/resistance.
4. **Check volume.** Confirm breakouts with expansion; treat low-volume breakouts and high-volume breakdowns carefully.
5. **Check momentum and volatility.** Use RSI/MACD/ATR/Bollinger only as secondary evidence, not standalone signals.
6. **Mark levels.** Name support, resistance, invalidation, and confirmation levels.
7. **Score each horizon.** Classify as bullish, neutral/range, weakening, or bearish with confidence.
8. **Synthesize.** Explain whether horizons align or conflict, then give a scenario plan.

## Output Contract

Minimum output:

- Data scope: ticker, frequency, adjustment, latest completed bar.
- Short-term trend call and invalidation.
- Medium-term trend call and invalidation.
- Long-term trend call and invalidation.
- Key support/resistance levels.
- Volume and momentum notes.
- Scenario plan: bullish confirmation, range continuation, bearish failure.
- Risk note: no deterministic prediction and not financial advice.

For the scoring grid, read `references/horizon-framework.md`.

## Common Mistakes

- Do not predict a price target from one candlestick pattern.
- Do not use intraday or incomplete candles as completed signals.
- Do not ignore volume on breakouts/breakdowns.
- Do not call a long-term reversal from a short-term bounce alone.
- Do not omit invalidation levels.

