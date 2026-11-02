# System Architecture

**Status**: Proposed; no resources or runtime exist.

## Logical Layers

| Layer | Candidate responsibility | Required boundary |
|---|---|---|
| Source intake | Validate approved document and authorization context; assign stable identity/revision | Reject unsupported, over-limit, unauthorized, or corrupt input before processing |
| Raw source | Preserve original content and source metadata | Owner-approved access, lifecycle, immutability/version, deletion, and region policy |
| Extraction | Extract text, layout, tables, and model-supported fields | Preserve API/model version, source locations, partial result, and failure status |
| Processing | Normalize, cleanse, chunk, and keep source lineage | Deterministic identity/version and replay-safe transformation |
| Embedding | Create vectors for one approved model/version/dimension | Bounded batches, retry-after handling, quota telemetry, and generation identity |
| Search | Store text, metadata, vectors, and authorization filters | Keyless service identity where supported; access check on every retrieval |
| Orchestration | Retrieve evidence, construct bounded context, generate or abstain | Retrieved material is untrusted; only authorized evidence may enter prompts |
| Conversation | Keep identity-bound session context | Retention, expiry, encryption, deletion, and storage remain undecided |
| Operations | Correlate state, measure quality, reconcile, alert, and recover | Redact content; define ownership, SLOs, recovery, and cost thresholds |

## Trust Boundaries

1. User/client to Python service: authenticate caller and derive trusted principal claims; never trust a client-supplied group list.
2. Service to source/search/model services: use narrowly scoped identity and network policy; do not propagate user tokens as service credentials without explicit design.
3. Search to generation: authorization-filtered evidence only; preserve provenance and treat document instructions as hostile input.
4. Telemetry: record identifiers/status required for correlation, not raw content or secrets by default.

## Failure Ownership

The intake coordinator owns idempotency and source revision state. Each adapter owns its timeout, provider-specific throttling, retry-after interpretation, and error normalization. A durable run ledger owns recovery after ambiguous commit. A reconciliation worker compares source-of-truth revision and permission state with processed/search projections. The API boundary owns safe user-facing failure/abstention. Exact service-specific retry values are implementation decisions based on current limits and workload testing.

## Availability and Scale

The 1,000 concurrent / 50,000 total-user values are unverified planning inputs. They do not prove capacity for Azure AI Search, model throughput, extraction TPS, Databricks, or a host. Required load shape, corpus size, ingest rate, query rate, percentiles, budget, regional availability, and RTO/RPO are open. See [NFRs](../product/requirements.md) and [capacity risks](../project-management/risks.md).