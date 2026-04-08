# Source Discovery Strategies

## Search Query Patterns

Tailor searches to the data type needed. Always include the current year for recency.

### Market Size & Valuation

```
"{market} market size {year}"
"{market} industry revenue {year}"
"{market} market value billion"
"{market} market forecast {year}-{year+5}"
"global {market} market report"
```

### Growth Rates

```
"{market} CAGR {year}"
"{market} market growth rate forecast"
"{market} industry growth trends"
```

### Competitive Intelligence

```
"{market} market share by company {year}"
"{market} top companies revenue"
"{market} competitive analysis"
"{market} industry leaders ranking"
"{company name} market share {market}"
"{company name} annual report {year}"
"{company name} 10-K SEC filing"
```

### TAM / SAM / SOM

```
"{market} total addressable market"
"{market} TAM SAM SOM"
"{market} serviceable market size"
```

### Funding & M&A

```
"{market} acquisitions {year}"
"{market} startup funding {year}"
"{market} venture capital investment"
"site:crunchbase.com {market}"
```

### Regulatory

```
"{market} regulations {country} {year}"
"{market} compliance requirements"
"{market} policy changes {year}"
"{market} government regulation"
```

### Consumer / Demand

```
"{market} consumer trends {year}"
"{market} buyer behavior survey"
"{market} customer preferences {year}"
"{market} adoption rate"
```

---

## Product Validation Search Patterns

Use these when evaluating a specific product idea or assessing product-market fit.

### Problem & Pain Point Research

```
"{problem} how do people solve"
"{problem} biggest challenge frustration"
"{current solution} complaints reviews problems"
"{product category} customer satisfaction survey"
"{product category} NPS score"
"reddit {problem} frustrating" OR "forum {problem} help"
"{product category} user feedback survey {year}"
"why do people switch from {competitor}"
```

### Alternative / Substitute Analysis

```
"{product category} alternatives comparison"
"{competitor} vs {competitor} comparison {year}"
"{product category} best tools software {year}"
"G2 reviews {product category}"
"Capterra {product category} reviews"
"{product category} open source alternative"
```

### Willingness to Pay / Pricing

```
"{product category} pricing comparison {year}"
"{product category} average selling price"
"{product category} willingness to pay survey"
"{competitor} pricing plans"
"{product category} SaaS pricing benchmark"
"{product category} enterprise pricing"
```

### Customer Acquisition & Go-to-Market

```
"{product category} customer acquisition cost benchmark"
"{product category} marketing channels"
"{product category} go-to-market strategy"
"{product category} sales cycle length"
"{product category} product-led growth"
"{product category} content marketing strategy"
```

### Startup Landscape & Funding

```
"{product category} startup funding {year}"
"{product category} seed round series A {year}"
"{product category} startup failures lessons"
"{product category} startup landscape map"
"site:crunchbase.com {product category} funding"
"{product category} Y Combinator"
"{product category} venture capital investment {year}"
```

### Unit Economics & Business Model

```
"{product category} SaaS metrics benchmark"
"{product category} LTV CAC ratio"
"{product category} gross margin benchmark"
"{product category} churn rate benchmark"
"{product category} revenue per user ARPU"
"{similar company} business model revenue"
```

### Market Timing & Adoption

```
"{product category} adoption rate {year}"
"{technology} maturity hype cycle Gartner"
"{product category} early adopters"
"{market} market readiness {year}"
"{enabling technology} cost reduction timeline"
```

---

## High-Value Source Domains

When WebFetch results are available, prioritize these domains:

### Tier 1 — Authoritative Data

| Domain                 | Type                   | Best For                                           |
| ---------------------- | ---------------------- | -------------------------------------------------- |
| statista.com           | Market data aggregator | Market size, share, growth stats                   |
| ibisworld.com          | Industry reports       | Industry structure, trends, key players            |
| grandviewresearch.com  | Market research        | Market size, segmentation, forecasts               |
| mordorintelligence.com | Market intelligence    | CAGR, regional breakdown, competitive landscape    |
| gartner.com            | Technology research    | Tech market analysis, Magic Quadrants, Hype Cycles |
| mckinsey.com           | Management consulting  | Strategic insights, macro trends                   |
| sec.gov/edgar          | SEC filings            | Company financials, 10-K, 10-Q reports             |
| census.gov             | Government data        | Demographics, economic census data                 |
| bls.gov                | Government data        | Labor statistics, industry employment              |
| trade.gov              | Government data        | Export/import data, trade statistics               |

### Tier 2 — Business Press

| Domain        | Type            | Best For                             |
| ------------- | --------------- | ------------------------------------ |
| bloomberg.com | Financial news  | Market moves, company news, analysis |
| reuters.com   | News agency     | Industry news, factual reporting     |
| ft.com        | Financial press | Global business analysis             |
| wsj.com       | Financial press | US business and market news          |

### Tier 3 — Industry & Tech Media

| Domain         | Type              | Best For                            |
| -------------- | ----------------- | ----------------------------------- |
| techcrunch.com | Tech media        | Startup/tech market coverage        |
| forbes.com     | Business media    | Industry rankings, company profiles |
| hbr.org        | Business research | Strategic frameworks, case studies  |
| crunchbase.com | Startup database  | Funding rounds, company data        |

### Tier 4 — Product & Startup Research

| Domain                    | Type                 | Best For                                          |
| ------------------------- | -------------------- | ------------------------------------------------- |
| g2.com                    | Software reviews     | Product comparisons, user sentiment, market grids |
| capterra.com              | Software reviews     | Pricing, feature comparisons, user reviews        |
| trustpilot.com            | Consumer reviews     | Customer satisfaction signals, complaint patterns |
| producthunt.com           | Product launches     | New entrant landscape, early traction signals     |
| ycombinator.com/companies | Startup directory    | YC-backed companies in a space                    |
| pitchbook.com             | VC/PE data           | Funding, valuations, deal flow                    |
| cbinsights.com            | Market intelligence  | Startup landscapes, funding trends, industry maps |
| failory.com               | Startup post-mortems | Why companies in a space failed                   |
| saasmetrics.co            | SaaS benchmarks      | Unit economics benchmarks for SaaS                |
| openvc.app                | VC landscape         | Investor activity in a sector                     |

---

## Search Iteration Strategy

If initial searches yield thin results:

1. **Broaden terms:** Replace specific product names with category-level terms.
2. **Try adjacent markets:** Search for the parent market or related verticals.
3. **Add "report" or "study":** Surfaces research firm summaries.
4. **Use "site:" operator:** Target specific high-value domains (e.g., `site:statista.com {market}`).
5. **Check press releases:** Companies often disclose market data in PR (`"{company} press release market {year}"`).
6. **Try industry associations:** Search for `"{market} industry association"` — they often publish annual reports.
7. **Search startup post-mortems:** For product validation, `"{product category} startup failed why"` reveals real-world lessons.
8. **Check review aggregators:** `site:g2.com "{product category}"` or `site:capterra.com "{product category}"` for user sentiment.

## Handling Paywalled Sources

Many research firms gate full reports behind paywalls. To extract useful data:

1. **Read the summary/abstract** — often contains headline stats (market size, CAGR, key players).
2. **Check press releases** — firms publish key findings to attract buyers.
3. **Search for citations** — other articles often cite the paywalled report's key numbers.
4. **Look for infographics** — some firms release visual summaries freely.
5. **Always note the original source** even if accessed via a secondary citation.
