# Execution Notes

## Current Operating Limitation
The current environment does not yet have fully reliable automated access to all desired market and YouTube data layers.

## Practical Strategy
Build the system in this order:
1. Rules and report structure
2. Monitoring and date discipline
3. Scheduling logic
4. Data-source hardening
5. End-to-end automation

## Why this order
This avoids automating bad process. First define what a valid report is, then automate the valid workflow.
