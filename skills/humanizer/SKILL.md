---
name: humanizer
version: 4.0.0
description: |
  Transform AI-generated text into writing that reads as authentically human and
  passes AI detection tools (GPTZero, Originality.ai, Turnitin, ZeroGPT). Use when
  editing, reviewing, or rewriting text to remove AI fingerprints — including academic
  papers, research dissertations, and essays that must pass Turnitin's sentence-level
  AI scanner. Applies a three-pass method: strip 24 general + 12 academic AI patterns,
  inject human writing signals (burstiness, perplexity variation, voice), and audit
  against detector heuristics. Not for plagiarism or fabricating citations.
---

# Humanizer: Defeat AI Detection

AI detectors measure two things: **pattern recognition** (known AI writing tics) and **statistical analysis** (perplexity, burstiness, token probability distributions). Removing AI tells is necessary but insufficient — sterile, "cleaned up" text still gets flagged because it lacks the statistical fingerprint of human writing. You must also inject authentic human signals.

## Three-pass method

1. **Strip** — Remove all 24 known AI writing patterns
2. **Inject** — Add human signals: burstiness, perplexity variation, voice, imperfection
3. **Audit** — Self-check against detector heuristics, revise remaining tells

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

---

## Academic writing patterns (A1–A12)

Academic text triggers Turnitin's sentence-level classifier differently from blog or opinion writing. These patterns are invisible to the general 24 checks above but cause heavy flagging in research papers. For detailed before/after examples, see [academic.md](academic.md).

**A1. Nominalization stacking** — Chains of abstract nouns where verbs would do: "the cultural determinants of the employee stress experience" → "how culture shapes employee stress." Reduce by ≥50%.

**A2. Uniform sentence complexity** — Every sentence has 2–3 subordinate clauses and lands between 25–50 words. Mix in short declarative sentences (8–12 words) between complex ones. Aim for at least one sub-15-word sentence per paragraph.

**A3. Academic vocabulary inflation** — "conceptualized", "operationalized", "contextually situated", "empirically substantive", "theore­tically informed", "irreducibly personal." Replace with plainer equivalents unless the term is a defined construct in the field.

**A4. Lockstep paragraph structure** — Every paragraph follows: topic sentence → elaboration → citation → bridge to next paragraph. Break the template: start some paragraphs with a question, a concession, a quote, or a direct claim. End some without a bridge.

**A5. Formulaic metadiscourse** — "The present study seeks to", "This research endeavors to", "It is within this framework that." Vary: "We set out to", "The goal here was", "This chapter asks whether."

**A6. Passive voice dominance** — AI defaults to passive in academic writing far more than human researchers do. Mix active and passive. "We interviewed 30 professionals" is legitimate academic prose, not informal.

**A7. Citation integration monotony** — Every citation as (Author, Year) at sentence end. Vary: "As Schein (2017) argued,", "Schein's (2017) framework suggests", "This aligns with earlier work on organizational culture (Schein, 2017; see also Hofstede et al., 2010)."

**A8. Triad amplification** — Groups of three modifiers, nouns, or clauses appearing in nearly every sentence: "accuracy, nuance, and respect." Use the natural count — sometimes two, sometimes four, sometimes one.

**A9. Qualifier chains** — "a critically important and fundamentally significant contribution to the growing body of scholarship." Cut to one qualifier or none.

**A10. Theoretical name-dropping** — Listing 4–5 theories with identical paragraph structure for each. Give unequal treatment: deep engagement with 1–2, brief mention of the rest.

**A11. Gap rhetoric** — "Significant lacunae remain in the existing literature that the present study seeks to address." State the gap plainly: "Few qualitative studies have examined this in Indian workplaces."

**A12. Hedging uniformity** — Every claim hedged identically with "may", "suggests", "appears to." Commit to some claims outright. Hedge others with different constructions: "The evidence points to", "In our reading of the data", "Though preliminary, these findings indicate."

---

## Pass 2: Inject human signals

Stripping AI patterns produces clean but sterile text. Detectors flag this too — it has low burstiness and uniform perplexity. This pass adds the statistical fingerprint of human authorship.

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

### Micro-imperfections

Detectors look for statistical "smoothness." Small irregularities break it.

- **Informal word where formal is expected.** "The API is kind of janky" in an otherwise professional piece.
- **Start sentences with "And" or "But."** And sometimes "So."
- **Mild repetition for emphasis.** "It was slow. Not a little slow. Painfully slow."
- **Hedging in specific spots, not globally.** "I think this works, but I haven't tested edge cases" — hedge one claim, not all of them.
- **Incomplete resolution.** "I'm not sure what the right answer is here. Moving on."

### Academic burstiness and voice

Academic writing can pass detection without sounding casual. The trick is varying complexity while staying formal.

**Sentence-length variation within formality.** Short formal sentences exist. "This matters." "The data were clear." "No pattern emerged." Alternate these with longer analytical sentences. Target: at least 2 sentences under 12 words per paragraph, mixed with 1–2 over 30 words.

**Researcher positioning.** Qualitative and mixed-methods papers expect first person. Use it: "We argue", "In our reading", "Our interpretation differs from", "The interviews revealed something we did not expect." This raises perplexity because AI avoids committing to positions in academic voice.

**Citation integration variety.** Rotate across these forms within a single section:
- Narrative: "Schein (2017) defined culture as..."
- Parenthetical: "...organizational norms (Schein, 2017)."
- Embedded: "Schein's (2017, p. 12) three-level model captures..."
- Comparative: "Unlike earlier models (e.g., Hofstede, 1980), Schein emphasized..."
- Discursive: "The claim that culture operates at unconscious levels (see Schein, 2017) has drawn criticism from..."

**Paragraph openers.** Avoid starting every paragraph with a topic sentence. Academic alternatives:
- A question: "But does hierarchical culture always produce stress?"
- A concession: "Admittedly, this framework has limitations."
- A specific datum: "Participant 7 described her workplace as 'a pressure cooker with a smile.'"
- A methodological aside: "At this point in the analysis, a pattern began to emerge."
- A direct claim: "This explanation is incomplete."

**Concrete specificity over abstraction.** Replace "in organizational contexts" with "in the three IT firms we studied." Replace "research has demonstrated" with "a 2019 meta-analysis of 42 studies found." Specificity is the single strongest perplexity booster in academic text.

**Uneven theoretical treatment.** Real researchers have favorites. Spend a full paragraph engaging with one theory. Mention another in a single sentence. This asymmetry signals human judgment.

---

## Pass 3: Detector audit

After rewriting, run this self-check against what detectors actually measure:

**Perplexity check** — Read each sentence: "Would a language model predict this exact word sequence with high confidence?" If yes for most sentences, inject more unexpected choices.

**Burstiness check** — Estimate words per sentence. If standard deviation is low (most sentences ±5 words of each other), restructure. Need a mix of very short and very long.

**Vocabulary check** — Scan for any surviving word from the AI vocabulary list (#7). Replace or justify each one.

**Structure check:**
- All paragraphs roughly the same length? Fix.
- Every paragraph flows smoothly from the previous? Break one transition.
- Clear intro-body-conclusion structure? Humans don't always follow it.

**Voice check:**
- Can you identify a specific person behind this writing? If "anyone could have written this," add personality.
- At least one opinion, one question, one specific detail?

**Read-aloud test** — Read the text aloud. Flag anything that sounds assembled rather than written. Flag anything you wouldn't say to a knowledgeable colleague.

**Final prompt** — "What makes this obviously AI generated?" List remaining tells, fix them. If nothing remains, the text passes.

### Turnitin-specific audit (for academic papers)

Turnitin classifies each sentence independently, then aggregates. A paper can have some flagged sentences and still pass if enough sentences read as human. Target: fewer than 20% of sentences flagged.

**Sentence-level perplexity sweep.** Read each sentence in isolation. Ask: "Is this the most likely way a language model would phrase this?" If yes, rephrase that sentence — change word order, swap a synonym, add or remove a clause, or restructure entirely. Focus on the sentences that feel most "default."

**Paragraph perplexity uniformity.** If every sentence in a paragraph has similar complexity and vocabulary level, the paragraph will flag even if individual sentences seem fine. Ensure each paragraph contains at least one sentence that differs noticeably in length or structure from its neighbors.

**Nominalization audit.** Count abstract noun phrases per paragraph ("the determination of", "the conceptualization of"). If more than 2 per paragraph, convert some back to verb forms.

**Active/passive ratio.** Check each section. If passive voice exceeds 70% of sentences, convert some to active. Methodology sections are the biggest offenders — "Interviews were conducted" → "We conducted interviews."

**Citation pattern audit.** In any 3-paragraph stretch, check if all citations follow the same integration pattern. If yes, vary at least one.

**Transition audit.** Check paragraph boundaries. If every paragraph's last sentence connects to the next paragraph's first sentence, break 2–3 of these connections. Let some paragraphs just end. Start the next one fresh.

**Section-start audit.** Check the first sentence of each major section. If they all follow the same template ("This section presents/examines/discusses..."), rewrite half of them with a different opening strategy.

---

## Content-type adaptation

| Type | Voice | Burstiness | Personality | Formality |
|------|-------|-----------|-------------|-----------|
| Blog/opinion | Strong first-person | High | Opinions, humor, edge | Casual-medium |
| Technical docs | Authoritative | Medium | Clarity over charm | Medium-formal |
| Essay/article | Distinctive | High | Arguments, uncertainty | Medium |
| Email | Direct, personal | High | Very human | Casual |
| Academic/research | Researcher voice (we/I) | Medium-high | Intellectual honesty, specificity | Formal |
| Social media | Conversational | Very high | Maximum personality | Very casual |

For academic writing: formality does NOT mean uniformity. The biggest mistake is making every sentence the same complexity. Mix short declarative formal sentences with longer analytical ones. Use first person where the discipline allows it (qualitative research, social sciences). Replace abstract nominalizations with verbs. Be specific where AI is vague. Vary citation integration style.

---

## Research paper workflow

When humanizing a full research paper or dissertation, work section by section. Each section type has different AI tells and different strategies.

**Acknowledgements / Preface.** Usually the most human-sounding section already. Light touch: check for AI vocabulary (#7) and formulaic phrases (#22). Preserve the personal voice — it helps establish the author as a real person.

**Abstract.** High-density flagging zone. Rewrite to be concise and specific rather than comprehensive and vague. Name the method, the sample size, the key finding. Avoid "the present study seeks to explore." Say what you found.

**Introduction / Background.** Heaviest AI tell density. Strip nominalization chains (A1), break lockstep paragraphs (A4), vary sentence length aggressively (A2). Add researcher voice: "We chose this topic because..." or "The question driving this study is..." Replace "the evolving landscape" language with specific claims.

**Literature review.** Most repetitive section — AI gives every source identical treatment. Fix: engage deeply with 2–3 key sources (discuss, critique, extend). Mention others briefly. Vary citation integration (A7). Break the "Author (Year) found X. Author (Year) also found Y." chain by grouping, contrasting, or narrating disagreements between sources.

**Theoretical framework.** AI presents each theory as a self-contained paragraph with identical structure. Fix: give theories unequal space (A10). Critique one. Show how two theories conflict. Use the framework to make a specific argument, not just catalogue.

**Methodology.** Passive voice trap (A6). Convert ≥40% of sentences to active voice. Add procedural specifics that raise perplexity: "Interviews lasted between 28 and 52 minutes" instead of "Interviews were conducted." Mention a real decision: "We chose phone interviews over video calls because participants reported feeling more candid without a camera."

**Results / Findings.** Use participant quotes generously — quoted speech from interviews is inherently high-perplexity and will not flag. Frame quotes with varied introductions, not always "Participant X stated that."

**Discussion.** Where researcher voice matters most. Commit to interpretations: "We believe this finding reflects..." rather than "This finding may potentially suggest." Acknowledge surprises: "We did not expect the strong negative reaction to recognition programs." Connect to practice with specifics, not platitudes.

**Conclusion / Implications.** Avoid the generic positive ending (pattern #24). State limitations honestly. Make specific recommendations. End with a question or a grounded claim, not "future research should explore."

For all sections: after rewriting, run the Turnitin-specific audit (Pass 3) on each section independently. If a section still reads as uniformly predictable, inject more variety before moving on.

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

Based on [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup, combined with analysis of detection methodologies used by GPTZero (perplexity/burstiness scoring), Originality.ai (token probability classifiers), Turnitin (statistical feature analysis), and ZeroGPT (sentence structure analysis).

For detailed before/after examples of all 24 general patterns, see [patterns.md](patterns.md). For academic-specific patterns A1–A12, see [academic.md](academic.md).
