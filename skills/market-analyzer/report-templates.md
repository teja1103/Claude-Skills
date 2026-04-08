# Report Templates

Templates for different analysis types. Select based on the situation table in SKILL.md.

---

## Full Market Analysis Template

The standard comprehensive report.

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

| Metric | Value | Basis         |
| ------ | ----- | ------------- |
| TAM    | ${X}  | {description} |
| SAM    | ${X}  | {description} |
| SOM    | ${X}  | {description} |

### Key Segments

{Breakdown by segment with relative sizes}

## 2. Competitive Landscape

### Market Leaders

| Company | Est. Market Share | Key Strengths |
| ------- | ----------------- | ------------- |
| {name}  | {X}%              | {strengths}   |

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

|              | Positive                  | Negative               |
| ------------ | ------------------------- | ---------------------- |
| **Internal** | **Strengths:** {list}     | **Weaknesses:** {list} |
| **External** | **Opportunities:** {list} | **Threats:** {list}    |

## 6. Regulatory & Macro

{Key regulatory considerations, macro factors}

---

## Sources

[1] {Title} — {URL} (accessed {date})
[2] {Title} — {URL} (accessed {date})
...
```

---

## Quick Overview Template

For rapid market snapshots when depth isn't needed.

```markdown
# {Market} — Quick Overview

**Date:** {date} | **Scope:** {scope}

## Key Numbers

| Metric        | Value           | Source |
| ------------- | --------------- | ------ |
| Market Size   | ${X}B ({year})  | [1]    |
| Growth (CAGR) | {X}% ({period}) | [2]    |
| Key Players   | {top 3-5 names} | [3]    |

## What's Happening

- {Trend 1 with data point} [source]
- {Trend 2 with data point} [source]
- {Trend 3 with data point} [source]

## Key Takeaway

{1-2 sentence summary of the most important insight}

## Sources

[1] {URL}
...
```

---

## Product-Market Fit Assessment Template

For evaluating whether a specific product idea fits its target market. Combines market data with product validation.

```markdown
# Product-Market Fit Assessment: {Product Name / Concept}

**Date:** {date}
**Target Market:** {market}
**Prepared by:** AI Market Analyzer

---

## Executive Summary

{2–3 paragraphs: What the product is, the market opportunity, and the headline PMF verdict with key supporting/detracting factors}

## 1. Product Concept

### What It Does

{One-paragraph description of the product}

### Value Proposition

{Single sentence: For [target customer] who [problem], [product] is a [category] that [key benefit]. Unlike [alternatives], it [differentiator].}

### Target Customer

- **Primary segment:** {who}
- **Segment size estimate:** {X} potential users/companies [source]
- **Key characteristics:** {demographics, firmographics, behaviors}

## 2. Problem Validation

### Problem Description

{What pain point does this product address?}

### Problem Severity: {Critical / Significant / Moderate / Mild}

{Evidence for severity rating — frequency, cost of the problem, emotional intensity}

### How People Solve It Today

| Current Solution    | Strengths | Weaknesses     | Market Share (est.) |
| ------------------- | --------- | -------------- | ------------------- |
| {Solution A}        | {pros}    | {cons}         | {X}%                |
| {Solution B}        | {pros}    | {cons}         | {X}%                |
| {Manual workaround} | {pros}    | {cons}         | {X}%                |
| {Do nothing}        | —         | {consequences} | {X}%                |

### Customer Pain Signals

{Evidence from reviews, forums, surveys, complaint patterns — with sources}

### Willingness to Pay

{Evidence that customers spend money on this problem — existing paid solutions, budget data, survey data}

## 3. Market Opportunity

### Market Size

- **TAM:** ${X}B — {basis} [source]
- **SAM:** ${X}B — {basis} [source]
- **SOM (Year 1–3):** ${X}M — {basis and assumptions}

### Growth Trajectory

- **CAGR:** {X}% ({period}) [source]
- **Growth drivers:** {key factors accelerating this market}

### Market Maturity

{Where on the adoption curve: innovators → early adopters → early majority → late majority}

## 4. Competitive Landscape

### Direct Competitors

| Competitor | Revenue/Funding | Positioning | Key Strength | Key Gap                      |
| ---------- | --------------- | ----------- | ------------ | ---------------------------- |
| {name}     | ${X}M           | {position}  | {strength}   | {gap your product addresses} |

### Indirect Competitors & Substitutes

{Products/services that solve the same problem differently}

### Competitive Gap Analysis

{Where specifically do current solutions fall short? This is the opening for the new product.}

### Barriers to Entry

- {Barrier 1}: {How it affects this product specifically}
- {Barrier 2}: {How it affects this product specifically}

## 5. Product-Market Fit Score

| Dimension            | Score (1-5) | Evidence              |
| -------------------- | :---------: | --------------------- |
| Problem severity     |     {X}     | {brief justification} |
| Market size          |     {X}     | {brief justification} |
| Competition gap      |     {X}     | {brief justification} |
| Timing               |     {X}     | {brief justification} |
| Differentiation      |     {X}     | {brief justification} |
| Monetization clarity |     {X}     | {brief justification} |
| Customer access      |     {X}     | {brief justification} |
| **Overall**          |  **{avg}**  |                       |

### PMF Interpretation

{What the score means: strong fit / promising with gaps / significant concerns / weak fit}

### Strongest Signals

{Top 2-3 reasons to believe in this product's market fit}

### Biggest Risks to Fit

{Top 2-3 concerns that could undermine fit}

## 6. Recommendations

### Verdict: {GO / CONDITIONAL GO / PAUSE / NO-GO}

{Reasoning for the verdict}

### If GO — Next Steps

1. {Validation step} — {what to test and how}
2. {Build step} — {what to build first}
3. {Launch step} — {beachhead strategy}

### If Concerns — What to Validate First

1. {Open question} — {how to resolve it}
2. {Open question} — {how to resolve it}

---

## Sources

[1] {Title} — {URL} (accessed {date})
[2] {Title} — {URL} (accessed {date})
...
```

---

## New Product Opportunity Report Template

Comprehensive end-to-end analysis for a new product idea. Combines full market research with product evaluation, business model assessment, and go-to-market strategy.

```markdown
# New Product Opportunity Report: {Product Name / Concept}

**Date:** {date}
**Target Market:** {market}
**Geographic Scope:** {scope}
**Prepared by:** AI Market Analyzer

---

## Executive Summary

{3–4 paragraphs covering: the opportunity in one sentence, market size and trajectory, competitive opening, PMF assessment, business model viability, and the headline recommendation}

---

## Part I: Market Landscape

### 1. Market Overview

#### Market Definition

{What this market includes and excludes}

#### Market Size & Growth

- **Current market size:** ${X}B ({year}) [source]
- **Projected size:** ${Y}B by {year} [source]
- **CAGR:** {X}% ({period}) [source]

#### TAM / SAM / SOM

| Metric | Value | Basis                         |
| ------ | ----- | ----------------------------- |
| TAM    | ${X}  | {description}                 |
| SAM    | ${X}  | {description}                 |
| SOM    | ${X}  | {description and assumptions} |

#### Key Segments

{Breakdown by segment with relative sizes and growth rates}

### 2. Competitive Landscape

#### Major Players

| Company | Revenue/Funding | Market Share | Positioning | Vulnerability        |
| ------- | --------------- | :----------: | ----------- | -------------------- |
| {name}  | ${X}M           |     {X}%     | {position}  | {where they're weak} |

#### Competitive Dynamics

{How competition works in this market — price wars, feature races, ecosystem lock-in, etc.}

#### Recent Activity

{M&A, funding, product launches, pivots in last 12–18 months}

#### White Space Map

{Segments or needs that current players underserve or ignore}

### 3. Trends & Drivers

#### Growth Drivers

1. {Driver} — {data} [source]

#### Headwinds

1. {Restraint} — {data} [source]

#### Emerging Disruptions

{Technology or business model shifts that could reshape the market}

### 4. Customer Landscape

#### Primary Segments

| Segment | Size | Growth | Pain Intensity | Willingness to Pay |
| ------- | ---- | ------ | :------------: | :----------------: |
| {name}  | {X}  | {X}%   |    {H/M/L}     |      {H/M/L}       |

#### Buyer Behavior

{How customers discover, evaluate, and purchase in this market}

#### Unmet Needs

{Needs that current solutions fail to address well}

### 5. Regulatory & Macro

{Key regulatory and macroeconomic factors affecting this market}

---

## Part II: Product Evaluation

### 6. Problem Validation

#### The Problem

{Clear statement of the problem this product addresses}

#### Severity & Frequency

{How painful and how often — with evidence}

#### Current Alternatives

| Alternative | Satisfaction | Cost | Switching Effort |
| ----------- | :----------: | ---- | :--------------: |
| {solution}  |    {1-5}     | {$X} |     {H/M/L}      |

#### Pain Signal Evidence

{Reviews, forums, survey data, complaint patterns — cited}

### 7. Product-Market Fit Score

| Dimension            | Score (1-5) | Evidence        |
| -------------------- | :---------: | --------------- |
| Problem severity     |     {X}     | {justification} |
| Market size          |     {X}     | {justification} |
| Competition gap      |     {X}     | {justification} |
| Timing               |     {X}     | {justification} |
| Differentiation      |     {X}     | {justification} |
| Monetization clarity |     {X}     | {justification} |
| Customer access      |     {X}     | {justification} |
| **Overall**          |  **{avg}**  |                 |

#### Interpretation

{What the score means and what it implies for the product}

### 8. Market Timing

#### Why Now?

{What has changed that makes this product possible or necessary today?}

#### Adoption Curve Position

{Where is the market: innovators, early adopters, early majority?}

#### Catalysts

{Recent events accelerating demand}

#### Too Early / Too Late Risk

{Assessment with historical parallels if available}

---

## Part III: Business Viability

### 9. Business Model

#### Revenue Model

{Recommended model with rationale — subscription, marketplace, usage-based, etc.}

#### Pricing Benchmarks

| Competitor / Comparable | Model   | Price Point | Notes   |
| ----------------------- | ------- | ----------- | ------- |
| {name}                  | {model} | ${X}/mo     | {notes} |

#### Recommended Pricing Range

{Suggested price point or range with reasoning}

### 10. Unit Economics (Estimates)

| Metric                          | Estimate   | Basis                              |
| ------------------------------- | ---------- | ---------------------------------- |
| Customer Acquisition Cost (CAC) | ${X}       | {industry benchmark or comparable} |
| Lifetime Value (LTV)            | ${X}       | {assumptions: ARPU × retention}    |
| LTV:CAC Ratio                   | {X}:1      | {healthy if >3:1}                  |
| Gross Margin                    | {X}%       | {comparable company data}          |
| Payback Period                  | {X} months | {CAC ÷ monthly margin}             |

{Caveats on these estimates — early-stage numbers are inherently uncertain}

### 11. Go-to-Market Strategy

#### Positioning

{Where this product sits vs competitors — and the narrative}

#### Beachhead Segment

{Which specific customer segment to win first, and why}

#### Primary Channels

| Channel   |   Fit   | CAC Estimate | Rationale                |
| --------- | :-----: | :----------: | ------------------------ |
| {channel} | {H/M/L} |     ${X}     | {why this channel works} |

#### Launch Playbook

1. **Months 1–3:** {validation / beta / early adopters strategy}
2. **Months 4–6:** {initial growth strategy}
3. **Months 7–12:** {scaling strategy}

---

## Part IV: Risk & Recommendation

### 12. SWOT (Product-Specific)

|              | Positive                  | Negative               |
| ------------ | ------------------------- | ---------------------- |
| **Internal** | **Strengths:** {list}     | **Weaknesses:** {list} |
| **External** | **Opportunities:** {list} | **Threats:** {list}    |

### 13. Key Risks

| Risk   | Likelihood | Impact  | Mitigation            |
| ------ | :--------: | :-----: | --------------------- |
| {risk} |  {H/M/L}   | {H/M/L} | {mitigation strategy} |

### 14. Verdict & Recommendations

#### Overall Assessment: {GO / CONDITIONAL GO / PAUSE / NO-GO}

{3–4 sentence summary of why}

#### If GO — Priority Actions

1. {Action 1} — {timeline}
2. {Action 2} — {timeline}
3. {Action 3} — {timeline}

#### Open Questions to Resolve

1. {Question} — {how to answer it}
2. {Question} — {how to answer it}

---

## Sources

[1] {Title} — {URL} (accessed {date})
[2] {Title} — {URL} (accessed {date})
...
```

---

## Competitive Battlecard Template

Focused comparison of specific competitors.

```markdown
# Competitive Battlecard: {Market}

**Date:** {date}

## Landscape Overview

{1-paragraph competitive dynamics summary}

## Player Comparison

| Dimension          | {Company A} | {Company B} | {Company C} |
| ------------------ | ----------- | ----------- | ----------- |
| **Revenue**        | ${X}M       | ${X}M       | ${X}M       |
| **Market Share**   | {X}%        | {X}%        | {X}%        |
| **Founded**        | {year}      | {year}      | {year}      |
| **Employees**      | {X}         | {X}         | {X}         |
| **Funding**        | ${X}M       | ${X}M       | ${X}M       |
| **Key Strength**   | {text}      | {text}      | {text}      |
| **Key Weakness**   | {text}      | {text}      | {text}      |
| **Target Segment** | {text}      | {text}      | {text}      |
| **Pricing Model**  | {text}      | {text}      | {text}      |

## Competitive Positioning Map
```

            High Price
                |
    Premium     |    Luxury
    Leaders     |    Niche
                |

───────────────┼───────────────
|
Budget | Emerging
Challengers | Disruptors
|
Low Price

```

## Recent Moves (Last 12 Months)
- **{Company A}:** {action} ({date}) [source]
- **{Company B}:** {action} ({date}) [source]

## Sources
[1] {URL}
...
```

---

## Market Entry Assessment Template

For evaluating whether to enter a specific market.

```markdown
# Market Entry Assessment: {Market}

**Date:** {date} | **Scope:** {geography}

## Market Attractiveness (Score: {X}/10)

### Size & Growth

- Current size: ${X}B [source]
- Growth: {X}% CAGR [source]
- **Score: {X}/10**

### Competitive Intensity

- Number of major players: {X}
- Market concentration (HHI or CR4): {metric}
- Barriers to entry: {High/Medium/Low}
- **Score: {X}/10**

### Customer Access

- Target segments clearly identifiable: {Yes/No}
- Customer acquisition channels: {list}
- Switching costs: {High/Medium/Low}
- **Score: {X}/10**

### Regulatory Complexity

- Key regulations: {list}
- Compliance cost: {High/Medium/Low}
- **Score: {X}/10**

## Go / No-Go Recommendation

{Recommendation with rationale based on scores above}

## Key Risks

1. {Risk 1} — Likelihood: {H/M/L}, Impact: {H/M/L}
2. {Risk 2} — Likelihood: {H/M/L}, Impact: {H/M/L}

## Sources

[1] {URL}
...
```

---

## Trend Deep-Dive Template

For focused analysis on industry trends and future direction.

```markdown
# Trend Analysis: {Market / Topic}

**Date:** {date}

## Trend Summary

{Overview paragraph describing the macro shift}

## Key Trends

### 1. {Trend Name}

- **What:** {description}
- **Evidence:** {data points with sources}
- **Impact:** {who is affected and how}
- **Timeline:** {when this becomes mainstream}
- **Confidence:** {High/Medium/Low — based on source quality}

### 2. {Trend Name}

...

## Convergence & Interactions

{How these trends interact or reinforce each other}

## Implications

- **For incumbents:** {impact}
- **For startups:** {opportunities}
- **For investors:** {signals to watch}

## Signals to Monitor

- {Leading indicator 1}
- {Leading indicator 2}

## Sources

[1] {URL}
...
```

---

## Investment / Due Diligence Template

For evaluating a specific company within a market context.

```markdown
# Market Due Diligence: {Company} in {Market}

**Date:** {date}

## Company Overview

| Metric         | Value           |
| -------------- | --------------- |
| Founded        | {year}          |
| HQ             | {location}      |
| Employees      | {count}         |
| Revenue (est.) | ${X}M           |
| Funding        | ${X}M ({stage}) |
| Key Product    | {name}          |

## Market Position

- Estimated market share: {X}% [source]
- Positioning: {leader/challenger/niche/emerging}
- Key differentiator: {text}

## Market Context

- Total market: ${X}B [source]
- Growth: {X}% CAGR [source]
- {Company}'s addressable segment: ${X}B

## Competitive Moat

- {Moat factor 1}: {Strong/Moderate/Weak}
- {Moat factor 2}: {Strong/Moderate/Weak}

## Risks

1. {Market risk} [source]
2. {Competitive risk} [source]
3. {Execution risk}

## Sources

[1] {URL}
...
```
