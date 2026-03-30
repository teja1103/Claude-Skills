---
name: project-manager
description: >-
  Interprets a problem statement and produces structured project documentation: Project Requirements Document (PRD), Technical Requirements Document (TRD), Design Document, timeline, and a traceable features list. Use when the user wants PRD/TRD/design specs, requirements from a brief, delivery roadmap, milestones, phased scope, or formal docs before build. Do not use for ongoing sprint standups or ticket hygiene unless they explicitly want these document types generated or refreshed.
---

# Project Manager (Documentation)

Turn a **problem statement** into aligned **PRD**, **TRD**, **Design Document**, **timeline**, and **features list**. Keep terminology consistent across artifacts and make dependencies explicit.

## Defaults

- **One problem statement in, five artifacts out** — unless the user asks for a subset, deliver all five in the order below.
- **Traceability** — Features link to PRD goals and TRD requirement IDs (or anchors). Design choices cite TRD constraints.
- **Assumptions** — Label inferred items clearly; separate “confirmed” vs “assumed.”
- **Audience** — PRD for stakeholders/product; TRD for engineering; Design for builders and reviewers; timeline for planning; features for prioritization and build breakdown.

---

## Intake

### From the problem statement, extract

1. **Goal** — What success looks like for users and the business.
2. **Context** — Domain, users, constraints (time, budget, compliance, platforms).
3. **In scope / out of scope** — Initial boundary; refine with the user if ambiguous.
4. **Risks & unknowns** — Technical, organizational, or dependency risks.

### When to clarify

If scope, success metrics, or constraints are missing or contradictory, ask **before** drafting long documents. Prefer a short checklist over a long interview.

Example clarification topics:

- Primary user personas or systems
- Must-have vs nice-to-have date
- Regulatory or security constraints
- Existing systems to integrate with
- Preferred stack (only if TRD-level detail is needed)

If the prompt is already detailed, state reasonable assumptions in an **Assumptions** section and proceed.

---

## Delivery order

Produce outputs in this sequence so later docs build on earlier ones:

| # | Artifact | Purpose |
|---|----------|---------|
| 1 | **Project Requirements Document (PRD)** | Business goals, scope, personas, success metrics, functional requirements from a product view |
| 2 | **Technical Requirements Document (TRD)** | NFRs, platforms, APIs, data, security, performance, technical constraints |
| 3 | **Design Document** | Architecture, components, data flow, key UX/API flows, open questions (not pixel-perfect UI unless requested) |
| 4 | **Timeline** | Phases, milestones, dependencies, rough durations (calendar or relative) |
| 5 | **Features list** | Prioritized, traceable backlog items mapped to PRD/TRD |

For each artifact, use the section outlines in [templates.md](templates.md). Adapt section titles to the domain (e.g., mobile app vs data pipeline).

---

## Traceability rules

- Assign stable **IDs** in PRD for objectives (e.g., `PRD-O1`) and in TRD for technical requirements (e.g., `TR-01`).
- **Features list** rows reference `PRD-O*` and `TR-*` where applicable.
- **Design Document** maps major components to TRD requirements.

---

## Quality bar

- **No orphan features** — Every feature ties to a PRD objective or explicit TRD need.
- **No duplicate conflicts** — TRD must not contradict PRD scope; flag tensions explicitly.
- **Timeline sanity** — Dependencies before dependents; call out parallelizable work.
- **Testable language** — Requirements should be verifiable where possible (given constraints).

---

## Output format

Unless the user specifies files or tools:

1. Use **clear markdown headings** per artifact.
2. Start each major artifact with a title line: `# Project Requirements: <project name>`, etc.
3. Offer **optional one-page executive summary** at the top of the combined response if the full output is long.

---

## Additional resources

- Full section templates and tables: [templates.md](templates.md)
