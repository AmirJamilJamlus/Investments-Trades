# Morning brief automation

Hands-off research delivery for busy mornings. **Read-only.** Never places orders.

## What it should do

1. Open this repo in Cursor (Cloud Agent or Automation).
2. Read `portfolio/watchlist.yml`.
3. Use moomoo MCP with read scopes only (`quote:read`, and `trade:read` if positions are included).
4. Write `research/briefs/YYYY-MM-DD.md` from `research/briefs/_template.md`.
5. Include Teach-me sections and informational Shariah glances.
6. Optionally mention the current curriculum lesson from `learn/progress.yml`.

## What it must not do

- Place, modify, or cancel orders
- Enable Phase 3
- Hide tickers because of Shariah labels
- Invent prices when MCP is unavailable

## Suggested prompt

```text
Run the investing-desk morning brief.
Use moomoo MCP for live quotes on portfolio/watchlist.yml.
Write research/briefs/YYYY-MM-DD.md from the template.
Include plain English, terms, what to notice, what this does not prove,
informational Shariah notes, and one practice question.
Do not place any orders.
```

## OAuth note

Cloud Agent and Desktop Cursor may not share the same moomoo token. If the scheduled run cannot reach moomoo, it should write a brief that says data was unavailable instead of guessing. Use Desktop Cursor for any Phase 3 trading.
