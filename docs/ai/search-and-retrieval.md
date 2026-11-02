# Search and Retrieval

**Status**: Azure AI Search is a candidate; tier, schema, filters, and ranking settings are pending.

Azure AI Search supports full-text BM25 and vector search in one hybrid request and merges ranked result sets with Reciprocal Rank Fusion. Vector schema requires a unique key, searchable content, vector field with `Collection(Edm.Single)`, matching dimensions, and a vector profile. Vector fields are not filterable; authorization metadata must use approved non-vector fields or a supported native permission feature. Semantic ranker is an optional text reranker with region, capacity, and billing constraints.

Proposed query flow: validate authenticated caller -> obtain trusted principal claims -> apply mandatory authorization policy -> run lexical and vector retrieval -> optionally rerank after benchmark -> return only authorized text/provenance to context construction. The general availability string filter is only a filtering mechanism; the application must authenticate and derive principal IDs. Native Entra ACL/RBAC, Purview, and SharePoint permission paths are preview in current docs and not presumed production-ready.

Measure Recall@k/nDCG and query latency separately, compare keyword/vector/hybrid, track filter correctness, and quantify semantic-ranker cost. See [ADR-007](../decisions/ADR-007-search-index.md), [ADR-008](../decisions/ADR-008-hybrid-retrieval.md), and [security model](../security/identity-and-access.md).