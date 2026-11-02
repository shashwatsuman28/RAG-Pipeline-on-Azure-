# ADR-008: Hybrid Retrieval and Ranking

**Status**: Proposed; benchmark required

## Context

The project brief requests BM25 keyword + vector hybrid retrieval; semantic ranking is a candidate improvement.

## Options

- BM25 only.
- Vector only.
- Hybrid lexical + vector with Reciprocal Rank Fusion.
- Hybrid with optional semantic reranking.

## Decision

Use hybrid as the baseline evaluation candidate; do not accept semantic ranking as mandatory before quality, region, throughput, and cost evaluation.

## Rationale

Azure AI Search runs keyword and vector in parallel and fuses results using RRF. Semantic ranker reranks a limited top set and has separate availability and billing conditions.

## Consequences

Need query set, filter correctness, ranking metrics, `k`/candidate tuning, semantic configuration, latency, and cost evidence. Access filters must be applied consistently to hybrid branches.

## Dependencies

Search index, embeddings, ACL source, corpus/query labels, region, service tier, SLO/budget.

## References

- [Hybrid search overview](https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview), accessed 2026-11-02.
- [Semantic ranking overview](https://learn.microsoft.com/en-us/azure/search/semantic-search-overview), accessed 2026-11-02.