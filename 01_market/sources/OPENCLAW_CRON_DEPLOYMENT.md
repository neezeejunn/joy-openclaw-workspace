# OpenClaw Cron Deployment Plan

## Goal
Map the market-report workflow onto concrete OpenClaw cron job types.

## Recommended Session Strategy
Use isolated cron jobs for this module.
Reason:
- avoids polluting the main session
- better for repeated checks
- easier to reason about delivery/no-delivery behavior

## Recommended Job Set
### Job A — Open Window
- schedule: cron
- time: 20:00 America/New_York on U.S. market weekdays
- sessionTarget: isolated
- delivery: none
- purpose: initialize market-day state and prepare monitoring

### Job B — Repeated Check
- schedule: cron
- times: every 30 minutes during the active window
- sessionTarget: isolated
- delivery: none by default
- purpose: detect same-day video, retrieve transcript, validate sources, generate report if all checks pass

### Job C — Close Window
- schedule: cron
- time: 02:00 America/New_York following the market day
- sessionTarget: isolated
- delivery: none
- purpose: close the market-day state and record failure reason if no transcript-backed comparison report exists

## Delivery Recommendation
Do not auto-deliver every run.
Instead:
- internal runs should use delivery none
- only the report-generation step should create a user-facing deliverable when it actually succeeds

## Output Recommendation
If the full formal comparison conditions are met:
- generate a daily report file under 01_market/daily/YYYY-MM-DD.md
- optionally deliver a concise summary to the user channel

If not met:
- update state only
- do not produce noisy user-facing output
