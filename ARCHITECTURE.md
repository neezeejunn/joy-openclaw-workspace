# Personal Operations Architecture

This workspace is organized around a modular system that can expand over time.

## Active Workstreams
1. 01_market  — US market research and opportunity analysis
2. 02_health  — Health tracking and lifestyle optimization
3. 03_info    — Information filtering and batched processing
4. 04_kol     — Influencer/KOL relationship pipeline

## Shared Control Layer
- control/priorities.md
- control/rules.md
- control/schedule.md
- control/routines.md

## Design Principles
- Build reusable systems first
- Separate raw inputs from analysis and outputs
- Prefer daily lightweight updates + weekly deep dives
- Use scheduled automation for precise tasks and main-session context for interactive guidance
- Store important reasoning so the system gets smarter over time

## Expansion Rule
Any new workstream should define:
1. Its objective
2. Its cadence (real-time / daily / weekly / batched)
3. Its inputs
4. Its outputs
5. Its memory structure
