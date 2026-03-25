# Execution Chain

## Goal
Turn cron triggers into a complete market-report pipeline.

## Layer 1: State
Every scheduled run should update a market-day state file under `01_market/state/YYYY-MM-DD.json`.
This is the first proof that execution actually happened.

## Layer 2: Report
When conditions are satisfied, generate a report under `01_market/daily/YYYY-MM-DD.md`.

## Layer 3: Send
Only after a report is generated should the system send a concise summary to the user.

## Rule
Do not attempt sending before report generation succeeds.
Do not mark a market day complete without state updates.
