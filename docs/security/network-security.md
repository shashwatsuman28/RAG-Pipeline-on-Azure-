# Network Security

**Status**: Pending region, deployment, and security decisions.

The design must enumerate inbound clients, outbound Azure dependencies, DNS, egress, administration paths, and private endpoint support by service/tier. App Service and AKS networking features vary by tier/mode. Azure AI Search private indexer connections have tier/feature constraints; Databricks storage network access varies by workspace compute and storage firewall mode. Do not assume a universal private-network topology.

Before a network decision, approve region and data residency, ingress exposure, private endpoints, VNet integration/injection, DNS forwarding, firewall rules, trusted service exceptions, outbound allowlist, monitoring, and break-glass access. Validate service-specific limitations against current official docs; no network configuration is selected here.