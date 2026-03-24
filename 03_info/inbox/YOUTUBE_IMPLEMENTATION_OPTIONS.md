# YouTube Transcript Implementation Options

## Option A: Browser-based transcript extraction
### Description
Use browser automation to open a YouTube video and read the transcript from the page.

### Pros
- works directly from the visible page
- aligns with the transcript-only policy

### Cons
- depends on reliable browser control
- currently blocked by gateway/browser instability

## Option B: External transcript retrieval path
### Description
Use a dedicated transcript retrieval method or service to obtain transcript text directly.

### Pros
- cleaner and more automatable if reliable
- less dependent on browser session state

### Cons
- requires new integration path
- may need maintenance if source behavior changes

## Option C: Manual transcript input fallback
### Description
User provides transcript or transcript export.

### Pros
- immediately usable
- very high control and clarity

### Cons
- not automated

## Recommendation
Prioritize Option B as the long-term path, while using Option C when needed and Option A only when browser control is healthy.
