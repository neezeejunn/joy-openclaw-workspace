# Failsafe Rules

## Purpose
Avoid bad or duplicated reports under imperfect data conditions.

## Rules
1. No report if same-day validation fails.
2. No report if a prior report for the same market day already exists.
3. No report if video publish date cannot be confirmed.
4. No comparison report if news/data sources are stale or ambiguous.
5. Stop quietly when deadlines pass; do not force output.

## Preferred Failure Mode
Silence is better than a wrong report.
