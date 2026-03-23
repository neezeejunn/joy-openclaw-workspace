# State and Output Paths

## Proposed State Location
- 01_market/state/
- one state file per market day

## Proposed Naming
- 01_market/state/2026-03-23.json
- 01_market/daily/2026-03-23.md

## Reason
This keeps:
- state separate from reports
- one market day = one state record
- cron jobs idempotent and easier to debug
