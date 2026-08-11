# AQS-MarketFeed

Machine-generated, read-only market research data for AQS consumers. This public repository contains sanitized calculation results only; the MarketData source code and private configuration remain private.

## ChatGPT Read Contract

1. GET `latest/health.json`.
2. If `research_usable=true`, GET `latest/aqs_decision_bundle.json`.
3. Verify `run_id`, `as_of`, freshness, and the manifest checksum.
4. After market close, also require `discovery_usable=true` before using Discovery results.
5. `research_actionable=true` permits directional research actions even when `execution_usable=false`; exact prices, position sizes, fills, and automated trades remain forbidden.
6. This feed contains no user account, holdings, cost, order, or transaction data.

Read order: health → bundle → brief (optional). Use GitHub Pages first; Raw GitHub is the backup route.

Primary Pages endpoints:

- `https://jiawei-wang-dev.github.io/AQS-MarketFeed/latest/health.json`
- `https://jiawei-wang-dev.github.io/AQS-MarketFeed/latest/aqs_decision_bundle.json`
- `https://jiawei-wang-dev.github.io/AQS-MarketFeed/latest/health.html`
- `https://jiawei-wang-dev.github.io/AQS-MarketFeed/latest/bundle.html`

Backup Raw endpoints:

- `https://raw.githubusercontent.com/jiawei-wang-dev/AQS-MarketFeed/main/latest/health.json`
- `https://raw.githubusercontent.com/jiawei-wang-dev/AQS-MarketFeed/main/latest/aqs_decision_bundle.json`
- `https://raw.githubusercontent.com/jiawei-wang-dev/AQS-MarketFeed/main/latest/chatgpt_market_brief.md`
- `https://raw.githubusercontent.com/jiawei-wang-dev/AQS-MarketFeed/main/latest/manifest.json`

This is market research data only. It is not a personal portfolio, trade recommendation, account system, or automatic-trading service.
