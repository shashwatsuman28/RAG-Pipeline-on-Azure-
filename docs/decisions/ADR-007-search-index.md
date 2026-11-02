# ADR-007: Azure AI Search Schema and Index Design

**Status**: Pending embedding, authorization, and workload decisions

## Context

FR-004 requires searchable text, vectors, document/chunk IDs, metadata, keyword/vector retrieval, and authorization.

## Options

- One index with text, vector, provenance, lifecycle, and filterable authorization metadata.
- Separate indexes/generations during embedding or schema migration.
- Alternative search store only if Azure AI Search fails a reviewed requirement.

## Decision

Azure AI Search is a candidate; no physical schema, tier, vector profile, key, or index strategy is accepted.

## Rationale

Azure AI Search supports hybrid retrieval and vector fields, but dimension, filterability, vector capacity, tier, region, and authorization pattern constrain schema.

## Consequences

Need deterministic keys, versioned schema, reindex/rollback strategy, retrieval-safe fields, permission metadata propagation to every chunk, quota/cost test, and deletion contract.

## Dependencies

Embedding model/dimensions, ACL authority, workload, region, data classification, private networking and semantic-ranker decision.

## References

- [Create a vector index](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-create-index), accessed 2026-11-02.
- [Document-level access control](https://learn.microsoft.com/en-us/azure/search/search-document-level-access-overview), accessed 2026-11-02.
- [Search service limits](https://learn.microsoft.com/en-us/azure/search/search-limits-quotas-capacity), accessed 2026-11-02.