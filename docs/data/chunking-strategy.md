# Chunking Strategy

**Status**: Pending representative corpus and retrieval evaluation; no chunk size or algorithm is selected.

The strategy must preserve section/table context and stable source location while generating chunks that fit the selected embedding and prompt constraints. Candidate approaches include structure-aware splits using headings/paragraphs, bounded token windows, overlap, and table-specific row/group serialization. These are evaluation candidates, not decisions.

Stable chunk identity should include source document ID, source revision, chunking version, and a deterministic element/range key. A repeat run for unchanged content and version should reproduce IDs. Any chunking-version change generates a new chunk generation and index reconciliation; old records are retired only after the new generation is verified.

Evaluate retrieval Recall@k/nDCG, context redundancy, table question performance, citation location quality, token/cost impact, and update stability on an owner-approved corpus. See [ADR-005](../decisions/ADR-005-chunking.md).