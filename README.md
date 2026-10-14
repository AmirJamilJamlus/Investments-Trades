# Investments and Trades workspace

Personal Cursor desk for moomoo research, beginner coaching, and informational Shariah notes. Built for a busy day job. The AI helps with tedious analysis. You keep the decisions.

## What this is

- **Cursor** is the coach and note-taker.
- **moomoo MCP** supplies live quotes, account reads, watchlist tools, and (later) orders.
- **This repo** stores watchlists, briefs, theses, proposals, lessons, and Shariah notes.

## What this is not

- Not unsupervised auto-trading
- Not a fatwa or Shariah certification service
- Not financial advice with guaranteed profits

## Quick start (local Cursor Desktop)

1. Open this folder in Cursor Desktop.
2. Confirm [`.cursor/mcp.json`](.cursor/mcp.json) points at `https://mcp.moomoo.com/mcp`.
3. In Cursor Settings → MCP, connect **moomoo-mcp** and finish the browser OAuth login.
4. Start with read scopes. `quote:read` and `trade:read` are enough for research.
5. Keep `trade:write` off until you intentionally enable Phase 3.

Official setup reference. [moomoo MCP Quick Start](https://open.moomoo.com/mcp-docs/quick-start)

### Smoke prompts

- What is the current stock price of Apple?
- What positions do I currently hold?
- Give me a morning brief on my watchlist.
- Shariah note on US.AAPL under my checklist.
- Explain that quote like I am new, then give me lesson 1’s practice question.

## How learning works

- Curriculum. [`learn/curriculum.md`](learn/curriculum.md)
- Glossary. [`learn/glossary.md`](learn/glossary.md)
- Progress. [`learn/progress.yml`](learn/progress.yml)

Ask for a **morning brief**, **next lesson**, or **quiz me**. Material answers should teach, not only report numbers.

## How Shariah notes work

- Checklist. [`portfolio/shariah-policy.yml`](portfolio/shariah-policy.yml)
- Mode. `notes_only`
- The desk **tells you** when something looks like a concern or is unclear.
- It does **not** hide or block tickers for that reason.

Details. [`shariah/README.md`](shariah/README.md)

## Phases

| Phase | You get | Orders |
| --- | --- | --- |
| 1 | MCP connected, coaching, glossary | No |
| 2 | Watchlist, briefs, proposals, lessons | No (drafts only) |
| 3 | Risk-limit gate + your approve phrase | Yes, after confirmation |

Phase 3 risk file. [`portfolio/risk-limits.yml`](portfolio/risk-limits.yml)  
Skill with the order gate. [`.cursor/skills/investing-desk/SKILL.md`](.cursor/skills/investing-desk/SKILL.md)  
Scheduled brief (read-only). [`automation/morning-brief.md`](automation/morning-brief.md)

## Repo map

```text
.cursor/mcp.json                 moomoo MCP endpoint
.cursor/rules/moomoo-trading.mdc desk rules
.cursor/skills/investing-desk/   coach skill
portfolio/                       watchlist, risk limits, shariah checklist
research/                        briefs, theses, proposals, journal
learn/                           glossary, curriculum, lessons
shariah/                         informational screen notes
automation/                      morning brief instructions
```

## Suggested first week

1. Connect moomoo OAuth and run the smoke prompts.
2. Edit `portfolio/watchlist.yml` to names you actually care about.
3. Run one morning brief.
4. Complete lessons 1 to 3 when you have spare minutes.
5. Leave Phase 3 off until the coaching loop feels natural.
