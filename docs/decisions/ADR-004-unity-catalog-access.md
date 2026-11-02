# ADR-004: Unity Catalog and Storage Access

**Status**: Proposed, conditional on Databricks selection

## Context

If Azure Databricks processes documents, it needs governed access to source/processed storage with no undocumented DBFS mount assumption.

## Options

- Unity Catalog Access Connector and managed identity via storage credential/external location.
- Service principal credential, only with documented exception.
- No Databricks access because processing remains in the Python service.

## Decision

If Databricks is selected, evaluate Unity Catalog external locations with Access Connector managed identity; no DBFS mount is proposed.

## Rationale

Current Microsoft Learn guidance documents managed identity support and Unity Catalog external locations for ADLS Gen2. Storage needs hierarchical namespace and network configuration must be reviewed.

## Consequences

Requires RBAC and UC privileges, workspace/metastore bindings, region alignment, storage firewall and file-event permissions. Avoiding secrets does not remove network or governance setup.

## Dependencies

Databricks selection, plan, region, storage account type, network policy, access scope, data governance.

## References

- [Managed identities in Unity Catalog](https://learn.microsoft.com/en-us/azure/databricks/connect/unity-catalog/cloud-storage/azure-managed-identities), accessed 2026-11-02.
- [ADLS Gen2 external locations](https://learn.microsoft.com/en-us/azure/databricks/connect/unity-catalog/cloud-storage/external-locations-adls), accessed 2026-11-02.