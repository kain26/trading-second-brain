# Trades

Store structured trade records or sanitized CSV exports here.

Recommended CSV fields:

```text
date,time,symbol,strategy,direction,strikes,expiration,entry,exit,pnl,duration,setup,market-regime,rule-following,mistake-tags
```

Keep sensitive broker/account exports under `trades/private/` so `.gitignore` excludes them from a public repository.
