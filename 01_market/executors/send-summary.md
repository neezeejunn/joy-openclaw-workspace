# Executor: send-summary

## Purpose
Send a concise summary only after report generation succeeds.

## Inputs
- completed report file
- market summary template

## Outputs
- message to user channel
- updated state file

## Required State Changes
- summarySent = true
- summaryMessageId recorded if available

## Success Condition
Summary is sent and state records the send result.
