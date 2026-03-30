# Architecture principles, trends, and patterns

## Quality attributes (prioritize explicitly)

Common dimensions—**rank for the initiative**; conflicts are normal.

| Attribute | Questions to ask |
|-----------|-------------------|
| **Performance** | Latency percentiles, throughput, batch vs interactive. |
| **Availability** | SLO/SLA, graceful degradation, blast radius. |
| **Security** | Threat model, data classification, identity lifecycle. |
| **Scalability** | Horizontal vs vertical path; hot partitions. |
| **Maintainability** | Team boundaries, module cohesion, testability. |
| **Cost** | Infra, egress, people time, opportunity cost. |
| **Time to market** | MVP slice, incremental migration. |

## Foundational principles

- **Separation of concerns** — UI, application rules, domain, infrastructure have clear homes.
- **Information hiding** — Stable interfaces; internal change without ripple.
- **Dependency inversion** — Core domain depends on abstractions at boundaries where it pays off (avoid over-abstraction in small systems).
- **Defense in depth** — Security at network, service, and data layers as appropriate.

## Modern software architecture trends (apply with context)

| Trend | What it usually implies |
|-------|-------------------------|
| **Evolutionary architecture** | Fitness functions; incremental, measurable change. |
| **Domain-Driven Design (tactical)** | Aggregates, bounded contexts where complexity warrants. |
| **Modular monolith first** | Clear modules before network split; reduces distributed complexity. |
| **Event-driven / messaging** | Loose coupling, eventual consistency, schema governance. |
| **API platforms** | Developer experience, rate limits, lifecycle, observability as product. |
| **Platform engineering** | Golden paths, paved roads—not blocking all flexibility. |
| **Team Topologies** | Stream-aligned teams; platform/enabling teams where needed; Conway-aware splits. |

## ADR (Architecture Decision Record) — minimal shape

```markdown
# ADR-NN: <Title>

## Status
Proposed | Accepted | Superseded by ADR-XX

## Context
<forces and constraints>

## Decision
<what we will do>

## Consequences
**Positive:** ...
**Negative:** ...
**Risks / follow-ups:** ...

## Alternatives considered
- **Option A:** rejected because ...
- **Option B:** rejected because ...
```

## C4-style layering (conceptual)

1. **Context** — System vs users and external systems.
2. **Containers** — Apps and data stores; deployable units.
3. **Components** — Major parts inside a container (services/modules).
4. **Code** — Usually left to implementation; reference patterns instead of full diagrams here unless requested.

## Anti-patterns in architecture discussions

- **Resume-driven design** — Novel tech without a forcing function.
- **Big design up front** without validation path.
- **Microlith** — Many “services” sharing one database and deployment lockstep.
- **Paper architecture** — Diagrams that teams cannot ship or operate.

## Review checklist

- [ ] Stakeholder goals and NFRs are explicit and ordered.
- [ ] Data ownership and consistency model are clear per boundary.
- [ ] Failure modes and degradation are discussed for critical paths.
- [ ] Security and compliance constraints are reflected in boundaries.
- [ ] Migration/evolution path exists for brownfield.
- [ ] Decisions likely to surprise teams are captured in ADRs.
