# Report Trigger Rules

## Trigger
A full post-market comparison report should trigger only when:
- It is a U.S. market weekday
- The monitoring window is active
- A same-day rhinofinance video is detected
- Same-day market/news inputs are available

## Stop Condition
- Stop polling as soon as a valid same-day video is found
- Otherwise stop at post-market + 10h

## Output Types
### Type A: Full Comparison Report
Requirements:
- Same-day channel video
- Same-day market/news sources

### Type B: No Report
If the channel has no same-day video within the monitoring window, do not force a comparison report.

## Reason
This preserves date integrity and avoids mixing stale commentary with current market developments.
