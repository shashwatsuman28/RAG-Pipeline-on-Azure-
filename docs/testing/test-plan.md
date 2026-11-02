# Test Plan

**Status**: Planned evidence; thresholds and datasets pending approval.

| Test group | Cases | Required report |
|---|---|---|
| Ingestion/extraction | Supported fixtures, corrupt/empty/encrypted/unsupported/over-limit, partial output | Format-feature matrix, provenance coverage, error classification |
| Transformation/chunking | Same revision repeat, new revision, table/heading boundaries, extraction partial state | Deterministic identity, lineage, chunk quality |
| Embedding/index | Batch limit, 429/retry-after, timeout after commit, dimension/schema mismatch, partial batch | Generation/version identity, final index state, retry count |
| Authorization | Allowed/denied users/groups, missing/stale permissions, permission change, cache/citation | Unauthorized disclosure count (required zero in fixtures) |
| RAG | Known-answer, conflicting evidence, no evidence, injection document, citations | Retrieval and answer metrics separately |
| Operations | Source update/delete, missed event, dead letter, service outage, restore | Convergence, measured RTO/RPO, SLO result |
| Capacity/cost | Owner-approved user/corpus/ingest/query/load shape | p50/p95/p99, throughput, throttling, failures, resource and cost inputs |

Owners: product for user success/quality thresholds, data/security for corpus and authorization, operations for service objectives and recovery, finance/project owner for spend. Numeric targets and named owners are pending. No Azure tests have been executed.