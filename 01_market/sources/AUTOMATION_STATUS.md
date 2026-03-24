# Automation Status

## Current Status
The market module cron automation has been enabled.

## Active Jobs
1. Market Open Window
2. Market Repeated Check
3. Market Repeated Check After Midnight
4. Market Close Window

## Intended Behavior
- Open the monitoring window on U.S. market weekdays
- Poll during the post-market window
- Attempt transcript-backed comparison only when same-day conditions are satisfied
- Close the window and record completion state after the deadline

## Important Note
Automation is now scheduled, but final report quality still depends on:
- same-day video availability
- transcript retrieval success
- same-day market/news source availability
