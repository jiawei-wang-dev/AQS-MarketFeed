# AQS-MarketFeed

Machine-generated, read-only market research data for AQS consumers. This public repository contains sanitized calculation results only; the MarketData source code and private configuration remain private.

## ChatGPT Read Contract

1. GET `latest/health.json`.
2. If `research_usable=true`, GET `latest/aqs_decision_bundle.json`.
3. Verify `run_id`, market `as_of`, the three-clock freshness object, and the manifest checksum. Never infer market freshness from `feed_generated_at`; use `market_snapshot_as_of`, `market_snapshot_age_seconds`, and `market_data_stale`.
4. After market close, also require `discovery_usable=true` before using Discovery results.
5. `research_actionable=true` permits directional research actions even when `execution_usable=false`; exact prices, position sizes, fills, and automated trades remain forbidden.
6. This feed contains no user account, holdings, cost, order, or transaction data.
7. Check `sample_status`. `REPLAY_VALIDATION` is `validation_only=true` and never qualifies for forward-performance metrics. A scheduled sample is formally eligible only when `eligible_for_forward_metrics=true`.
8. `stock_discovery_summary.candidate_groups` describes the complete published Top20 distribution; `new_discoveries` is only a capped subset. `discovery_history` describes system novelty. `NEW_TO_USER` must be determined privately by ChatGPT Library.

Industry `rotation_state` and `market_state_summary` are deterministic market-fact classifications, not trading signals. Formal-close retries are observable through `formal_close.initial_attempt_at`, `last_attempt_at`, `retry_count`, `next_retry_at`, `cutoff_at`, `final_status`, `failure_reason`, `baseline_committed`, and `baseline_date`.

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
