# Backend principles, trends, and checklist

## Design principles

| Principle | Practice |
|-----------|----------|
| **Cohesion** | Modules change together; avoid “god services.” |
| **Coupling** | Integrate through stable contracts (schemas, events), not shared DB tables across bounded contexts when avoidable. |
| **Explicit failure** | Timeouts, retries with backoff, circuit breaking where appropriate; no infinite blocking. |
| **Least privilege** | Credentials scoped minimally; audit sensitive operations. |

## Modern software engineering (server)

- **Testing**: unit for domain; contract tests at API edges; integration tests for DB and queues; smoke tests for deploy pipelines.
- **Migrations**: reversible where possible; backward-compatible rollout (expand/contract) for zero-downtime.
- **Configuration**: 12-factor style—environment for environment-specific values; feature flags for risky behavior change.
- **Observability**: correlation IDs; structured JSON logs; RED metrics for services (rate, errors, duration).

## API and contract trends

| Topic | Guidance |
|-------|----------|
| **REST** | Resources, consistent verbs, problem+json or consistent error envelope. |
| **GraphQL** | N+1 awareness (dataloaders), complexity limits, auth per field. |
| **Events** | Outbox/inbox for reliable delivery; idempotent consumers; schema evolution (compat rules). |
| **Versioning** | URL or header strategy documented; deprecation policy. |

## Data and consistency

- Choose **transaction boundaries** to match invariants; document when **read-your-writes** is not guaranteed.
- **Indexes** match real query patterns; avoid silent full table scans on hot paths.
- **Caches**: TTL and invalidation strategy explicit; stampede mitigation for hot keys.

## Security baseline

- Validate and normalize all external input; parameterized queries; output encoding where generating markup.
- **AuthZ** checked at handler/use-case layer, not only at API gateway.
- Rate limiting and abuse controls for public endpoints.

## Anti-patterns to flag

- **Anemic domain** with all logic in controllers/handlers untested.
- **Distributed monolith**—synchronous chains across many services without timeouts.
- **Logging PII** or secrets in plain text.
- **Retry storms** without jitter and caps.

## Quick review checklist

- [ ] Authorization enforced for the operation, not only authentication.
- [ ] Errors won’t leak stack traces or internal IDs to untrusted clients (unless intended).
- [ ] Database access uses migrations; no silent schema drift.
- [ ] Background work has retry/dead-letter story; poison messages handled.
- [ ] External calls have timeouts and metrics.
