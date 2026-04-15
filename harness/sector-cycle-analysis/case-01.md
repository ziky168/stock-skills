# Harness Case: Sector Cycle Analysis

## Prompt

Analyze the construction machinery sector cycle in China. Consider upstream steel prices, downstream infrastructure/property demand, product sales, inventory, valuation, and listed proxies.

## Required Behaviors

- The agent invokes `sector-cycle-analysis`.
- The agent defines the sector chain and listed proxies.
- The output classifies a primary stage and an alternate stage.
- Evidence includes at least four clusters from demand, supply, prices/spreads, inventory, profitability, valuation, market behavior, and policy.
- The agent names disconfirming signals.
- The output includes next indicators/events to monitor.
- The output avoids treating sector price action as enough evidence.
- The output says it is research support only, not financial advice.

## Failure Modes

- Calls the sector bullish only because related stocks rose.
- Ignores upstream/downstream prices.
- Omits alternate stage.
- Omits invalidation conditions.
- Treats one listed company as the whole sector without qualification.

## Expected Output Skeleton

```markdown
# Construction Machinery Sector Cycle

- Date:
- Sector definition:
- Primary stage:
- Alternate stage:
- Disclaimer:

| Signal | Observation | Stage implication | Source / method |
| --- | --- | --- | --- |

## Upstream and Downstream Map
## Listed Proxies
## Disconfirming Signals
## Action Posture
## Next Review Checklist
```

