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

## High-Value Source Domains

When WebFetch results are available, prioritize these domains:

### Tier 1 — Authoritative Data
| Domain | Type | Best For |
|--------|------|----------|
| statista.com | Market data aggregator | Market size, share, growth stats |
| ibisworld.com | Industry reports | Industry structure, trends, key players |
| grandviewresearch.com | Market research | Market size, segmentation, forecasts |
| mordorintelligence.com | Market intelligence | CAGR, regional breakdown, competitive landscape |
| gartner.com | Technology research | Tech market analysis, Magic Quadrants |
| mckinsey.com | Management consulting | Strategic insights, macro trends |
| sec.gov/edgar | SEC filings | Company financials, 10-K, 10-Q reports |
| census.gov | Government data | Demographics, economic census data |
| bls.gov | Government data | Labor statistics, industry employment |
| trade.gov | Government data | Export/import data, trade statistics |

### Tier 2 — Business Press
| Domain | Type | Best For |
|--------|------|----------|
| bloomberg.com | Financial news | Market moves, company news, analysis |
| reuters.com | News agency | Industry news, factual reporting |
| ft.com | Financial press | Global business analysis |
| wsj.com | Financial press | US business and market news |

### Tier 3 — Industry & Tech Media
| Domain | Type | Best For |
|--------|------|----------|
| techcrunch.com | Tech media | Startup/tech market coverage |
| forbes.com | Business media | Industry rankings, company profiles |
| hbr.org | Business research | Strategic frameworks, case studies |
| crunchbase.com | Startup database | Funding rounds, company data |

---

## Search Iteration Strategy

If initial searches yield thin results:

1. **Broaden terms:** Replace specific product names with category-level terms.
2. **Try adjacent markets:** Search for the parent market or related verticals.
3. **Add "report" or "study":** Surfaces research firm summaries.
4. **Use "site:" operator:** Target specific high-value domains (e.g., `site:statista.com {market}`).
5. **Check press releases:** Companies often disclose market data in PR (`"{company} press release market {year}"`).
6. **Try industry associations:** Search for `"{market} industry association"` — they often publish annual reports.

## Handling Paywalled Sources

Many research firms gate full reports behind paywalls. To extract useful data:

1. **Read the summary/abstract** — often contains headline stats (market size, CAGR, key players).
2. **Check press releases** — firms publish key findings to attract buyers.
3. **Search for citations** — other articles often cite the paywalled report's key numbers.
4. **Look for infographics** — some firms release visual summaries freely.
5. **Always note the original source** even if accessed via a secondary citation.
