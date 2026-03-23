# Market-Day Time Rules

## Core Rule
The report belongs to the U.S. market day being analyzed, not simply the current UTC date.

## Window Rule
Use America/New_York as the reference timezone.

- Market close anchor: 16:00 ET
- Monitoring start: 20:00 ET (post-market +4h)
- Monitoring end: 02:00 ET next calendar day in ET (post-market +10h)

## Cross-Midnight Rule
Checks between 00:00 ET and 02:00 ET still belong to the previous market day report.

## Practical Example
- Monday market day report may still be monitored until early Tuesday 02:00 ET
- The report date remains Monday market day, not Tuesday UTC

## Why this matters
Without this rule, source dates and state tracking can drift across midnight and create duplicate or misdated reports.
