# Architecture Overview

**Status**: Proposed reference architecture; not approved for implementation.

The candidate flow separates source of truth, processing, retrieval, generation, and operations. Candidate services are Azure Blob Storage, Azure AI Document Intelligence v4, Azure Databricks/PySpark with Unity Catalog, Azure OpenAI, Azure AI Search, and a Python service. Product, security, and workload decisions remain prerequisites to acceptance.

```mermaid
flowchart LR
  OP[Document operator] --> IN[Intake boundary]
  IN --> RAW[(Raw source candidate: Blob Storage)]
  RAW --> EXT[Extraction candidate: Document Intelligence]
  EXT --> PROC[Processing candidate: Databricks / PySpark]
  PROC --> DER[(Processed data candidate: ADLS Gen2 / Delta)]
  PROC --> EMB[Embedding deployment candidate: Azure OpenAI]
  EMB --> IDX[(Azure AI Search index)]
  U[Authenticated user] --> API[Python service candidate]
  API -->|identity + mandatory authorization| IDX
  IDX -->|authorized evidence + provenance| API
  API --> LLM[Chat deployment candidate]
  LLM --> API
  API --> U
  OPS[Monitoring / reconciliation] -. observes .-> IN
  OPS -. observes .-> PROC
  OPS -. observes .-> IDX
  OPS -. observes .-> API
```

The index is derived and rebuildable. Authorization must be applied before evidence reaches the model and before citations or snippets reach the caller. Events trigger work; durable source revision, idempotency state, and reconciliation determine the active result. See [system architecture](system-architecture.md), [data flow](data-flow.md), and [open questions](../project-management/open-questions.md).