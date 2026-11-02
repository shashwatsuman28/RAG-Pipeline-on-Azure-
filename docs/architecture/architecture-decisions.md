# Architecture Decisions

This index links decision records. **Proposed** means researched but not approved; **Pending** means owner input is required; **Accepted** is reserved for explicit approval with evidence.

| ADR | Topic | Current status |
|---|---|---|
| [ADR-001](../decisions/ADR-001-blob-layout.md) | Raw and processed storage layout | Proposed |
| [ADR-002](../decisions/ADR-002-document-extraction.md) | Document extraction approach | Proposed |
| [ADR-003](../decisions/ADR-003-databricks-processing.md) | Databricks processing strategy | Proposed |
| [ADR-004](../decisions/ADR-004-unity-catalog-access.md) | Unity Catalog and storage access | Proposed |
| [ADR-005](../decisions/ADR-005-chunking.md) | Chunk identity and chunking strategy | Pending corpus/evaluation |
| [ADR-006](../decisions/ADR-006-embedding-model.md) | Embedding model and dimensions | Pending benchmark/region/budget |
| [ADR-007](../decisions/ADR-007-search-index.md) | Search schema and index generation | Pending model/ACL decisions |
| [ADR-008](../decisions/ADR-008-hybrid-retrieval.md) | Hybrid retrieval and ranking | Proposed; benchmark required |
| [ADR-009](../decisions/ADR-009-conversation-state.md) | Conversation history and persistence | Pending policy |
| [ADR-010](../decisions/ADR-010-langchain.md) | LangChain Azure integration | Pending current Search package verification |
| [ADR-011](../decisions/ADR-011-hosting-platform.md) | App Service vs AKS | Pending workload/team/network input |
| [ADR-012](../decisions/ADR-012-document-authorization.md) | Authentication and document authorization | Pending security/data-owner decision |
| [ADR-013](../decisions/ADR-013-networking.md) | Networking and private connectivity | Pending region/security topology |
| [ADR-014](../decisions/ADR-014-monitoring.md) | Monitoring, logs, and evaluation telemetry | Proposed; policy/owner targets pending |

The ADR set is not approval to provision resources. Each record cites authoritative sources and identifies unresolved dependencies.