# Conversation Management

**Status**: Proposed interface; persistence, expiry, and memory strategy pending data policy.

Conversation identifiers must bind to an authenticated principal and the confirmed single-organization boundary. Every read/write must verify ownership and current access. Stored turns may reference document IDs/revisions and citations; permission changes or deletion may invalidate previous evidence and require rechecking before it is surfaced again.

Current LangChain short-term memory guidance models state per thread and uses a checkpointer for persistence; in-memory state is illustrative, not production persistence. Trimming or summarization may reduce context but can discard evidence, so any summary must retain provenance and be evaluated. Storage product, retention, encryption, transcript visibility, deletion semantics, token budget, and summarization policy are open. See [ADR-009](../decisions/ADR-009-conversation-state.md).