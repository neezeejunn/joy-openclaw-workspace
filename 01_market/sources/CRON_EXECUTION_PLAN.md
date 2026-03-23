# Cron Execution Plan

## Goal
Translate the market-monitoring design into an execution-ready plan for scheduled automation.

## Conceptual Jobs
### Job A: Open market-day window
Purpose:
- initialize market-day state
- mark monitoringStarted = true
- prepare the report workspace for the target market day

### Job B: Repeated channel/transcript check
Purpose:
- run every 30 minutes during the active window
- exit quietly if state already says completed or reportGenerated
- detect same-day video
- attempt transcript retrieval
- if transcript retrieval fails, record transcript_unavailable for that check
- if transcript retrieval succeeds and same-day source validation passes, generate formal report

### Job C: Close market-day window
Purpose:
- mark monitoringCompleted = true if deadline has passed
- if no valid transcript-backed report was generated, record stopReason accordingly

## Recommended Behavior
- All jobs should be idempotent
- Repeated checks should never duplicate a finished report
- The close job should never overwrite a successful report state
- Independent market analysis can exist separately, but formal YouTube comparison requires transcript-backed success

## State Updates
### Job A writes
- marketDay
- monitoringStarted = true
- monitoringCompleted = false

### Job B may write
- sameDayVideoFound
- sameDayVideoUrl
- sameDayVideoPublishTime
- transcript retrieval status
- sameDayValidationPassed
- reportGenerated
- reportPath
- stopReason = report_generated

### Job C may write
- monitoringCompleted = true
- stopReason = no_same_day_transcript_by_deadline OR no_same_day_video_by_deadline
