# Failure Modes

## 1. Scheduler exists but workflow does not execute
Symptoms:
- cron jobs visible
- no state files
- no reports generated

## 2. Transcript missing
Symptoms:
- sameDayVideoFound may be true
- transcriptAvailable remains false
- no formal comparison report

## 3. Source-date mismatch
Symptoms:
- sameDayValidationPassed remains false
- report generation blocked

## 4. Summary send blocked
Symptoms:
- report exists
- summarySent remains false

## Current Primary Failure
Scheduler exists, but workflow execution has not yet produced state artifacts.
