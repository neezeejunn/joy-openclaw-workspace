# Email Optimization Engine

## Goal
Build a long-term optimization system instead of relying only on static mailbox rules.

## Core Components
### 1. Sender scoring
Track whether a sender is usually:
- high-value
- mixed-value
- low-value

### 2. Subject / keyword weighting
Track positive and negative indicators across subjects and message previews.

### 3. Message type classifier
Classify messages into:
- shipping
- work / collaboration
- billing
- security
- newsletter
- promotions
- admin / misc

### 4. Routing policy
Route to:
- Inbox
- Same-day review
- 16_30_batch
- ignore / archive

### 5. Feedback loop
Use mistakes to improve the system over time.

## Principle
The system should learn and tighten over time instead of being frozen as static rules.
