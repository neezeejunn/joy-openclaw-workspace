# Executor Interface

## Goal
Define concrete execution units so automation can be verified through outputs rather than inferred from scheduling.

## Executor Contract
Each executor should define:
- purpose
- inputs
- output files
- state mutations
- success condition
- failure condition

## Required Output Rule
An executor is not considered working unless it produces an observable artifact.

## Core Executors
### open-window
- creates or initializes the market-day state file

### repeated-check
- updates state based on same-day video/transcript/source checks

### generate-report
- writes the report file when conditions pass

### send-summary
- sends a concise summary and records summary status

### close-window
- finalizes the state with stopReason if no successful report was generated
