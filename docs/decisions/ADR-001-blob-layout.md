# ADR-001: Raw and Processed Storage Layout

**Status**: Proposed

## Context

FR-001/DR-001/DR-003 require a recoverable original, stable revision identity, derived-data lineage, and deletion handling. The brief names Blob Storage for raw files and Blob/Delta Lake for processed chunks.

## Options

- Blob Storage for raw and processed artifacts.
- Blob Storage raw plus ADLS Gen2/Delta Lake processed data.
- Other source/lakehouse arrangement selected after corpus and workload review.

## Decision

No layout accepted. Blob Storage is the raw-source candidate; ADLS Gen2/Delta is a conditional processed-data candidate if Databricks/Unity Catalog is approved.

## Rationale

Keep original source and derived/rebuildable projections conceptually separate, with explicit revision and lifecycle ownership.

## Consequences

Need stable IDs, version/checksum semantics, access policy, storage tiers, lifecycle, backups, deletion reconciliation, and cost estimates. ADLS Gen2 hierarchical namespace and UC access requirements constrain the candidate.

## Dependencies

Corpus, classification, residency, retention/legal hold, region, Databricks decision, and budget.

## References

- [Blob authorization with Microsoft Entra ID](https://learn.microsoft.com/en-us/azure/storage/blobs/authorize-access-azure-active-directory), accessed 2026-11-02.
- [Unity Catalog external locations](https://learn.microsoft.com/en-us/azure/databricks/connect/unity-catalog/cloud-storage/external-locations-adls), accessed 2026-11-02.