# PolyBot v5 — Polymarket Market Maker Journal

> Open-source market maker running live on Polymarket with $61.34 starting capital.
> Day 0: 2026-03-09

## Current Status (Day 0)

| Metric | Value |
|--------|-------|
| Portfolio Value | $61.34 |
| ROI | +0.0% |
| Total Fills | 0 |
| Adverse Selection Rate | 0% |
| Active Positions | 1 |

## Strategy

PolyBot v5 is an adaptive Polymarket market maker with data-driven quote protection:

- **Spread band filter**: Only quotes when spread is 0.05-0.15 (medium liquidity)
- **Post-fill cooldown**: 60s pause after each fill to avoid stale-price pickoffs
- **Inventory direction lock**: No same-side accumulation (reduces adverse selection from 83% to near 0%)

## Daily Reports

| Day | Date | Portfolio | ROI | Fills | Adverse Rate |
|-----|------|-----------|-----|-------|-------------|
| 0 | 2026-03-09 | $61.34 | +0.0% | 0 | 0% |

## Research Journey

This project evolved through systematic research:

1. **ML prediction** → NO (zero predictive power, all features corr < ±0.01)
2. **Binance→Polymarket lead-lag** → NO (correlations near zero)
3. **Jump-fade arbitrage** → Edge exists but execution impossible (spread = 0.98)
4. **Market making with quote protection** → Current approach (v5)

Key insight: The edge is not in *predicting* prices, but in *providing liquidity safely*.

## Architecture

- Python bot on EC2 (Ireland)
- Polymarket CLOB API for order management
- 15-second quote cycle with adaptive regime classification
- Fill Impact Engine tracks post-fill price movement at 5s/15s/60s

## License

MIT
