# State Model for Market Report Automation

## Purpose
Prevent duplicate reports, track whether a valid same-day video was found, and record whether the day's monitoring is complete.

## Per-Market-Day State Fields
- marketDay
- monitoringStarted
- monitoringCompleted
- sameDayVideoFound
- sameDayVideoUrl
- sameDayVideoPublishTime
- sameDayValidationPassed
- reportGenerated
- reportPath
- stopReason

## Typical stopReason values
- report_generated
- no_same_day_video_by_deadline
- source_dates_unclear
- data_unavailable
- manual_skip

## Rules
1. Only one formal comparison report per market day.
2. If reportGenerated is true, do not poll again that day.
3. If monitoringCompleted is true, do not reopen monitoring for that market day.
4. If sameDayVideoFound is true but validation fails, record the failure reason.
