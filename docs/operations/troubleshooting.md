# Troubleshooting

**Status**: Diagnostic guide for future implementation; no running system exists.

| Symptom | Evidence to collect safely | Initial diagnostic boundary |
|---|---|---|
| Extraction rejected/partial | Run ID, model/API version, media type, page/size class, safe error code | Compare to current service format/limit matrix; inspect source only with authorization |
| Repeated 429/throttle | Provider, UTC time, request ID, retry-after, request rate | Reduce/constrain concurrency; verify quota and deployment capacity |
| Dimension/index schema error | Embedding generation ID, dimension, index schema version | Confirm vector output equals index field dimensions; do not mix generations |
| Search has no evidence | Query correlation ID, filters applied, index freshness and result counts | Verify authorization filter and indexing state without exposing restricted snippets |
| Unexpected citation/answer | Prompt/model version, authorized result IDs, evaluation case | Trace result-to-source revision and citation validation; treat source text as untrusted |
| Stale/deleted document remains | Source revision/deletion state, event checkpoint, active search IDs | Run authorized reconciliation; inspect legal hold/retention exceptions |

Exact commands, dashboards, endpoints, and escalation contacts are pending implementation and operations ownership.