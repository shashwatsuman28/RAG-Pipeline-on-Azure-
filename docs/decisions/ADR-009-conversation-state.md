# ADR-009: Conversation State and Persistence

**Status**: Pending data policy and user workflow

## Context

FR-006 requires conversational context isolated by principal; retention and deletion are not defined.

## Options

- Stateless requests with client-supplied context (requires strong trust/size controls).
- Persisted thread state/checkpointer in an approved store.
- Bounded recent-turn state with evaluated summary/trim policy.

## Decision

No store, duration, memory policy, or LangChain persistence adapter is selected.

## Rationale

Current LangChain guidance supports state per thread and production checkpointers, but storage, privacy, retention, deletion, and scale are project policy decisions.

## Consequences

Identity binding, token budgets, old-citation reauthorization, deletion propagation, encryption, expiry, and failure recovery must be designed. In-memory examples are not production state.

## Dependencies

Data classification, conversation UX, retention, availability, owner access, and workload.

## References

- [LangChain short-term memory](https://docs.langchain.com/oss/python/langchain/short-term-memory), accessed 2026-11-02.