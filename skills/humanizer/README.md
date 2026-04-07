# Humanizer

A Cursor skill that transforms AI-generated text into writing that reads as authentically human and passes AI detection tools.

## What's different about v4

v3 handled general AI text well but had a blind spot: **academic papers**. Research writing triggers Turnitin's sentence-level AI classifier through patterns that are invisible to the general 24-pattern checklist — nominalization chains, uniform sentence complexity, lockstep paragraph structure, passive voice dominance, and citation integration monotony. v4 adds 12 academic-specific patterns, a Turnitin-targeted audit pass, and a section-by-section research paper workflow.

This skill uses a three-pass method:

1. **Strip** — Remove 24 general + 12 academic AI writing patterns
2. **Inject** — Add human writing signals: burstiness, perplexity variation, structural unpredictability, voice, micro-imperfections, and academic-specific techniques (researcher positioning, citation variety, concrete specificity)
3. **Audit** — Self-check against heuristics used by GPTZero, Originality.ai, Turnitin (with sentence-level academic audit), and ZeroGPT

## Installation

### For Cursor (project skill)

Clone into your project's `.cursor/skills/` directory:

```bash
git clone https://github.com/blader/humanizer.git .cursor/skills/humanizer
```

### For Cursor (personal skill)

Clone into your personal skills directory:

```bash
mkdir -p ~/.cursor/skills
git clone https://github.com/blader/humanizer.git ~/.cursor/skills/humanizer
```

## Usage

In Cursor, invoke the skill:

```
/humanizer

[paste your text here]
```

Or ask the agent to humanize text directly:

```
Please humanize this text: [your text]
```

## File structure

| File | Purpose |
|------|---------|
| `SKILL.md` | Core skill — three-pass method, 24 general + 12 academic patterns, human signal injection, Turnitin-specific audit, research paper workflow |
| `patterns.md` | Reference — detailed before/after examples for all 24 general AI patterns |
| `academic.md` | Reference — detailed before/after examples for all 12 academic-specific AI patterns (A1–A12) |
| `README.md` | This file — installation, usage, overview |

## The 24 AI patterns

### Content patterns
| # | Pattern | What to do |
|---|---------|-----------|
| 1 | Significance inflation | State facts without editorializing importance |
| 2 | Notability name-dropping | Cite one specific source with context |
| 3 | Superficial -ing phrases | Delete or replace with sourced claims |
| 4 | Promotional language | Use neutral descriptive language |
| 5 | Vague attributions | Name specific sources or remove |
| 6 | Formulaic challenges | Replace with specific facts and dates |

### Language patterns
| # | Pattern | What to do |
|---|---------|-----------|
| 7 | AI vocabulary | Replace with plain words |
| 8 | Copula avoidance | Use "is", "are", "has" |
| 9 | Negative parallelisms | State the point directly |
| 10 | Rule of three | Use the natural number of items |
| 11 | Synonym cycling | Repeat the clearest term |
| 12 | False ranges | List items directly |

### Style patterns
| # | Pattern | What to do |
|---|---------|-----------|
| 13 | Em dash overuse | Commas, periods, parentheses |
| 14 | Boldface overuse | Remove mechanical emphasis |
| 15 | Inline-header lists | Convert to prose |
| 16 | Title Case headings | Sentence case |
| 17 | Emojis in structure | Remove |
| 18 | Curly quotes | Straight quotes |

### Communication patterns
| # | Pattern | What to do |
|---|---------|-----------|
| 19 | Chatbot artifacts | Remove entirely |
| 20 | Cutoff disclaimers | Find sources or remove |
| 21 | Sycophantic tone | Respond directly |

### Filler and hedging
| # | Pattern | What to do |
|---|---------|-----------|
| 22 | Filler phrases | Shorten or delete |
| 23 | Excessive hedging | Commit to a claim or remove |
| 24 | Generic conclusions | End with specifics |

## Human signal injection

Beyond stripping patterns, the skill teaches the agent to inject signals that mark writing as human:

- **Burstiness** — Vary sentence length between extremes (3 words to 35+), not uniformly medium
- **Perplexity variation** — Use occasionally unexpected but valid word choices to break statistical uniformity
- **Structural unpredictability** — Vary paragraph lengths, break logical order, use abrupt transitions
- **Voice markers** — Contractions, fragments, self-interruption, rhetorical questions, parenthetical asides, position-taking
- **Micro-imperfections** — Register shifts, incomplete resolutions, mild intentional repetition
- **Content-type adaptation** — Different strategies for blog posts vs. academic writing vs. emails
- **Academic burstiness** — Short formal sentences mixed with complex analytical ones (v4)
- **Researcher positioning** — First-person voice, intellectual commitments, specific interpretations (v4)
- **Citation integration variety** — Rotate narrative, parenthetical, embedded, comparative, discursive forms (v4)
- **Concrete specificity** — Replace abstract nominalizations with verbs and specific details (v4)

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — primary source for the 24 patterns
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) — maintaining organization

## The 12 academic AI patterns (v4)

| # | Pattern | What to do |
|---|---------|-----------|
| A1 | Nominalization stacking | Convert abstract noun chains back to verbs |
| A2 | Uniform sentence complexity | Mix short declarative with long analytical sentences |
| A3 | Academic vocabulary inflation | Use plainer equivalents unless term is a defined construct |
| A4 | Lockstep paragraph structure | Vary openers: questions, concessions, data, claims |
| A5 | Formulaic metadiscourse | Replace "The present study seeks to" with varied forms |
| A6 | Passive voice dominance | Convert ≥40% of methodology sentences to active voice |
| A7 | Citation integration monotony | Rotate across 5 citation styles within each section |
| A8 | Triad amplification | Use natural counts, not always three |
| A9 | Qualifier chains | Cut to one qualifier or none |
| A10 | Theoretical name-dropping | Give unequal treatment to theories |
| A11 | Gap rhetoric | State gaps plainly, not grandiose |
| A12 | Hedging uniformity | Commit to some claims, vary hedge constructions |

## Version history

- **4.0.0** — Academic paper support: 12 academic-specific AI patterns (A1–A12), Turnitin sentence-level audit, research paper section-by-section workflow, academic burstiness and voice techniques, citation integration variety, new academic.md reference file
- **3.0.0** — Major rewrite: three-pass method (Strip/Inject/Audit), human signal injection techniques (burstiness, perplexity, voice), detector audit checklist, expanded AI vocabulary watchlist, content-type adaptation, patterns moved to reference file
- **2.2.0** — Added final "obviously AI generated" audit + second-pass rewrite
- **2.1.1** — Fixed pattern #18 example (curly quotes vs straight quotes)
- **2.1.0** — Added before/after examples for all 24 patterns
- **2.0.0** — Complete rewrite based on raw Wikipedia article content
- **1.0.0** — Initial release

## License

MIT
