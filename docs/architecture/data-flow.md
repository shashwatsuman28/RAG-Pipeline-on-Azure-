# Data Flow Architecture

**Status**: Proposed lifecycle; exact event source, storage layout, and permission synchronization remain pending.

```mermaid
sequenceDiagram
  participant O as Operator / approved connector
  participant I as Intake coordinator
  participant B as Raw source candidate
  participant D as Document Intelligence v4 candidate
  participant P as Processing / Databricks candidate
  participant E as Embedding deployment candidate
  participant S as Azure AI Search candidate
  O->>I: Source + trusted origin context + idempotency input
  I->>I: Validate policy, type/limit, identity, revision
  I->>B: Persist original + revision metadata
  I->>D: Analyze approved document revision
  D-->>I: Elements + locations + partial/error state
  I->>P: Versioned extraction result
  P->>P: Normalize, transform, chunk, stable IDs
  P->>E: Batch chunk text + model generation
  E-->>P: Vectors + dimensions + model identity
  P->>S: Deterministic upsert with text, vector, provenance, permission metadata
  S-->>I: Per-document index result
  I->>I: Mark active only after confirmed projection and policy checks
```

**Query flow**: authenticated caller -> trusted principal resolution -> mandatory permission filter/token policy -> hybrid BM25/vector search -> bounded authorized context with source references -> chat model -> answer or abstention -> citations rechecked against current authorization -> response.

**Update/delete flow**: notification triggers lookup; coordinator compares current authoritative revision/permission state; processing generation is idempotent; old active search records are superseded only after replacement is safe; deletion removes all in-scope derived data unless a policy/legal hold requires a documented retained state. Reconciliation catches delayed, duplicated, or missed events.

**Failure boundaries**: extraction may partially succeed; embedding and search may throttle or return partial batch errors; network timeouts may hide whether writes committed. Record stage state and reconcile by deterministic identity before retry. Never advance active source revision based on event arrival alone.