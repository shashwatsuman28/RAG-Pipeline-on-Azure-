# Data Lifecycle

**Status**: Lifecycle principles are required; durations and legal exceptions are pending.

1. **Receive**: validate origin, type/limits, source identity/revision, and permission context.
2. **Store**: retain the original in the approved raw store; record checksum/version and access boundary.
3. **Process**: create run, extraction, normalized elements, chunks, and embeddings with version lineage.
4. **Publish**: write a deterministic search projection; activate a revision only after required consistency/authorization checks.
5. **Update**: process new revision without losing old-state traceability; safely supersede after publication.
6. **Delete/hold**: propagate deletion or approved retention/legal hold through source, processed outputs, vectors/index, caches, conversations, logs, and backups in scope.
7. **Reconcile**: compare authoritative state with active derived projections; repair drift and record result.

No retention period, backup retention, deletion service level, purge guarantee, or legal hold policy is asserted. Product, data, security, and legal owners must approve these before using real content.