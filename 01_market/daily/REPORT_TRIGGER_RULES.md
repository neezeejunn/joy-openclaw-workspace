# Report Trigger Rules

## Trigger
A full post-market comparison report should trigger only when:
- It is a U.S. market weekday
- The monitoring window is active
- A same-day rhinofinance video is detected
- A same-day transcript is available
- Same-day market/news inputs are available

## Stop Condition
- Stop polling as soon as a valid same-day video with transcript is found and the report is generated
- Otherwise stop at post-market + 10h

## Output Types
### Type A: Full Comparison Report
Requirements:
- Same-day channel video
- Same-day transcript
- Same-day market/news sources

### Type B: No Formal YouTube Comparison
If the channel has no same-day video transcript within the monitoring window, do not force a comparison report.
Independent market analysis may still exist, but YouTube comparison should be marked unavailable.

## Reason
This preserves date integrity and avoids mixing stale commentary or non-transcript summaries with current market developments.
