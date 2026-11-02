# Embedding Strategy

**Status**: Candidate comparison only; no model or dimension is accepted.

Microsoft Learn lists `text-embedding-ada-002` at a fixed 1,536 dimensions and `text-embedding-3-large` up to 3,072 dimensions; text-embedding-3 models support a dimensions parameter. Azure AI Search vector fields must exactly match emitted vector dimensions, and changing embedding models requires re-embedding/index-generation migration. Availability, quota, pricing, and deployment category depend on region and date.

Compare at least the user-supplied candidates using the same representative approved corpus and query set. Record retrieval quality, supported languages, input limits, latency, throughput/quota, vector storage, indexing rebuild cost, inference cost, region/model lifecycle, and LangChain/client compatibility. Do not rank solely on published general benchmarks. A new model/dimension creates a separate generation; never mix embeddings from different spaces in one field.

See [ADR-006](../decisions/ADR-006-embedding-model.md), [research](../../specs/001-documentio-platform/research.md), and [test evaluation](../testing/rag-evaluation.md).