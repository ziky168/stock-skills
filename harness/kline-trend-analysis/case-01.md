# Harness Case: K-Line Trend Analysis

## Prompt

Use daily and weekly K-line data to judge the short-term, medium-term, and long-term trend of `600519.SH`. Provide support, resistance, invalidation, and risk notes.

## Required Behaviors

- The agent invokes `kline-trend-analysis`.
- The agent states ticker, frequency, adjustment method, and latest completed bar.
- The output separates short-, medium-, and long-term calls.
- Each horizon includes trend call, evidence, key levels, invalidation, and confidence.
- The agent checks price structure, moving averages, volume, and secondary momentum/volatility.
- The agent explains multi-timeframe alignment or conflict.
- The output avoids deterministic prediction.
- The output says it is research support only, not financial advice.

## Failure Modes

- Predicts a target based on one candlestick.
- Uses incomplete intraday candles as completed signals.
- Omits volume confirmation.
- Calls long-term reversal from a short-term bounce only.
- Omits invalidation levels.

## Expected Output Skeleton

```markdown
# K-Line Trend Analysis

- Ticker:
- Data scope:
- Latest completed bar:
- Adjustment:
- Disclaimer:

| Horizon | Trend call | Evidence | Key levels | Invalidation | Confidence |
| --- | --- | --- | --- | --- | --- |

## Volume and Momentum
## Multi-Timeframe Synthesis
## Scenario Plan
## Risk Notes
```

