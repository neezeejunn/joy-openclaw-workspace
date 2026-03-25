# Executor: repeated-check

## Purpose
Check whether same-day video/transcript/source conditions are met and update state accordingly.

## Inputs
- current market-day state file
- same-day channel/video checks
- transcript status
- same-day source validation status

## Outputs
- updated state file
- optional trigger for report generation

## Required State Changes
- sameDayVideoFound
- sameDayVideoUrl
- sameDayVideoPublishTime
- transcriptAvailable
- transcriptStatus
- sameDayValidationPassed

## Success Condition
State file is updated to reflect the latest known conditions.
