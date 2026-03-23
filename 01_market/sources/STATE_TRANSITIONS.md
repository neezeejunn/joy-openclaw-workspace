# State Transitions

## Initial
- monitoringStarted = false
- monitoringCompleted = false
- reportGenerated = false

## Open Window
Trigger: Job A runs
Transition:
- monitoringStarted -> true

## Polling Active
Trigger: Job B runs during active window
Possible transitions:
- sameDayVideoFound -> true
- transcript retrieval status updated
- sameDayValidationPassed -> true
- reportGenerated -> true
- stopReason -> report_generated

## Completed Successfully
Condition:
- reportGenerated = true
- monitoringCompleted may later become true but should not change success state

## Completed Without Formal Comparison
Condition:
- deadline reached with no same-day transcript-backed report
Possible stop reasons:
- no_same_day_video_by_deadline
- no_same_day_transcript_by_deadline
- source_dates_unclear
- data_unavailable

## Terminal Rule
Once monitoringCompleted = true for a market day, do not reopen that market day.
