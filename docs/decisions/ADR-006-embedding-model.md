# ADR-006: Embedding Model and Dimensions

**Status**: Pending benchmark, region, and budget

## Context

INT-004/FR-004 require vector embeddings; the brief lists `text-embedding-3-large` and `text-embedding-ada-002`.

## Options

- text-embedding-3-large with approved dimension.
- text-embedding-ada-002 at 1,536 dimensions, subject to current lifecycle/availability verification.
- Another currently supported GA deployment selected through benchmark.

## Decision

No model or dimension accepted. Benchmark the named candidates plus eligible alternatives on an approved corpus and region.

## Rationale

The model catalog documents different dimensions, input behavior, availability, and cost. Search schema dimensions must match vector output; changing embedding space requires re-embedding.

## Consequences

Model change requires embedding/index generation migration. Storage, recall, latency, quota, model lifecycle and reprocessing costs need measurement.

## Dependencies

Region, subscription, model deployment availability/quota, language/corpus, query set, retrieval metrics, budget.

## References

- [Foundry model catalog](https://learn.microsoft.com/en-us/azure/ai-foundry/openai/concepts/models), accessed 2026-11-02.
- [Generate embeddings](https://learn.microsoft.com/en-us/azure/ai-foundry/openai/how-to/embeddings), accessed 2026-11-02.