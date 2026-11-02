# ADR-013: Networking and Private Connectivity

**Status**: Pending data residency and security architecture

## Context

Document and model calls may carry sensitive content. Project input does not state public/private exposure, corporate network integration, or region.

## Options

- Public endpoints with tightly scoped identity/firewall restrictions if approved.
- Private endpoints/VNet integration for selected services and host.
- Hybrid connectivity if approved client/source systems require it.

## Decision

No network topology accepted. Must first select region, host, exact service tiers, and data classification, then check feature-specific private-link support.

## Rationale

Search indexer private links and Databricks/storage networking have service/tier/runtime constraints; blanket private-network assumptions may make a candidate design invalid.

## Consequences

Requires DNS, egress, firewall, ingress, monitoring, administration, service identity, and connectivity tests per boundary.

## Dependencies

Data classification/residency, host choice, region, Databricks decision, Search tier, model deployment, corporate network policy.

## References

- [Azure compute decision guide](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree), accessed 2026-11-02.
- [Azure AI Search limits and private link constraints](https://learn.microsoft.com/en-us/azure/search/search-limits-quotas-capacity), accessed 2026-11-02.
- [Unity Catalog managed identity storage access](https://learn.microsoft.com/en-us/azure/databricks/connect/unity-catalog/cloud-storage/azure-managed-identities), accessed 2026-11-02.