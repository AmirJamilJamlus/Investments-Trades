# Shariah notes

This folder stores **informational** Shariah notes for tickers you research.

## How this works

1. The desk reads [`portfolio/shariah-policy.yml`](../portfolio/shariah-policy.yml).
2. When a symbol comes up, it writes a short note with a label such as `likely_ok`, `likely_concern`, `unclear`, or `needs_scholar`.
3. You always see the note. Nothing is hidden or blocked because of that label.

## What this is not

- Not a fatwa
- Not a certified Shariah board
- Not a guarantee that a stock is halal or haram
- Not a filter that removes tickers from research or trading

When the note says `unclear` or `needs_scholar`, treat that as homework, not as a machine ruling.

## Files

- `screens/` — per-symbol checklist notes
- `purification-log.md` — optional reminders if mixed income may need purifying
