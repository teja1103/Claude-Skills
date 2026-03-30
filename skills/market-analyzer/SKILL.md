---
name: market-analyzer
description: >-
  Performs extensive market analysis including market sizing, competitive landscape, trends, SWOT, and customer segmentation. Gathers data from multiple web sources and cites them. Use when the user asks for market analysis, market research, competitive analysis, industry analysis, market sizing, TAM/SAM/SOM, trend analysis, or SWOT analysis. Do not use for stock trading, financial portfolio management, or personal investment advice.
---

# Market Analyzer

Conduct thorough market analysis by researching multiple sources, synthesizing findings, and delivering structured reports with citations.

## Defaults

- **Always cite sources** with numbered references `[1]`, `[2]`, etc. and list full URLs at the end.
- **Use axios** for any programmatic HTTP requests (never fetch).
- **Use WebSearch and WebFetch** as primary research tools to gather live data.
- **Prefer recent data** — include the current year in search queries.
- **Cross-reference claims** across at least 2–3 sources before stating them as fact.

---

## Analysis Workflow

### Phase 1: Scope the Analysis

Before researching, clarify with the user:

1. **Target market or industry** — What specific market, product category, or sector?
2. **Geographic scope** — Global, specific region, or specific country?
3. **Analysis depth** — Quick overview (~5 min) or deep dive (~15+ min)?
4. **Focus areas** — Which sections matter most? (See Analysis Modules below)
5. **Time horizon** — Current snapshot, historical trends, or forward projections?

If the user's request is clear enough, infer these and proceed. Otherwise use AskQuestion:

```
Example AskQuestion:
- "What geographic scope?" → ["Global", "North America", "Europe", "Asia-Pacific", "Specific country"]
- "Which analysis modules?" → ["Market Overview", "Competitive Landscape", "Trends & Drivers", "Customer Segmentation", "SWOT", "All of the above"] (allow_multiple)
- "How deep should the analysis go?" → ["Quick overview (key highlights)", "Standard (covers all modules)", "Deep dive (exhaustive with projections)"]
```

### Phase 2: Research

Execute parallel web searches across multiple dimensions. Run these as concurrent searches:

**Market size & growth:**
```
WebSearch: "{market} market size {year}"
WebSearch: "{market} industry revenue forecast"
WebSearch: "{market} CAGR growth rate"
```

**Competitive landscape:**
```
WebSearch: "{market} top companies market share"
WebSearch: "{market} competitive landscape {year}"
WebSearch: "{market} industry leaders"
```

**Trends & drivers:**
```
WebSearch: "{market} industry trends {year}"
WebSearch: "{market} market drivers challenges"
WebSearch: "{market} emerging technologies disruption"
```

**Customer & segmentation:**
```
WebSearch: "{market} customer segments demographics"
WebSearch: "{market} buyer behavior trends"
```

**Regulatory & macro:**
```
WebSearch: "{market} regulations policy {year}"
WebSearch: "{market} industry outlook macroeconomic impact"
```

After each search, use **WebFetch** on the most relevant URLs to extract detailed data points, statistics, and quotes.

### Phase 3: Synthesize & Validate

1. Cross-reference statistics across multiple sources — flag conflicting data.
2. Prefer authoritative sources: industry reports (Statista, IBISWorld, Grand View Research, Mordor Intelligence), government data, reputable business press (Bloomberg, Reuters, Financial Times), and company filings.
3. Note data recency — mark outdated stats with the year of the source.
4. Distinguish between verified data and estimates/projections.

### Phase 4: Deliver the Report

Use the report template below. Omit sections the user didn't ask for.

---

## Analysis Modules

### 1. Market Overview
- Market definition and scope
- Total Addressable Market (TAM), Serviceable Addressable Market (SAM), Serviceable Obtainable Market (SOM)
- Current market size (revenue) and historical growth
- CAGR and growth projections (3–5 year horizon)
- Key market segments by product type, application, end-user, or geography

### 2. Competitive Landscape
- Major players and estimated market share
- Competitive positioning map (leaders, challengers, niche, emerging)
- Key differentiators per competitor
- Recent M&A activity, funding rounds, partnerships
- Barriers to entry

### 3. Trends & Drivers
- Macro trends shaping the industry
- Technology drivers and disruption vectors
- Demand-side drivers (consumer behavior shifts)
- Supply-side drivers (cost, manufacturing, logistics)
- Headwinds and restraints

### 4. Customer Segmentation
- Primary buyer personas / customer segments
- Segment size and growth rates
- Buying criteria and decision drivers
- Unmet needs and whitespace opportunities

### 5. SWOT Analysis
- Strengths of the overall market / specific company
- Weaknesses and structural challenges
- Opportunities (growth vectors, adjacencies)
- Threats (competition, regulation, substitution)

### 6. Regulatory & Macro Environment
- Key regulations and compliance requirements
- Upcoming policy changes
- Trade dynamics and tariffs
- Macroeconomic factors (interest rates, inflation, labor market)

---

## Report Template

```markdown
# Market Analysis: {Market Name}

**Date:** {current date}
**Scope:** {geographic scope}
**Prepared by:** AI Market Analyzer

---

## Executive Summary
{2–3 paragraph overview of key findings, market size, growth trajectory, and top opportunities/risks}

## 1. Market Overview
### Market Definition
{What this market includes and excludes}

### Market Size & Growth
- **Current market size:** ${X}B ({year}) [source]
- **Projected size:** ${Y}B by {year} [source]
- **CAGR:** {X}% ({period}) [source]

### TAM / SAM / SOM
| Metric | Value | Basis |
|--------|-------|-------|
| TAM    | ${X}  | {description} |
| SAM    | ${X}  | {description} |
| SOM    | ${X}  | {description} |

### Key Segments
{Breakdown by segment with relative sizes}

## 2. Competitive Landscape
### Market Leaders
| Company | Est. Market Share | Key Strengths |
|---------|------------------|---------------|
| {name}  | {X}%             | {strengths}   |

### Competitive Positioning
{Analysis of positioning — leaders vs challengers vs niche players}

### Recent Activity
{M&A, funding, partnerships in last 12 months}

## 3. Trends & Drivers
### Growth Drivers
1. {Driver 1} — {explanation with data} [source]
2. {Driver 2} — {explanation with data} [source]

### Market Restraints
1. {Restraint 1} — {explanation} [source]

### Emerging Trends
{Technology shifts, behavioral changes, regulatory trends}

## 4. Customer Segmentation
### Primary Segments
{Segment descriptions with size estimates}

### Buying Criteria
{What drives purchase decisions in this market}

## 5. SWOT Analysis
| | Positive | Negative |
|---|----------|----------|
| **Internal** | **Strengths:** {list} | **Weaknesses:** {list} |
| **External** | **Opportunities:** {list} | **Threats:** {list} |

## 6. Regulatory & Macro
{Key regulatory considerations, macro factors}

---

## Sources
[1] {Title} — {URL} (accessed {date})
[2] {Title} — {URL} (accessed {date})
...
```

---

## Citation Rules

**Always apply these rules:**

1. Every quantitative claim (market size, growth rate, share %) must have a numbered citation.
2. Qualitative insights from a specific source must be cited.
3. Common industry knowledge (e.g., "the cloud market has grown rapidly") does not need a citation but benefits from one.
4. Format: `[N]` inline, full reference in the Sources section at the end.
5. Include the access date for all web sources.
6. If two sources conflict, present both: "Source A reports $X [1], while Source B estimates $Y [2]."

**Source quality ranking (prefer higher-ranked):**
1. Government/regulatory data (census, SEC filings, trade commissions)
2. Industry research firms (Statista, Gartner, IDC, McKinsey, IBISWorld)
3. Company filings and investor presentations (10-K, annual reports)
4. Major business press (Bloomberg, Reuters, Financial Times, WSJ)
5. Trade publications and industry associations
6. Reputable tech/business media (TechCrunch, Forbes, Harvard Business Review)
7. Analyst blogs and opinion pieces

---

## Handling Uncertainty

- **Data gaps:** State explicitly: "Reliable data for {X} is limited; the following is the best available estimate."
- **Conflicting data:** Present both figures with sources and explain the likely reason for discrepancy.
- **Outdated data:** Flag it: "Most recent available data is from {year}."
- **Projections:** Distinguish forecasts from historical data: "Projected to reach $XB by {year} (forecast) [source]."

---

## Additional Resources

- For source discovery strategies and search query patterns, see [sources.md](sources.md)
- For extended report templates and format variations, see [report-templates.md](report-templates.md)
