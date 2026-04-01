# Humanizer

A Cursor skill that transforms AI-generated text into writing that reads as authentically human and passes AI detection tools.

## What's different about v4

Most "humanizer" tools only strip obvious AI tics (buzzwords, em dashes, emoji). That's necessary but insufficient — clean, sterile text still gets flagged because detectors also measure **statistical properties**: perplexity (word predictability), burstiness (sentence-length variation), and token probability distributions. Modern detectors (2025+) also use sentence-level classification and epistemic consistency analysis.

This skill uses a three-pass method:

1. **Strip** — Remove 30 known AI writing patterns (based on Wikipedia's AI Cleanup project, plus 6 new reasoning/structure patterns)
2. **Inject** — Add human writing signals: burstiness, perplexity variation, structural unpredictability, voice, epistemic texture, micro-imperfections
3. **Audit** — Self-check against heuristics used by GPTZero, Originality.ai, Turnitin, ZeroGPT, Copyleaks, and Winston AI

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
| `SKILL.md` | Core skill — three-pass method, 30 pattern watchlists, human signal injection (including epistemic texture), detector audit checklist |
| `patterns.md` | Reference — detailed before/after examples for all 30 AI patterns |
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

### Reasoning and structure patterns (new in v4)
| # | Pattern | What to do |
|---|---------|-----------|
| 25 | Numbered-step reasoning | Weave into prose unless genuinely sequential |
| 26 | Exhaustive balanced coverage | Be lopsided — spend time on what matters |
| 27 | Connector addiction | Delete most transitions; start with the subject |
| 28 | Abstraction over specifics | Name concrete details, numbers, examples |
| 29 | Recursive summarization | Don't restate — move forward |
| 30 | Uniform confidence tone | Vary certainty — be sure, tentative, and uncertain |

## Human signal injection (expanded in v4)

Beyond stripping patterns, the skill teaches the agent to inject signals that mark writing as human:

- **Burstiness** — Vary sentence length between extremes (3 words to 35+), not uniformly medium
- **Perplexity variation** — Use occasionally unexpected but valid word choices to break statistical uniformity
- **Structural unpredictability** — Vary paragraph lengths, break logical order, use abrupt transitions
- **Voice markers** — Contractions, fragments, self-interruption, rhetorical questions, parenthetical asides, position-taking
- **Epistemic texture** (new) — Knowledge provenance ("I read somewhere..."), partial knowledge, changed minds, selective depth, curiosity about open questions
- **Micro-imperfections** — Register shifts, incomplete resolutions, mild intentional repetition, imprecise numbers, mid-thought backtracking
- **Content-type adaptation** — Different strategies for blog posts vs. academic writing vs. emails vs. business reports

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — primary source for the 24 patterns
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) — maintaining organization

## Version history

- **4.0.0** — 6 new patterns (#25-30: reasoning and structure tells), epistemic texture injection, sentence-level detector audit, updated for Copyleaks/Winston AI, expanded micro-imperfections, business/report content type
- **3.0.0** — Major rewrite: three-pass method (Strip/Inject/Audit), human signal injection techniques (burstiness, perplexity, voice), detector audit checklist, expanded AI vocabulary watchlist, content-type adaptation, patterns moved to reference file
- **2.2.0** — Added final "obviously AI generated" audit + second-pass rewrite
- **2.1.1** — Fixed pattern #18 example (curly quotes vs straight quotes)
- **2.1.0** — Added before/after examples for all 24 patterns
- **2.0.0** — Complete rewrite based on raw Wikipedia article content
- **1.0.0** — Initial release

## License

MIT
