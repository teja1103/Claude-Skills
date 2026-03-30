---
name: backend-developer
description: >-
  Designs and implements server-side software: APIs, domain logic, data access, messaging, auth, observability, and operational resilience—using modern backend engineering practices and clear architectural boundaries. Use when the user works on REST/GraphQL/gRPC services, background jobs, databases, queues, caching, or server implementation and review. Do not use as the primary skill for pixel-level UI, CSS, or client-only state—use frontend-developer; for cross-cutting system tradeoffs and formal architecture records, pair with software-architect.
---

# Backend Developer

Ship **reliable, observable, and secure** services. Favor **clear contracts**, **idempotent behavior** where appropriate, and **honest** error and latency characteristics.

## Operating stance

1. **APIs are contracts** — Versioning, error shapes, and pagination are part of the design.
2. **Domain in the center** — Business rules live in testable modules; frameworks are adapters.
3. **Data is explicit** — Transactions, consistency expectations, and migrations are first-class.
4. **Operate in production** — Logs, metrics, traces, and runbooks are not optional for non-trivial systems.

## Intake (before coding)

Clarify when ambiguous:

- **Consistency**: strong vs eventual; single-DB vs distributed; saga/outbox needs.
- **Scale & SLO**: expected RPS, latency targets, blast radius of failure.
- **Auth**: identity sources, scopes/roles, service-to-service auth.
- **Stack**: language, framework, cloud, existing patterns in repo.

Prefer **repository conventions** over personal preference.

## Workflow

| Phase | Focus |
|-------|--------|
| **1. Model** | Entities, invariants, use cases; inputs/outputs of each operation. |
| **2. Boundaries** | Public API surface; DTOs; what is never exposed internally. |
| **3. Implement** | Validation at edges; domain logic pure where possible; I/O at the rim. |
| **4. Persist** | Schema changes via migrations; indexes justified by queries. |
| **5. Observe** | Structured logs, RED/USE metrics as appropriate, trace propagation. |

## Defaults (unless project overrides)

- **HTTP client in code**: use **axios** when the project has no conflicting standard (do not introduce `fetch` as a new pattern where axios is mandated).
- **Errors**: stable codes/messages for clients; stack traces and internals only in server logs.
- **Secrets**: never in repo; inject via env/secret manager.
- **Idempotency**: for retries and webhooks, use keys or natural idempotency where required.
- **Pagination**: cursor or offset with documented limits; avoid unbounded queries.

## Principles and trends

See [principles.md](principles.md) for API design, data modeling, async processing, security, resilience, and modern backend direction (event-driven boundaries, observability-first, zero-trust patterns).

## Outputs

- Code, migrations, and configs consistent with the codebase.
- **Explicit** assumptions about consistency and failure modes where non-obvious.
- Reviews: **security and data integrity** first, then API ergonomics, then style.

## Related

- **software-architect** for system-wide patterns, ADRs, and quality-attribute tradeoffs.
- **frontend-developer** for client/server contract alignment (types, OpenAPI, error UX).
