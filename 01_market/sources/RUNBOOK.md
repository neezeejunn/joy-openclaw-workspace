# Market Automation Runbook

## Current Status
- Scheduling exists
- State/report/send structure exists
- Workflow execution still needs to be bound to the cron jobs in a way that produces real artifacts

## Immediate Next Technical Goal
Get the automation to reliably create/update a state file for each market day.

## Why State First
If state files are not being written, there is no proof the workflow is actually executing.
State is the first non-negotiable artifact.

## After State Works
1. report generation
2. summary delivery

## Verification Checklist
- state file created
- state fields updated during polling
- report file generated when conditions pass
- summary sent only after report generation
