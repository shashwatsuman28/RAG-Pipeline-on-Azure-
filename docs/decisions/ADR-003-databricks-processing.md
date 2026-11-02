# ADR-003: Databricks Processing Strategy

**Status**: Proposed

## Context

INT-003 proposes Databricks/PySpark for cleansing, transformation, and chunking. Portfolio scope and actual corpus volume are unknown.

## Options

- Python processing in the application/service boundary.
- Azure Databricks with PySpark, incremental ingestion, and governed tables.
- Hybrid: simple service for orchestration and Databricks only for demonstrated batch scale.

## Decision

Do not select Databricks until the volume/velocity and operational need justify it. If selected, use current Unity Catalog governance and assess Lakeflow pipelines/Auto Loader.

## Rationale

Distributed processing can address scale but adds account/plan, runtime, pipeline, data access, and operational cost. A portfolio workload may not justify it.

## Consequences

Requires workload evidence, team ownership, checkpointing and out-of-order semantics, access model, and a documented path for incremental/backfill/reprocessing.

## Dependencies

Corpus size/rate, budget, Databricks plan/region, Unity Catalog availability, network and identity design.

## References

- [Auto Loader](https://learn.microsoft.com/en-us/azure/databricks/ingestion/cloud-object-storage/auto-loader/), accessed 2026-11-02.
- [Lakeflow pipelines](https://learn.microsoft.com/en-us/azure/databricks/ldp/), accessed 2026-11-02.