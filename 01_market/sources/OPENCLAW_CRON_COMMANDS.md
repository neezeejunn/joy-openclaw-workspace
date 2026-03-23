# OpenClaw Cron Command Sketches

## Note
These are deployment sketches, not yet executed commands.
They document the intended cron shape for later activation.

## Job A — Open Window
```bash
openclaw cron add \
  --name "Market Open Window" \
  --cron "0 20 * * 1-5" \
  --tz "America/New_York" \
  --session isolated \
  --message "Initialize the U.S. market-day monitoring window for the current market day. Update the market module state file. Do not send user-facing output." \
  --no-deliver
```

## Job B — Repeated Check
Example split-cron approach (recommended over a single everyMs loop):
```bash
openclaw cron add \
  --name "Market Repeated Check" \
  --cron "0,30 20-23 * * 1-5" \
  --tz "America/New_York" \
  --session isolated \
  --message "Check rhinofinance for a same-day market-analysis video. Attempt transcript retrieval. If transcript is unavailable, record transcript_unavailable and exit quietly. If transcript and same-day source validation succeed, generate the formal market report and stop further work for this market day." \
  --no-deliver
```

Second cross-midnight check job:
```bash
openclaw cron add \
  --name "Market Repeated Check After Midnight" \
  --cron "0,30 0-1 * * 2-6" \
  --tz "America/New_York" \
  --session isolated \
  --message "Continue monitoring the previous U.S. market day until 02:00 ET. Respect market-day state and do not reopen completed days." \
  --no-deliver
```

## Job C — Close Window
```bash
openclaw cron add \
  --name "Market Close Window" \
  --cron "0 2 * * 2-6" \
  --tz "America/New_York" \
  --session isolated \
  --message "Close the prior U.S. market-day monitoring window. If no same-day transcript-backed comparison report exists, mark monitoring completed and record the stop reason. Do not send user-facing output." \
  --no-deliver
```

## Why split the repeated checks
Because the monitoring window crosses midnight in New York time.
Splitting the cron schedule keeps the market-day logic cleaner.
