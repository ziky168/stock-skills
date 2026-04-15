# Data Playbook (Company Deep Research)

Use this when a “research-grade” report must be reproducible, or when preferred SDK-based data pulls are unavailable.

## 1. Primary Source First (CNINFO)

- Fetch the full annual report PDF (CNINFO `static.cninfo.com.cn` typically hosts stable PDFs).
- Extract and record:
  - Revenue, net profit, operating cash flow, ROE.
  - Segment revenue and margins (by product and by geography if available).
  - Domestic vs overseas revenue share.
  - Risk disclosures (macro, commodity, FX, receivable/credit, competition).

## 2. Latest Close Integrity Rule

The report must include the latest completed trading-day close with:

- date
- close price
- source
- method

If you cannot verify the true latest trading-day close:

- state “latest verified close = …”
- state “latest trading day close = pending verification”
- provide the fastest verification path (quote page export, broker app screenshot, or an SDK pull once dependencies are fixed)

## 3. Fallback Ladder for Price Data

Preferred:

- AkShare daily history (completed bars).

Fallback:

- Use a reputable quote provider page that shows daily close with a date.
- If only dynamic real-time quotes are available, do not treat them as the required “latest close”.

## 4. Cache Convention (Recommended)

Cache under a deterministic path:

```text
data/<ticker>/<report-date>/
  annual_report.pdf
  key_figures.json
  prices.csv
  notes.md
```

Minimum `key_figures.json` fields:

- report_date
- currency
- revenue
- net_profit
- operating_cash_flow
- capex_cash (if available)
- overseas_revenue
- overseas_share
- segments: list of {name, revenue, margin}
- leverage: {asset_liability_ratio, short_term_debt, long_term_debt}

## 5. K-Line Without SDK

If you cannot pull daily bars via an SDK:

- request/export a daily-bar CSV for at least 250 trading days
- compute MA/ATR/RSI locally
- document the data source and the exact date range

## 6. Vendored Helper Skills (This Repo)

This repository includes:

- `skills/deep-research`
- `skills/akshare-stock`

Notes:

- The deep-research `scripts/research_engine.py` is a pipeline/checklist driver; in agent runtimes it’s usually invoked as a skill to actually perform retrieval + synthesis.
- The akshare-stock skill expects `akshare` installed in its Python runtime (commonly Python 3.9). If `akshare` import fails, you must use the fallback ladder above or install dependencies explicitly (do not assume they exist).
