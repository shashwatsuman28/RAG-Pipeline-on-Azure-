# Integration Architecture

**Status**: Candidate integrations researched; only Python and Azure are stated project inputs. Integration selection remains subject to ADRs and runtime verification.

| Candidate integration | Boundary | Verified consideration | Pending |
|---|---|---|---|
| Azure Blob Storage | Raw source store | Python package `azure-storage-blob`; current official page requires Python 3.10+; Microsoft Entra ID/RBAC and Azure Identity are supported | Account type, hierarchical namespace, event/change-feed mode, layout, lifecycle, access authority |
| Azure AI Document Intelligence | Extraction | v4 `2024-11-30` GA; Python SDK `azure-ai-documentintelligence` 1.0.0; Entra token credential supported with custom subdomain | Format matrix, model types, limits, region, quota, costs, representative extraction quality |
| Azure Databricks / Unity Catalog | Distributed processing | Managed identity through Access Connector + UC storage credentials/external locations; Auto Loader supports incremental discovery | Whether needed at portfolio scale, account/plan, region, networking, data layout and ownership |
| Azure OpenAI in Microsoft Foundry Models | Embedding and generation | v1 GA supports OpenAI Python client and Entra token provider for supported API operations | Exact model, region, deployment type, API feature compatibility, quota, quality and price |
| Azure AI Search | Keyword/vector/hybrid retrieval | Python package `azure-search-documents`; supports Entra RBAC, hybrid BM25 + vector and RRF; schema dimensions must match vectors | Tier, schema, filters, ACL authority, semantic ranker, private endpoints, capacity and cost |
| LangChain | Python orchestration abstraction | Current docs recommend `langchain-openai` for Azure OpenAI v1; current memory guidance supports persisted checkpointers | Azure Search vector store integration could not be verified due docs endpoint 404; confirm package/API at implementation time |

Avoid retired SDK/API names and DBFS mounts. The Azure Search native ACL/Purview options are preview in current docs; do not accept those for production without explicit review. See [research](../../specs/001-documentio-platform/research.md).