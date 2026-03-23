# Automation Workflow

## Step 1: Monitoring
- Start inside the defined post-market monitoring window
- Check the target channel for same-day uploads
- Validate the publish date before continuing

## Step 2: Source Validation
Before generating a report, verify:
- Video publish date matches report day
- News sources match report day
- Market data corresponds to the same market day/session

## Step 3: Report Generation
If all source dates align:
- Produce the independent market analysis
- Add the channel comparison layer
- Mark report with date/session labels

## Step 4: Stop Logic
- Stop immediately when a valid report has been generated
- Stop at end of monitoring window if no valid same-day video exists

## Failure Handling
- If the video exists but the date is unclear, do not generate a formal comparison report
- If news/data sources are not clearly same-day, either wait for better sources or skip the report
