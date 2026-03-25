# Executor: generate-report

## Purpose
Write the market report file once conditions are satisfied.

## Inputs
- state file showing conditions passed
- market/news analysis inputs
- transcript-backed comparison inputs when available

## Outputs
- `01_market/daily/YYYY-MM-DD.md`
- updated state file with report path

## Required State Changes
- reportGenerated = true
- reportPath set
- stopReason = report_generated

## Success Condition
A report file exists and the state references it.
