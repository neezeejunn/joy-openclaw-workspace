# Source Availability Matrix

## Purpose
Track which market/news sources are actually readable in the current environment, and what kind of information each source can provide.

## Currently More Usable
### CNBC
- Status: usable
- Best for: readable market news articles, macro updates, sector commentary, company-specific stories
- Strength: article bodies are often readable through current tooling
- Weakness: may still not expose every table / quote block cleanly

### Morningstar
- Status: partially usable
- Best for: market overview, style/sector framing, valuation context, article discovery
- Strength: some market structure and featured coverage pages are readable
- Weakness: not always ideal for deep article extraction from all subpages

### Barron's Market Data
- Status: partially usable
- Best for: market-data hub, futures/economy calendar, article discovery, market context
- Strength: some market-data pages and linked article headlines are readable
- Weakness: full article bodies may still be restricted or inconsistent

## Currently Less Usable / Blocked
### Bloomberg
- Status: blocked / anti-bot
- Issue: robot check / anti-automation barrier

### Reuters
- Status: blocked in current fetch path
- Issue: JS / anti-bot wall

### MarketWatch
- Status: blocked in current fetch path
- Issue: JS / anti-bot wall

### WSJ
- Status: blocked in current fetch path
- Issue: JS / ad-block / paywall style barrier

### Investing.com
- Status: blocked / anti-bot
- Issue: challenge page

### TheStreet
- Status: blocked in current fetch path
- Issue: JS / anti-bot wall

## Practical Source Strategy
### Primary readable sources for now
1. CNBC
2. Morningstar
3. Barron's market-data pages

### Secondary / aspirational sources
- Bloomberg
- Reuters
- MarketWatch
- WSJ
- Investing.com
- TheStreet

## Rule
Prefer sources that expose readable article bodies over sources that only expose homepage titles.
