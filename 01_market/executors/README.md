# Market Executors

This directory defines the execution units that cron should trigger.

## Why
Cron scheduling alone is not sufficient. Each scheduled event needs a concrete executor that produces file-based side effects.

## Planned Executors
- open-window
- repeated-check
- close-window
- generate-report
- send-summary

## Principle
Executors should create observable artifacts:
- state updates
- report files
- summary-send records
