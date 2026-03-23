# Hotmail Level 3 Integration Plan

## Objective
Enable long-term, operational email management for `joy940207@hotmail.com` with the ability to:
- read emails
- classify emails
- create/manage folders
- move emails
- support continuous optimization

## Recommended Integration Method
Use Microsoft Graph / Outlook API with OAuth-based access.
Do not treat browser control as the primary long-term solution.

## Why
Browser control is fragile and session-dependent.
API access is more stable, auditable, and suitable for sustained automation.

## Phase Plan
### Phase 1: Controlled read/write capability
Target capabilities:
- read messages
- read folders
- create folders
- move messages between folders

### Phase 2: Low-risk operational automation
Start with:
- create `16_30_batch`
- move low-priority mail into that folder
- keep high-priority mail in Inbox
- avoid delete actions

### Phase 3: Ongoing optimization
Add:
- sender-level priority tuning
- keyword weighting
- exception handling
- false-positive correction
- better batching logic

## Recommended Folder Strategy
Start simple:
- Inbox
- 16_30_batch
Optional later:
- Later_Review
- Important_Keep

## Initial Priority Policy
### Keep in Inbox
- shipping / delivery
- work / collaboration
- billing / payments
- security alerts

### Move to 16_30_batch
- ads
- promotions
- newsletters
- routine updates
- optional reading

## Permission Boundary Recommendation
Initial operational scope should include:
- read email
- read/write folders
- move email

Initial operational scope should exclude:
- delete email
- mass archive old history
- send email
- broad destructive actions

## Risk Control
- Start with low-risk movement only
- Keep Inbox as the safe default for important classes
- Do not auto-delete
- Review misclassifications before broadening automation

## Long-Term Goal
Create a continuously improving email triage system rather than a large set of static mailbox rules.
