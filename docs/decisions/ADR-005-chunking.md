# ADR-005: Chunk Identity and Chunking Strategy

**Status**: Pending corpus and evaluation

## Context

FR-003/DR-001/DR-002 require retrieval units with source location and stable identity across retries/reprocessing.

## Options

- Structure-aware sections/paragraphs and table-aware units.
- Fixed token-window chunks with overlap.
- Hybrid structure-aware splitting with bounded windows for oversized sections.

## Decision

No algorithm, chunk size, overlap, or table serialization is selected. Evaluate candidates with an approved corpus.

## Rationale

Document structure and table context affect retrieval and citations; no user corpus, languages, query set, model token limits, or quality measurements are available.

## Consequences

Chunk identity must include source revision and chunker version. Changes require new generation, index coexistence or rebuild, and evaluation. Citation mapping needs source offsets/page locations.

## Dependencies

Corpus and query set, extraction quality, embedding model, context budget, quality and cost thresholds.

## References

- [Document Intelligence layout analysis](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/prebuilt/layout?view=doc-intel-4.0.0), accessed 2026-11-02.
- [Azure AI Search vector index](https://learn.microsoft.com/en-us/azure/search/vector-search-how-to-create-index), accessed 2026-11-02.