# Proposed Interface Boundaries

**Status**: Conceptual contracts only. This folder does not define implemented APIs, service URLs, credentials, or deployment configuration.

## Boundaries

| Boundary | Producer -> consumer | Required contract behavior |
|---|---|---|
| Source intake | Approved client/source connector -> ingestion boundary | Source identity, revision/digest, media type, authorization context, idempotency key, size validation, and acceptance/rejection result. Transport and payload are pending. |
| Extraction result | Extractor -> processing pipeline | Model/API version, source revision, extracted elements, source spans/locations, partial warnings, stable result status, and retryable/terminal error classification. |
| Processed chunk | Transformation pipeline -> embedding/index pipeline | Stable document/revision/chunk identity, chunking version, text, provenance, permission metadata reference, and schema version. Exact schema pending. |
| Search projection | Index writer -> Azure AI Search | Deterministic key, text, metadata, vector/model/dimension identity, authorization filter fields, and upsert/delete semantics. Index schema pending ADR approval. |
| Retrieval request/result | Question-answering service -> search service | Authenticated principal context, query, hybrid retrieval config, mandatory authorization filter/token policy, result provenance, and explicit empty/filtered result. |
| Generation context/result | Orchestrator -> Azure model deployment -> caller | Bounded authorized context, instruction hierarchy, citation mapping, model/deployment version, grounded/abstain/failure state, and safe error mapping. API shape pending. |
| Change/reconciliation event | Storage or processing event source -> ingestion coordinator | At-least-once-safe event handling; verify source/topic; compare revision/ETag/sequencer; deduplicate; checkpoint; reconcile source-of-truth state. Event schema is provider-dependent. |

## Cross-Boundary Invariants

- A source revision and processing pipeline version are explicit throughout extraction, chunking, embedding, and indexing.
- Event arrival is not proof of freshness or authorization. Read current source state and fail closed for unknown permission data.
- Every external call has a timeout, bounded retry/backoff for transient failures, retry-after/throttle handling where supplied, correlation identity, and a terminal-failure path.
- An operation with unknown commit outcome is reconciled by deterministic identity before retrying.
- Content and permission metadata are independently classified; logs must not duplicate protected document payloads.
- APIs and payload schemas are proposals. Product owner must approve clients and security owner must approve identity/permission semantics before formal contract design.