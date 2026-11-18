# EVRAYN architecture

EVRAYN separates AI interpretation from deterministic authority and execution.

## Ask EVRAYN path

```mermaid
flowchart LR
  U[User question or instruction] --> I[Ask intake]
  I --> C[Server-supplied project context]
  C --> M[LLM interpretation]
  M --> T[Controlled retrieval tools]
  T --> D[(Authoritative project data)]
  D --> E[Evidence-grounded answer]
  E --> P[Structured response or proposal]
  P --> H{Human decision required?}
  H -->|Yes| A[Human review]
  H -->|No| R[Read-only response]
  A --> G[Deterministic authority gate]
  G --> X[Permitted action]
  X --> L[Audit and state update]
```

## Authority boundary

- **AI may:** interpret language, identify intent, retrieve evidence, classify, summarize and propose.
- **Deterministic system owns:** canonical state, business rules, calculations, timers, authority, permissions, idempotency, routing, execution safety and audit.
- **Humans own:** consequential or ambiguous commercial, technical, quality, legal, payment, safety, cancellation and major-recovery decisions.

The LLM must not directly mutate authoritative procurement state.
