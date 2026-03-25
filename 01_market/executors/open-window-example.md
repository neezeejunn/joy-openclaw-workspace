# Open-Window Example Outcome

## Expected Artifact
When the open-window executor is functioning, it should create:
- `01_market/state/YYYY-MM-DD.json`

## Minimum Initial State
- marketDay set
- monitoringStarted = false or true depending on execution timing
- monitoringCompleted = false
- reportGenerated = false
- summarySent = false

## Why this matters
This is the first observable proof that the workflow is writing files rather than existing only as scheduler metadata.
