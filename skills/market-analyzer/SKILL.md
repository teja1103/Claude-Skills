---
name: market-analyzer
description: >-
  Conducts end-to-end market analysis and product-market fit assessment for new
  product ideas. Performs market sizing (TAM/SAM/SOM), competitive landscape mapping,
  trend analysis, SWOT, and customer segmentation — then layers on problem validation,
  product-market fit scoring, business model viability, go-to-market strategy, and
  market timing assessment. Gathers data from multiple web sources and cites them.
  Use when the user asks for market analysis, market research, competitive analysis,
  industry analysis, market sizing, TAM/SAM/SOM, trend analysis, SWOT analysis,
  product-market fit, product validation, market opportunity assessment, go-to-market
  strategy, or wants to evaluate whether a product idea is viable. Not for stock
  trading, financial portfolio management, personal investment advice, or marketing
  campaign execution (ad copy, SEO, social media strategy).
---

# Market Analyzer

Conduct thorough market analysis and product-market fit assessment by researching multiple sources, synthesizing findings, and delivering structured reports with citations.

## Defaults

- **Always cite sources** with numbered references `[1]`, `[2]`, etc. and list full URLs at the end.
- **Use axios** for any programmatic HTTP requests (never fetch).
- **Use WebSearch and WebFetch** as primary research tools to gather live data.
- **Prefer recent data** — include the current year in search queries.
- **Cross-reference claims** across at least 2–3 sources before stating them as fact.

---

## Workflow

### Step 1: Identify the Analysis Mode

Determine which mode applies based on the user's request:

| Mode                   | Trigger                                                                     | What it adds beyond market research                          |
| ---------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------ |
| **Market Research**    | "analyze the {X} market", general industry questions                        | Nothing — standard market analysis                           |
| **Product Evaluation** | "is there a market for {product}?", "will {idea} work?", product-market fit | Problem validation, PMF scoring, business model, GTM, timing |

If unclear, ask:

```
AskQuestion:
- "What would you like to analyze?"
  → ["A market or industry (general research)", "A specific product idea (market fit assessment)", "Both — market research with product fit overlay"]
```

### Step 2: Scope the Analysis

Before researching, establish:

1. **Target market or industry** — What specific market, product category, or sector?
2. **Geographic scope** — Global, specific region, or specific country?
3. **Analysis depth** — Quick overview (~5 min), standard (~10 min), or deep dive (~20+ min)?
4. **Focus areas** — Which modules matter most? (See Analysis Modules below)
5. **Time horizon** — Current snapshot, historical trends, or forward projections?

For **Product Evaluation** mode, also establish:

6. **Product concept** — What does it do? One-sentence value proposition.
7. **Target customer** — Who is the primary user/buyer?
8. **Problem statement** — What pain point does it address?
9. **Revenue model** — How would it make money? (if known)

If the request is clear enough, infer these and proceed. Otherwise use AskQuestion.

### Step 3: Research

Execute parallel web searches across multiple dimensions. Run as concurrent searches where possible.

**Core market research** (always run):

```
WebSearch: "{market} market size {year}"
WebSearch: "{market} industry revenue forecast CAGR"
WebSearch: "{market} top companies market share {year}"
WebSearch: "{market} competitive landscape {year}"
WebSearch: "{market} industry trends {year}"
WebSearch: "{market} market drivers challenges"
```

**Customer & segmentation:**

```
WebSearch: "{market} customer segments demographics"
WebSearch: "{market} buyer behavior trends {year}"
WebSearch: "{market} willingness to pay pricing"
```

**Regulatory & macro:**

```
WebSearch: "{market} regulations policy {year}"
WebSearch: "{market} industry outlook macroeconomic impact"
```

**Product Evaluation mode — add these:**

```
WebSearch: "{problem/pain point} solutions alternatives {year}"
WebSearch: "{product category} customer complaints pain points"
WebSearch: "{product category} startup funding {year}"
WebSearch: "{product category} failed startups lessons"
WebSearch: "{product category} pricing models SaaS" (or relevant model)
WebSearch: "{product category} customer acquisition cost"
WebSearch: "{product category} go-to-market strategy"
```

After each batch, use **WebFetch** on the most relevant URLs to extract detailed data points, statistics, and quotes. See [sources.md](sources.md) for extended query patterns and source prioritization.

### Step 4: Synthesize & Validate

1. Cross-reference statistics across multiple sources — flag conflicting data.
2. Prefer authoritative sources (see source quality ranking in Citation Rules).
3. Note data recency — mark outdated stats with the year of the source.
4. Distinguish between verified data and estimates/projections.
5. For product evaluation: cross-reference market gaps against the proposed product's capabilities.

### Step 5: Deliver the Report

Select the appropriate template from [report-templates.md](report-templates.md):

| Situation                          | Template                           |
| ---------------------------------- | ---------------------------------- |
| Quick market snapshot              | Quick Overview                     |
| Full market analysis               | Full Market Analysis               |
| Competitor comparison              | Competitive Battlecard             |
| New product idea evaluation        | **Product-Market Fit Assessment**  |
| Comprehensive new product analysis | **New Product Opportunity Report** |
| Market entry decision              | Market Entry Assessment            |
| Trend focus                        | Trend Deep-Dive                    |
| Company due diligence              | Investment / Due Diligence         |

Omit sections the user didn't ask for.

---

## Analysis Modules

### Core Market Modules (always available)

#### 1. Market Overview

- Market definition and scope
- Total Addressable Market (TAM), Serviceable Addressable Market (SAM), Serviceable Obtainable Market (SOM)
- Current market size (revenue) and historical growth
- CAGR and growth projections (3–5 year horizon)
- Key market segments by product type, application, end-user, or geography

#### 2. Competitive Landscape

- Major players and estimated market share
- Competitive positioning map (leaders, challengers, niche, emerging)
- Key differentiators per competitor
- Recent M&A activity, funding rounds, partnerships
- Barriers to entry

#### 3. Trends & Drivers

- Macro trends shaping the industry
- Technology drivers and disruption vectors
- Demand-side drivers (consumer behavior shifts)
- Supply-side drivers (cost, manufacturing, logistics)
- Headwinds and restraints

#### 4. Customer Segmentation

- Primary buyer personas / customer segments
- Segment size and growth rates
- Buying criteria and decision drivers
- Unmet needs and whitespace opportunities

#### 5. SWOT Analysis

- Strengths of the overall market / specific company
- Weaknesses and structural challenges
- Opportunities (growth vectors, adjacencies)
- Threats (competition, regulation, substitution)

#### 6. Regulatory & Macro Environment

- Key regulations and compliance requirements
- Upcoming policy changes
- Trade dynamics and tariffs
- Macroeconomic factors (interest rates, inflation, labor market)

### Product Evaluation Modules (Product Evaluation mode)

#### 7. Problem Validation

Assess whether the problem the product solves is real, painful, and worth paying for.

- **Problem severity**: Is this a critical pain, a moderate inconvenience, or a nice-to-have?
- **Frequency**: How often do target customers encounter this problem?
- **Current solutions**: What do people use today? (direct competitors, workarounds, manual processes, ignoring it)
- **Solution satisfaction**: How satisfied are they with current alternatives? Look for complaint patterns, review sentiment, forum discussions.
- **Willingness to pay**: Is there evidence people spend money to solve this? Existing paid solutions, budget allocation signals.

Research approach:

```
WebSearch: "{problem} how do people solve"
WebSearch: "{current solution} complaints reviews problems"
WebSearch: "{product category} customer satisfaction survey"
WebSearch: "reddit {problem} frustrating" OR "forum {problem} help"
```

#### 8. Product-Market Fit Scoring

Synthesize research into a structured PMF assessment.

Score each dimension 1–5 and provide evidence:

| Dimension                | Question                                | Score guidance                                         |
| ------------------------ | --------------------------------------- | ------------------------------------------------------ |
| **Problem severity**     | How painful is the problem?             | 5 = hair-on-fire, 1 = mild inconvenience               |
| **Market size**          | Is the addressable market large enough? | 5 = $1B+ TAM, 1 = <$10M niche                          |
| **Competition gap**      | Is there room for a new entrant?        | 5 = wide open or incumbent weakness, 1 = saturated     |
| **Timing**               | Is the market ready now?                | 5 = strong tailwinds, 1 = too early or too late        |
| **Differentiation**      | Can this product credibly stand apart?  | 5 = strong unique angle, 1 = me-too                    |
| **Monetization clarity** | Is there a clear path to revenue?       | 5 = proven model in market, 1 = no precedent           |
| **Customer access**      | Can you reach target customers?         | 5 = clear channels exist, 1 = fragmented/hard to reach |

**Overall PMF Score**: Average of dimensions. Interpret:

- 4.0–5.0: Strong product-market fit signal. Move fast.
- 3.0–3.9: Promising but has gaps. Address weak dimensions before committing.
- 2.0–2.9: Significant concerns. Pivot the concept or validate further.
- 1.0–1.9: Weak fit. Likely needs fundamental rethinking.

#### 9. Business Model Viability

Assess whether the product can build a sustainable business.

- **Revenue model**: Which model fits? (SaaS subscription, marketplace commission, freemium, one-time purchase, usage-based, advertising, licensing)
- **Pricing benchmarks**: What do comparable products charge? What does the market tolerate?
- **Unit economics sketch**: Estimate rough CAC, LTV, and LTV:CAC ratio based on market benchmarks.
- **Gross margin profile**: What do similar companies achieve?
- **Scalability**: Does the model scale with technology, or does it require linear cost growth?

Use market data and competitor financials (where available from public filings, funding announcements, or industry benchmarks) to ground these estimates.

#### 10. Go-to-Market Strategy

Based on market structure and customer segments, recommend GTM approach.

- **Positioning**: Where does the product sit vs. competitors? (cost leader, premium, niche specialist, disruptor)
- **Primary channels**: Which customer acquisition channels are most viable? (content/SEO, paid ads, partnerships, direct sales, product-led growth, community)
- **Beachhead segment**: Which specific customer segment to target first and why.
- **Key messaging**: What value proposition resonates based on the pain points validated in Problem Validation?
- **Distribution advantages**: Any structural advantages in reaching customers? (existing platforms, API integrations, network effects)

#### 11. Market Timing Assessment

Evaluate whether now is the right time to enter.

- **Technology readiness**: Are enabling technologies mature enough?
- **Market maturity**: Where on the adoption curve? (innovators, early adopters, early majority, late majority)
- **Catalysts**: Recent events accelerating demand (regulation changes, platform shifts, cultural shifts, pandemic effects)
- **"Why now?" narrative**: What has changed that makes this possible or necessary today that wasn't true 2–3 years ago?
- **Risk of being too early vs too late**: Historical examples of timing in this market.

---

## Citation Rules

1. Every quantitative claim (market size, growth rate, share %) must have a numbered citation.
2. Qualitative insights from a specific source must be cited.
3. Common industry knowledge does not need a citation but benefits from one.
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
- **PMF scores with weak evidence:** Note confidence level: "Score based on limited data — treat as directional, not definitive."

---

## Additional Resources

- For source discovery strategies and search query patterns, see [sources.md](sources.md)
- For report templates and format variations, see [report-templates.md](report-templates.md)
