# Frontend principles, trends, and checklist

## Design principles (non-negotiables)

| Principle | Practice |
|-----------|----------|
| **Clarity** | One purpose per component; names reflect behavior, not implementation trivia. |
| **Consistency** | Reuse tokens (spacing, type, color); avoid one-off magic numbers tied to a single screen. |
| **Feedback** | Loading, success, error, empty states are designed, not improvised. |
| **Accessibility** | Keyboard, focus, contrast, motion preferences; form labels and errors programmatically associated. |
| **Resilience** | Graceful degradation when JS fails or network is slow (where product allows). |

## Modern software engineering (client)

- **Types or contracts**: TypeScript types, or JSDoc where untyped; prop shapes stable across refactors.
- **Testing**: Unit for pure logic; component tests for behavior; e2e for critical paths—proportion matches risk.
- **Observability**: Meaningful client errors (breadcrumbs/context) without leaking PII in logs.
- **Security**: XSS-safe patterns (avoid `dangerouslySetInnerHTML` without sanitization); safe links (`rel` where needed); CSP awareness if project uses it.

## Platform and practice trends (use judiciously)

| Area | Trend | Guidance |
|------|--------|----------|
| **Rendering** | SSR, islands, server components (ecosystem-specific) | Match framework; avoid double data-fetch waterfalls; clarify server vs client boundaries. |
| **State** | Signals, lightweight stores, server cache libraries | Prefer minimal state; derive when possible; avoid global soup. |
| **Styling** | Design tokens, container queries, cascade layers | Tokens first; component-scoped CSS where it reduces leakage. |
| **DX** | Strict linting, formatters, Storybook/Ladle | Align with repo; document stories for reusable components. |
| **Performance** | INP, LCP, CLS as Core Web Vitals | Measure before micro-optimizing; fix layout shift and long tasks provably. |

## Anti-patterns to flag

- **Prop drilling** beyond ~3 levels without composition or context with a clear scope.
- **useEffect** for things that are really data derivation or event handlers (framework-specific smell).
- **Accessibility as an afterthought**—retrofitting aria without fixing structure.
- **Copy-paste** across routes instead of shared primitives (when duplication is not accidental).

## Quick review checklist

- [ ] Interactive controls are buttons/links/inputs appropriately.
- [ ] Focus order makes sense; modals trap focus and restore on close.
- [ ] Images and media have alt text or decorative handling.
- [ ] Forms: labels, errors, disabled vs loading states distinguished.
- [ ] No unnecessary client bundle weight (lazy routes where appropriate).
- [ ] Keys in lists are stable identifiers.
