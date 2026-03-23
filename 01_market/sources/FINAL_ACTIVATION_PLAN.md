# Final Activation Plan

## Intended Behavior
### Success path
1. Monitor the target channel in the post-market window
2. Detect a same-day video
3. Attempt transcript retrieval
4. If transcript is available and same-day market/news sources validate, generate a formal comparison report
5. Save the full report under 01_market/daily/YYYY-MM-DD.md
6. Send a concise Telegram summary

### Transcript-failure path
1. If no transcript is available, do not generate a formal YouTube comparison
2. If market/news analysis quality is sufficient, still generate an independent market report
3. Mark the report: no_formal_youtube_comparison
4. Save the report file
5. Optionally send Telegram summary of the independent report

### Insufficient-data path
1. If overall market/news data quality is too weak, generate no formal report
2. Update state only
3. Stay quiet

## Activation Prerequisites
Before cron activation, verify:
- transcript retrieval path is trustworthy enough
- state file writing is defined
- report generation behavior is deterministic enough
- Telegram delivery format is decided
