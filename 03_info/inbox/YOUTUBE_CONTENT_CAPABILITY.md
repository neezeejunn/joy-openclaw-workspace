# YouTube Content Capability Design

## Objective
Enable reliable extraction of actual video content, not just titles, for analysis workflows.

## Current Problem
The current environment can often fetch a YouTube link and title, but not reliably obtain transcript-grade content.
This blocks serious comparison and summarization work.

## Capability Levels
### Level 0: Title only
- very low confidence
- not enough for formal analysis

### Level 1: Metadata
- title
- publish date
- channel
- description
- still not enough for formal transcript-based workflows

### Level 2: Transcript access
- minimum viable level for formal analysis
- required for serious comparison workflows

### Level 3: Structured semantic extraction
- transcript plus sectioning, claims, topics, timestamps
- ideal for reusable analysis across modules

## Recommended Priority
The immediate goal should be Level 2: transcript access.
