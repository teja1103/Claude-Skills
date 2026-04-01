---
name: humanizer
version: 4.0.0
description: |
  Transform AI-generated text into writing that reads as authentically human and
  passes AI detection tools (GPTZero, Originality.ai, Turnitin, ZeroGPT, Copyleaks,
  Winston AI). Use when editing, reviewing, or rewriting text to remove AI fingerprints.
  Applies a three-pass method: strip 30 known AI patterns (content, language, style,
  structure, reasoning), inject human writing signals (burstiness, perplexity variation,
  voice, epistemic texture), and audit against detector heuristics including token
  probability analysis and sentence-level classification.
---

# Humanizer: Defeat AI Detection

AI detectors measure two things: **pattern recognition** (known AI writing tics) and **statistical analysis** (perplexity, burstiness, token probability distributions). Removing AI tells is necessary but insufficient — sterile, "cleaned up" text still gets flagged because it lacks the statistical fingerprint of human writing. You must also inject authentic human signals.

## Three-pass method

1. **Strip** — Remove all 30 known AI writing patterns
2. **Inject** — Add human signals: burstiness, perplexity variation, voice, epistemic texture, imperfection
3. **Audit** — Self-check against detector heuristics (including sentence-level classifiers), revise remaining tells

---

## Pass 1: Strip AI tells

Scan for and rewrite every instance of these patterns. For detailed before/after examples, see [patterns.md](patterns.md).

### Content patterns

**1. Significance inflation**
Watch: stands/serves as, testament, reminder, vital/significant/crucial/pivotal role/moment, underscores, highlights importance, reflects broader, symbolizing, enduring/lasting, setting the stage, marks a shift, key turning point, evolving landscape, indelible mark, deeply rooted
→ State facts. Cut all editorializing of importance.

**2. Notability name-dropping**
Watch: independent coverage, local/regional/national media outlets, leading expert, active social media presence
→ Cite one specific source with context instead of listing outlets.

**3. Superficial -ing phrases**
Watch: highlighting, underscoring, emphasizing, ensuring, reflecting, symbolizing, contributing to, cultivating, fostering, encompassing, showcasing
→ Delete the -ing clause or replace with a sourced factual claim.

**4. Promotional language**
Watch: boasts, vibrant, rich (figurative), profound, enhancing, exemplifies, commitment to, natural beauty, nestled, in the heart of, groundbreaking, renowned, breathtaking, must-visit, stunning
→ Neutral descriptive language. If it sounds like ad copy, cut it.

**5. Vague attributions**
Watch: Industry reports, Observers cite, Experts argue, Some critics, several sources/publications
→ Name a specific source or remove the claim entirely.

**6. Formulaic challenges sections**
Watch: Despite its... faces challenges..., Despite these challenges, Challenges and Legacy, Future Outlook
→ Specific facts about actual problems with dates and details.

### Language patterns

**7. AI vocabulary** (these words appear at far higher rates in post-2023 text)

Core tells: Additionally, align with, arguably, comprehensive, crucial, delve, dive into, emphasizing, empower, enduring, enhance, essentially, evolving, explore (as analysis verb), facet, foster, fundamentally, garner, harness, highlight (verb), holistic, innovative, interplay, intricate/intricacies, key (adj), landscape (abstract), leverage, multifaceted, myriad, navigate (abstract), noteworthy, nuanced, paradigm, pivotal, plethora, realm, robust, showcase, streamline, synergy, tapestry (abstract), testament, transformative, underscore (verb), unpack, utilize, valuable, vibrant

Phrasing tells: "it is worth noting", "it should be noted", "it bears mentioning", "one cannot overstate", "at its core", "in today's [X]", "the intersection of", "when it comes to", "a testament to"

→ Replace with plain words. "Additionally" → "Also" or just start the sentence. "Utilize" → "Use". "Leverage" → "Use". "Navigate the landscape" → describe what's actually happening.

**8. Copula avoidance**
Watch: serves as, stands as, marks, represents [a], boasts, features, offers [a]
→ Use "is", "are", "has". Simple verbs are human.

**9. Negative parallelisms**
Watch: Not only...but..., It's not just X, it's Y, not merely...but...
→ State the point directly. Drop the rhetorical contrast.

**10. Rule of three**
→ Use the natural number of items. Often two, sometimes four, sometimes one. Three every time is a tell.

**11. Synonym cycling** (elegant variation)
→ Repeat the clearest term. "Protagonist" four times beats "protagonist/main character/central figure/hero."

**12. False ranges**
Watch: from X to Y constructions where X and Y aren't on a meaningful scale
→ List items directly without forcing a spectrum.

### Style patterns

**13. Em dash overuse** → Use commas, periods, or parentheses. One em dash per 500 words max.

**14. Boldface overuse** → Remove mechanical emphasis. Bold for actual emphasis only.

**15. Inline-header lists** (bolded label + colon + explanation) → Convert to prose or plain list.

**16. Title Case in headings** → Sentence case.

**17. Emojis in structure** → Remove entirely.

**18. Curly quotes** (\u201c...\u201d) → Straight quotes ("...").

### Communication patterns

**19. Chatbot artifacts** — "I hope this helps", "Of course!", "Certainly!", "Would you like...", "Let me know", "Here is a...", "Happy to help"
→ Remove entirely. These are conversation, not content.

**20. Knowledge-cutoff disclaimers** — "as of [date]", "While details are limited...", "based on available information..."
→ Find real sources or remove the claim.

**21. Sycophantic tone** — "Great question!", "You're absolutely right!", "Excellent point!", "That's a really interesting..."
→ Respond directly. Skip the flattery.

### Filler and hedging

**22. Filler phrases** — "In order to" → "To". "Due to the fact that" → "Because". "At this point in time" → "Now". "It is important to note that" → delete. "The system has the ability to" → "The system can".

**23. Excessive hedging** — "could potentially possibly be argued that it might" → "may"

**24. Generic positive conclusions** — "The future looks bright", "Exciting times ahead", "journey toward excellence"
→ End with specific facts, plans, or an honest assessment.

### Reasoning and structure patterns

**25. Numbered-step reasoning where prose would be natural**
Watch: "First, ... Second, ... Third, ... Finally, ..." or "Step 1: ... Step 2: ..." for things that aren't actually sequential.
→ Weave the logic into prose. Humans use numbered steps for actual procedures (recipes, instructions), not for presenting arguments or explaining concepts.

**26. Exhaustive balanced coverage**
Watch: every paragraph covers one "aspect" with equal weight. Topic → history → benefits → challenges → future. AI treats every subject as deserving a five-paragraph essay with equal-length sections.
→ Be lopsided. Spend 80% on the interesting part. Skip the boring parts. Humans write what they care about, not a balanced encyclopedia entry.

**27. Connector addiction**
Watch: every sentence or paragraph opens with a transition word. "However," "Moreover," "Furthermore," "In addition," "Consequently," "Nevertheless," "Similarly," "Conversely."
→ Delete most connectors. Start sentences with the subject. The relationship between ideas is usually obvious from context. Two connectors per 500 words is plenty.

**28. Abstraction over specifics**
Watch: AI summarizes instead of showing. "Various factors contribute to..." "Multiple approaches exist for..." "There are several considerations..."
→ Name the specific factors. Give one concrete example instead of gesturing at many. "The lease was $1,200/month" beats "housing costs were a significant factor."

**29. Recursive summarization**
Watch: the conclusion restates the introduction. The last paragraph of a section echoes the first. Sub-conclusions appear after every section.
→ Don't summarize what you just said. End sections by moving forward (next point, implication, open question), not backward.

**30. Uniform confidence tone**
Watch: AI writes everything with the same mid-level certainty. No sentence is tentative; no sentence is emphatic. Every claim has the same informational temperature.
→ Vary confidence. Some things you're sure about — write them bluntly. Some things you're guessing — say so. "I think" and "definitely" should both appear, in the right places.

---

## Pass 2: Inject human signals

Stripping AI patterns produces clean but sterile text. Detectors flag this too — it has low burstiness and uniform perplexity. Modern detectors (2025+) also look at sentence-level token probability uniformity and epistemic consistency. This pass adds the statistical and cognitive fingerprint of human authorship.

### Burstiness (sentence-length variation)

AI writes sentences of consistently medium length (15-25 words). Detectors like GPTZero explicitly measure this. Human writing swings between extremes.

**Technique:** After your first rewrite, check sentence lengths. If most fall in the 12-25 word range, break the pattern:

Bad (uniform — gets flagged):
> The tool generates code quickly. It handles boilerplate effectively. Users report mixed experiences with complex tasks. Testing remains important for all outputs.

Good (bursty — passes detection):
> It's fast. Boilerplate, test scaffolding, the repetitive stuff nobody wants to write — it handles that well. But hand it something architecturally complex and you'll spend more time fixing its output than you saved, which sort of defeats the point.

Target a sentence-length mix like: 4, 22, 8, 35, 6, 18, 3, 27 words.

### Perplexity variation (unexpected word choices)

AI picks the most statistically probable next word. This creates uniformly low perplexity — the primary signal detectors use. Humans are less predictable.

**Technique:** Occasionally replace a predictable word with a less common but valid alternative. Use concrete metaphors. Pull in domain-specific terminology.

- "Important" → "non-negotiable" or "the part that'll bite you"
- "Challenging" → "a pain" or "genuinely annoying"
- "Implemented" → "bolted on" or "shipped" or "wired up"
- "Utilized" → just "used" (simpler is often less predictable than the AI-preferred fancy word)

One or two unexpected choices per paragraph. More than that reads as trying too hard.

### Structural unpredictability

AI produces uniform 3-5 sentence paragraphs with smooth logical flow. Humans are messier.

- **Vary paragraph length dramatically.** One-sentence paragraphs. Then a dense 6-8 sentence block. Then two short ones back to back.
- **Break expected order.** Start with the conclusion, then backtrack. Lead with a caveat before the main point.
- **Abrupt transitions.** "Anyway," or "But here's the thing:" or just start a new thought without transition. Not every paragraph needs a connector.
- **Leave threads loose.** Not every point needs resolution. Humans sometimes raise a question and move on without answering it.

### Voice and personality markers

Voiceless writing triggers detectors just like slop does. Build a consistent authorial presence.

**Contractions.** Use them in informal and semi-formal writing. "It's", "don't", "wouldn't", "they're". AI systematically underuses contractions — detectors know this.

**Sentence fragments.** "Not great." "Which is a lot." "Fair enough." Grammatically incomplete, communicatively effective.

**Self-interruption.** "It's mainly useful for — well, actually, it depends on what you mean by useful."

**Rhetorical questions.** "So what does this actually buy you?" "Is that a problem? Depends who you ask."

**Parenthetical asides.** "(I'm still not entirely sure about this one.)" or "(your mileage may vary)"

**Position-taking.** AI hedges everything. Humans commit. "This is a bad idea." beats "This could potentially present challenges."

**Temporal grounding.** "Last week," "back when we were still on v2," "the morning after the deploy."

**Register shifts.** Mix formal and informal within a piece. A technical explanation followed by "basically, it's a mess" is human.

**Reader acknowledgment.** "You've probably run into this." "If you've worked with legacy code, you know."

### Epistemic texture

AI writes as an omniscient narrator — it knows everything and has no memory of learning it. Humans have knowledge histories, partial understanding, and learning arcs. This is one of the strongest human signals and one of the hardest for detectors to fake.

- **Knowledge provenance.** "I read somewhere that..." or "A friend who works in biotech told me..." or "The last time I checked this was 2023, so take it with a grain of salt." Humans know *how* they know things.
- **Partial knowledge.** "I can't remember the exact number, but it was something like 40%." "I think it was Kahneman, or maybe Tversky — one of those two." AI never forgets or confuses details; humans routinely do.
- **Changed minds.** "I used to think X, but after [experience], I lean toward Y." Intellectual evolution is deeply human.
- **Selective depth.** Humans know some topics deeply and others superficially, and they signal which is which. "I'm not an expert on this, but from what I've gathered..." vs diving into granular detail on their specialty.
- **Curiosity and gaps.** "I've always wondered why..." or "I still don't fully understand how..." Humans are comfortable with open questions.

### Micro-imperfections

Detectors look for statistical "smoothness." Small irregularities break it.

- **Informal word where formal is expected.** "The API is kind of janky" in an otherwise professional piece.
- **Start sentences with "And" or "But."** And sometimes "So."
- **Mild repetition for emphasis.** "It was slow. Not a little slow. Painfully slow."
- **Hedging in specific spots, not globally.** "I think this works, but I haven't tested edge cases" — hedge one claim, not all of them.
- **Incomplete resolution.** "I'm not sure what the right answer is here. Moving on."
- **Imprecise numbers where AI would be exact.** "About twenty people" not "approximately 20 individuals." "A couple hundred bucks" not "$200."
- **Backtracking mid-thought.** "The main reason is — actually, no, let me back up."

---

## Pass 3: Detector audit

After rewriting, run this self-check against what detectors actually measure. Modern detectors (GPTZero, Originality.ai 3.0+, Copyleaks, Winston AI) use both document-level statistical analysis and sentence-level classification — a single AI-sounding sentence in an otherwise human paragraph can flag the whole section.

**Perplexity check** — Read each sentence: "Would a language model predict this exact word sequence with high confidence?" If yes for most sentences, inject more unexpected choices. Pay special attention to opening sentences of paragraphs — detectors weight these heavily.

**Burstiness check** — Estimate words per sentence. If standard deviation is low (most sentences ±5 words of each other), restructure. Need a mix of very short and very long. Target coefficient of variation > 0.4.

**Vocabulary check** — Scan for any surviving word from the AI vocabulary list (#7). Replace or justify each one. Also check for pattern #27 connector addiction — mass connectors are a strong signal in newer classifiers.

**Sentence-level scan** — Read each sentence individually and ask: "Does this sentence sound like it was generated by a language model?" Detectors now classify at the sentence level and aggregate. Flag sentences that are:
- Perfectly grammatical with no personality
- Generic enough to appear in any article on the topic
- Smoothly connected to the previous sentence with a textbook transition

**Structure check:**
- All paragraphs roughly the same length? Fix.
- Every paragraph flows smoothly from the previous? Break one transition.
- Clear intro-body-conclusion structure? Humans don't always follow it.
- Exhaustive balanced coverage (#26)? Cut the boring parts.
- Recursive summarization (#29)? Cut the recap.

**Epistemic check:**
- Does the text read like an omniscient narrator? Add knowledge provenance.
- Is confidence level uniform throughout? Vary it.
- Any "I don't know" or "I'm not sure" moments? If zero, the text sounds AI-generated regardless of other signals.

**Voice check:**
- Can you identify a specific person behind this writing? If "anyone could have written this," add personality.
- At least one opinion, one question, one specific detail?
- At least one moment of imprecision, uncertainty, or backtracking?

**Read-aloud test** — Read the text aloud. Flag anything that sounds assembled rather than written. Flag anything you wouldn't say to a knowledgeable colleague.

**Final prompt** — "What makes this obviously AI generated?" List remaining tells, fix them. If nothing remains, the text passes.

---

## Content-type adaptation

| Type | Voice | Burstiness | Personality | Formality | Epistemic signals |
|------|-------|-----------|-------------|-----------|-------------------|
| Blog/opinion | Strong first-person | High | Opinions, humor, edge | Casual-medium | High — personal experience, changed minds |
| Technical docs | Authoritative | Medium | Clarity over charm | Medium-formal | Medium — caveats, version notes |
| Essay/article | Distinctive | High | Arguments, uncertainty | Medium | High — sources, intellectual honesty |
| Email | Direct, personal | High | Very human | Casual | High — conversational hedging |
| Academic | Measured | Medium-low | Intellectual humility | Formal | High — citations, limitations, careful claims |
| Social media | Conversational | Very high | Maximum personality | Very casual | Medium — casual uncertainty |
| Business/report | Professional | Medium | Understated | Medium-formal | Medium — data sourcing, assumption framing |

For academic/formal writing: reduce fragments and slang but keep burstiness, unexpected vocabulary, position-taking, and epistemic honesty. Formality does not equal uniformity — formal human writing still varies in sentence length, shows uncertainty, and takes positions.

---

## Output format

1. **Draft rewrite** — AI patterns stripped, human signals injected
2. **Detector audit** — Bullet list of remaining tells (or "None found")
3. **Final rewrite** — Revised after audit
4. **Changes summary** — What was changed and why (optional, if helpful)

---

## Full example

**Input (AI-generated):**
> Great question! Here is an essay on this topic. I hope this helps!
>
> AI-assisted coding serves as an enduring testament to the transformative potential of large language models, marking a pivotal moment in the evolution of software development. In today's rapidly evolving technological landscape, these groundbreaking tools—nestled at the intersection of research and practice—are reshaping how engineers ideate, iterate, and deliver, underscoring their vital role in modern workflows.
>
> At its core, the value proposition is clear: streamlining processes, enhancing collaboration, and fostering alignment. It's not just about autocomplete; it's about unlocking creativity at scale, ensuring that organizations can remain agile while delivering seamless, intuitive, and powerful experiences to users.
>
> Industry observers have noted that adoption has accelerated from hobbyist experiments to enterprise-wide rollouts, from solo developers to cross-functional teams. Additionally, the ability to generate documentation, tests, and refactors showcases how AI can contribute to better outcomes, highlighting the intricate interplay between automation and human judgment.
>
> - 💡 **Speed:** Code generation is significantly faster
> - 🚀 **Quality:** Output quality has been enhanced through improved training
> - ✅ **Adoption:** Usage continues to grow, reflecting broader industry trends
>
> Despite challenges typical of emerging technologies—including hallucinations, bias, and accountability—the ecosystem continues to thrive. In conclusion, the future looks bright. Exciting times lie ahead as we continue this journey toward excellence. Let me know if you'd like me to expand on any section!

**Draft rewrite (Pass 1 + 2):**
> AI coding assistants are fast at the boring parts. Config files, test boilerplate, the repetitive glue code you'd rather not write — that's where they earn their keep. I've used Copilot daily for about a year and it probably saves me twenty minutes a day on that kind of work.
>
> The tricky part is everything else.
>
> Hand it an architectural question and you get something that compiles, looks reasonable, and quietly does the wrong thing. I merged a suggestion last month that passed every lint check we have. Took two days to figure out it was silently swallowing errors in a retry loop. The code looked confident. I just wasn't paying enough attention to question it.
>
> GitHub likes to say Copilot users "accept 30% of suggestions." OK. But acceptance isn't correctness, and correctness isn't value. A 2024 Uplevel study found no real difference in pull-request throughput between teams with AI assistants and teams without. That surprised me, but it matches what I've seen — the time you save on boilerplate gets eaten debugging hallucinated logic.
>
> Some people on my team use it like better autocomplete and review every line. Others turned it off. Both seem fine.
>
> Without tests you're guessing either way. The AI just helps you guess faster, which isn't obviously a good thing.

**Detector audit:**
- ✓ Burstiness: sentence lengths range 3 to 38 words
- ✓ Perplexity: "silently swallowing errors in a retry loop" and "guess faster" are low-probability phrases
- ✓ Voice: clear first-person, opinions stated directly
- ✓ Structure: paragraphs range 1 to 5 sentences, transitions vary
- ✓ No AI vocabulary words detected
- ✓ Contractions used naturally throughout
- Minor: closing line is slightly aphoristic

**Final rewrite:**
> AI coding assistants are fast at the boring parts. Config files, test boilerplate, the repetitive glue code you'd rather not write — that's where they earn their keep. I've used Copilot daily for about a year and it probably saves me twenty minutes a day on that kind of work.
>
> The tricky part is everything else.
>
> Hand it an architectural question and you get something that compiles, looks reasonable, and quietly does the wrong thing. I merged a suggestion last month that passed every lint check we have. Took two days to realize it was silently swallowing errors in a retry loop. The code looked confident. I just wasn't paying enough attention.
>
> GitHub likes to say Copilot users "accept 30% of suggestions." OK. But acceptance isn't correctness, and correctness isn't value. A 2024 Uplevel study found no real difference in pull-request throughput between teams with AI assistants and teams without. That surprised me, but it matches what I've seen — time saved on boilerplate gets eaten debugging hallucinated logic.
>
> Some people on my team use it like better autocomplete and review every line. Others turned it off after it kept suggesting patterns from a deprecated internal library. Both approaches seem reasonable to me.
>
> I don't have a grand conclusion. If you have good test coverage, these tools will probably save you some time on the mechanical stuff. If you don't have tests, the AI will help you ship bugs faster. Make of that what you will.

---

## Reference

Based on [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup, combined with analysis of detection methodologies used by GPTZero (perplexity/burstiness scoring + sentence-level classification), Originality.ai (token probability classifiers), Turnitin (statistical feature analysis), ZeroGPT (sentence structure analysis), Copyleaks (multi-layer neural classification), and Winston AI (document fingerprinting). Patterns #25-30 based on analysis of common structural signatures in post-2024 AI outputs that earlier pattern lists missed.

For detailed before/after examples of all 30 patterns, see [patterns.md](patterns.md).
