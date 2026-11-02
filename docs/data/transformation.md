# Data Transformation

**Status**: Proposed; no transformation engine selected.

Transformation converts extraction responses into normalized, versioned elements while preserving source revision, locations, and extraction confidence. Cleansing must not erase source evidence; normalization should retain raw and normalized representations where the approved policy permits. Tables need a representation that preserves headers, cell indices, spans, and page linkage. Unsupported fields and partial extraction must remain explicit.

Azure Databricks/PySpark is a candidate for distributed transformations. If selected, use current Unity Catalog storage credentials and external locations with managed identity rather than defaulting to legacy DBFS mounts. For a portfolio-scale corpus, assess operational and cost overhead against simpler Python processing before approving Databricks.

See [proposed data model](../../specs/001-documentio-platform/data-model.md), [Databricks ADR](../decisions/ADR-003-databricks-processing.md), and [Unity Catalog ADR](../decisions/ADR-004-unity-catalog-access.md).