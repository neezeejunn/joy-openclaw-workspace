# Scheduling Plan for Post-Market Reports

## Goal
Turn the monitoring rules into a repeatable automation plan.

## Market Clock Assumption
Use U.S. regular market close as the anchor point.
Regular close is 16:00 America/New_York on standard trading days.

## Monitoring Window
- Start: 20:00 America/New_York (post-market +4h)
- End: 02:00 America/New_York next day (post-market +10h)
- Days: Monday to Friday market days
- Polling interval: every 30 minutes

## Logic
1. Open monitoring window at 20:00 ET
2. Check rhinofinance for a same-day video
3. If not found, wait 30 minutes
4. Repeat until 02:00 ET
5. If found, stop polling and generate report immediately
6. If not found by 02:00 ET, close the day with no channel-comparison report

## Time Discipline
The report date should follow the market day being analyzed, not merely UTC date rollover.
For example, checks after midnight ET but before 02:00 ET still belong to the previous market day report.

## Dependencies
- A reliable way to detect same-day channel uploads
- A reliable way to collect same-day market/news sources
- A report generation path triggered only after validation
