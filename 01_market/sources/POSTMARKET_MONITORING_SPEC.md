# Post-Market Monitoring Spec

## Objective
Generate a same-day market analysis report only when a same-day video from the target YouTube channel is available, and only using sources from the report day.

## Target Channel
- rhinofinance
- https://youtube.com/@rhinofinance

## Monitoring Window
Use U.S. market trading days only (Monday to Friday).

### Timing Rule
- Start checking at post-market + 4 hours
- Stop checking at post-market + 10 hours
- Poll every 30 minutes until a same-day video is found
- If found, stop polling immediately and generate the report
- If not found by the stop time, end monitoring for the day

## Same-Day Source Rule
A formal report may be generated only if the following are all from the same report day:
1. Channel video publish date
2. Market/news sources used in the report
3. Market context being described

If a source date is unclear, do not use it as a primary basis for the report.

## Report Mode
- If same-day video is found: generate full comparison report
- If no same-day video is found: no channel-comparison report for that day

## Hard Guardrails
- Do not mix previous-session news and current-session news without explicit labeling
- Do not mix weekend commentary into a weekday report unless clearly marked as background
- Do not treat old videos as current-day comparison material
