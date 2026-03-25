# Executor: close-window

## Purpose
Finalize the market-day state when the monitoring window ends.

## Inputs
- current state file

## Outputs
- updated state file

## Required State Changes
- monitoringCompleted = true
- stopReason set if report not generated

## Success Condition
A final state file exists describing the outcome of the market day.
