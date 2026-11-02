# ADR-002: Document Extraction Approach

**Status**: Proposed

## Context

FR-002 asks for text, tables, key-value pairs, layout, and source references across PDF, Word, tables, and structured documents.

## Options

- Azure Document Intelligence v4 Layout plus selected prebuilt models.
- Other Azure extraction capability/model, selected after fixture comparison.
- Local/open-source parser for some formats combined with a cloud extraction service.

## Decision

Evaluate Azure Document Intelligence v4 (`2024-11-30` GA) first; do not accept it as a universal extractor until per-format tests and limits are reviewed.

## Rationale

Official docs identify v4 as current and describe Python SDK support. Layout supports text/structure and selected tables, but model/file support varies; Office embedded images and XLSX table extraction have limitations.

## Consequences

Need model routing/format matrix, partial status, page/element provenance, page/size quotas, quota and page-cost estimates. Key-value extraction must use supported model features, not an assumed general layout capability.

## Dependencies

Authorized corpus, file types/languages/limits, region, resource type/authentication, budget, extraction quality targets.

## References

- [Document Intelligence overview](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/overview?view=doc-intel-4.0.0), accessed 2026-11-02.
- [Layout analysis](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/prebuilt/layout?view=doc-intel-4.0.0), accessed 2026-11-02.
- [Service limits](https://learn.microsoft.com/en-us/azure/ai-services/document-intelligence/service-limits?view=doc-intel-4.0.0), accessed 2026-11-02.