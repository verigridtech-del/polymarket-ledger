# Polymarket BTC Auto Trader — Public Ledger

Automated trading bot for Polymarket's BTC 5-minute Up/Down prediction markets.

## What This Is

This repository is a **public, tamper-resistant record** of every trade made by the bot.

- All trades are logged automatically — wins and losses
- No manual edits. No cherry-picking results
- Updated every 30 minutes via cron

## What's Tracked

`daily_summary.txt` — Daily performance log (JST timezone)
```
2026-02-27 | PnL: $+7.44 | Balance: $59.61 | WR: 60% (3W 2L) [v3:5]
```

- **PnL**: Profit/loss for the day
- **Balance**: Running balance from initial capital
- **WR**: Win rate (Wins / Total)
- **[v3:5]**: Model version and number of trades

## How It Works

Three machine learning models (V1, V2, V3) run in parallel. Every few hours, all three retrain on the latest market data. The system automatically selects whichever model has the best statistical edge. No human decision-making involved.

Only LIVE trades with real money are recorded here. Dry-run / paper trades are excluded.

## Integrity

- **Branch protection is enabled**: force pushes and branch deletions are blocked
- Every commit is timestamped and cannot be retroactively removed
- This means past records cannot be altered or erased
- You can verify this under Settings > Branches > Branch protection rules

Initial capital: **$52.17**
Tracking start: **2026-02-26 21:08 JST**

## Links

- Daily updates posted on [X (Twitter)]https://x.com/verigrid_tech?s=21
- Bot runs 24/7 on Cloud

## Disclaimer

This is an experimental project. Past performance does not guarantee future results. This is not financial advice.
