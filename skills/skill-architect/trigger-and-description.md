# Trigger and description craft

The `description` field is the main discovery surface. Skills are often **under-triggered**—the model does not consult them when it should. Design for that.

---

## What belongs in `description`

Write in **third person**. Include:

1. **Capabilities** — concrete verbs and artifacts (not marketing fluff).
2. **Trigger scenes** — user goals, domains, file types, stack names.
3. **Exclusions** — adjacent requests that **should not** invoke this skill (near-misses beat absurd negatives).

Optional fourth: **co-occurring terms** — things users say together when they mean this skill (“dashboard + internal metrics”, “PDF + form fields”).

**Avoid:** Storing exclusive trigger lists only in the body—metadata readers will not see them.

---

## Trigger probe set (manual optimization)

Build **10–20 probes**:

| Class | Count | Content |
|-------|-------|---------|
| **Should trigger** | 8–12 | Varied tone, length, specificity; some **without** naming the skill explicitly |
| **Should not** | 8–12 | **Near-misses**: share vocabulary but differ in intent or better tool |

**Good negative:** For a PDF form skill — “Export this **Google Form** responses to CSV” (different object).

**Bad negative:** “Compute fibonacci” — teaches nothing.

**Good positive:** Messy real prompt with filenames, typos, and constraints.

**Weak positive:** “Extract text from PDF” — may be too trivial for skill consultation.

---

## Under-trigger vs over-trigger

| Symptom | Likely fix |
|---------|------------|
| Misses real cases | Add synonyms, user phrasings, deliverables, and domains to description |
| Fires on adjacent tasks | Strengthen **exclusions**; name the competing workflow |
| Fires on trivial tasks | Accept some misses; or make description explicitly **multi-step / specialized** |

---

## “Pushy” vs spammy

Pushy (good): cover paraphrases and common adjacent confusions.

Spammy (bad): huge keyword lists that match everything—causes over-trigger and dilutes signal.

**Heuristic:** If removing a phrase changes nothing in practice, delete it.

---

## After editing SKILL.md

Body changes can drift from metadata. Re-run a **3-probe sanity** on triggers whenever you:

- Add/remove a major workflow section, or
- Change tools/scripts the skill depends on.
