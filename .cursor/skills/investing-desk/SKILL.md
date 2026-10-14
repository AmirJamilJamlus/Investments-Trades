---
name: investing-desk
description: Personal moomoo investing desk. Morning briefs, beginner teaching, informational Shariah notes, draft proposals, and Phase 3 order gate.
---

# Investing desk

Use this skill whenever the user asks for research, briefs, lessons, Shariah notes, trade ideas, or orders in this repo.

## Data shapes

- **WatchItem** in `portfolio/watchlist.yml`
- **RiskLimits** in `portfolio/risk-limits.yml`
- **Shariah checklist** in `portfolio/shariah-policy.yml` (`mode: notes_only`)
- **Brief / Thesis / TradeProposal / Journal** under `research/`
- **ShariahNote** under `shariah/screens/`
- **LessonProgress** in `learn/progress.yml`

## Core loop (Phases 1 to 2)

1. Pull live facts from moomoo MCP. Do not invent quotes or positions.
2. Teach one useful idea in beginner language.
3. Attach informational Shariah notes. Never filter or refuse for Shariah status.
4. Write or update files using the templates under `research/` and `shariah/`.
5. If the user asks to buy or sell, create a **draft** proposal. Do not place an order.

## Commands

- **Morning brief.** Read watchlist, fetch quotes, write `research/briefs/YYYY-MM-DD.md` from the template.
- **Should I buy X?** Draft `research/proposals/...` with learner rationale and Shariah notes. Stop for approval. No order in Phase 1 to 2.
- **Shariah note on X.** Write or update `shariah/screens/...`. Keep X on the watchlist regardless of label.
- **Explain like I am new.** Slow down. Define terms. One concept at a time.
- **Quiz me.** Short oral quiz using watchlist or recent brief.
- **Next lesson.** Use `learn/curriculum.md` and update `learn/progress.yml` when a practice question is completed.

## Required sections in material answers

Plain English summary. Terms used. What to notice. What this does not prove. Shariah notes. One practice question.

Append new glossary terms to `learn/glossary.md`.

## Phase 3 order gate

Only when the user has explicitly enabled Phase 3 in the conversation and `portfolio/risk-limits.yml` is respected.

Before any place or cancel order tool call:

1. Re-read `portfolio/risk-limits.yml`.
2. Show a confirmation card with symbol, side, quantity, limit price, estimated notional, risk-limit pass/fail, and the current Shariah note label (visible, not blocking).
3. Teach-back. Ask the user to confirm in their own words why the order fits their thesis and size limits.
4. Wait for the exact approve phrase from `risk-limits.yml` (default `approve order`).
5. Only then call the moomoo trade tool.
6. After fill or cancel, write a journal entry from `research/journal/_template.md`.

Refuse market orders unless `allow_market_orders` is true. Refuse options, futures, shorting, and margin while those flags are false.

Shariah `likely_concern` or `unclear` must still appear on the confirmation card. Do not auto-reject for that reason.

## Safety

- Default posture is no orders.
- Confirm tickers before watchlist changes.
- Missing Shariah fundamentals mean `unclear`, not `likely_ok`.
- Not financial advice with guaranteed outcomes. Not a fatwa.
