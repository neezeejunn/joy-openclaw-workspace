# YouTube Transcript-Only Policy

## Principle
For this market-analysis workflow, only transcript-based video understanding is considered reliable enough for formal comparison.

## Hard Rule
If a same-day video transcript cannot be obtained, treat the YouTube reading step as a failure.
Do not fall back to description-only reading for formal comparison work.

## Reason
The user's requirement is that only the actual spoken video content is valuable enough for comparison.
Descriptions may be incomplete, promotional, or structurally different from the spoken analysis.

## Operational Consequence
- Transcript available -> proceed with video analysis
- Transcript unavailable -> fail the YouTube comparison step
- No transcript -> no formal comparison report for that day

## Reporting Rule
If transcript retrieval fails, explicitly record:
- transcript_unavailable
- no_formal_youtube_comparison
