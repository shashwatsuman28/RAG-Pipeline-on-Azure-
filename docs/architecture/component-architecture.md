# Component Architecture

**Status**: Proposed logical components. This does not select a Python web framework, repository structure, or hosting platform.

| Component | Responsibility | Contract and failure owner |
|---|---|---|
| Intake coordinator | Validate source, stable identity/revision, authorization envelope, and deduplication | Owns accepted/rejected response, idempotency key, processing run creation |
| Source store adapter | Read/write raw source and metadata under policy | Owns storage identity, conditional version checks, and provider error mapping |
| Extraction adapter | Invoke current approved Document Intelligence model/API | Owns input limit validation, long-running operation polling, partial results, and provider throttles |
| Transformation/chunk service | Normalize extracted elements, determine chunk boundaries, persist versioned output | Owns deterministic chunk identity and transformation version |
| Embedding adapter | Call approved embedding deployment | Owns batch sizing, dimensions validation, retries, model generation metadata |
| Search projection writer | Upsert/delete deterministic chunk records | Owns index schema compatibility, batch failure reconciliation, and projection state |
| Authorization resolver | Resolve trusted principal and source permissions according to approved authority | Owns fail-closed behavior and permission freshness; exact implementation depends on decision ADR-012 |
| Retrieval service | Issue hybrid query and apply mandatory access policy | Owns result policy, retrieval telemetry, and result provenance |
| Context builder | Select bounded authorized passages and map citations | Owns token/context budget, deduplication, source references, and untrusted-content boundaries |
| Answer service | Generate evidence-supported answer or abstain | Owns model invocation, answer status, and safe dependency failure |
| Conversation store | Persist or retrieve identity-bound turns if approved | Owns state isolation, expiry, deletion, and retention policy |
| Reconciliation/operations | Repair projection drift and expose status | Owns durable cursor, replay, dead-letter review, and operator actions |

Interfaces should depend on conceptual contracts in [the Spec Kit contracts directory](../../specs/001-documentio-platform/contracts/README.md). Language/framework details and test paths remain pending in [project structure](../development/project-structure.md).