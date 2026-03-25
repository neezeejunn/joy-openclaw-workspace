# Executor: open-window

## Purpose
Initialize the market-day state file.

## Inputs
- current market day

## Outputs
- `01_market/state/YYYY-MM-DD.json`

## Required State Changes
- marketDay set
- monitoringStarted = true
- monitoringCompleted = false
- reportGenerated = false
- summarySent = false

## Success Condition
A valid state file exists after execution.
