# Identity and Access

**Status**: User auth provisional; document permission source pending.

### User identity

Microsoft Entra ID was selected during clarification for user authentication, subject to identity-owner confirmation of tenant, claims, app registration, token audience, and group behavior. The first release serves one enterprise organization. This does not establish app roles, administrator permissions, or service-to-service identity.

### Service identity

Evaluate managed identities for Azure-hosted workloads and the least-privilege service role for each storage, search, extraction, Databricks, and model operation. Local development uses a developer identity, not a production secret. Role assignments, custom subdomain requirements, and network restrictions must be verified for the selected services.

### Document authorization

The authority (source-system ACL inheritance vs Documentio-managed policy) remains a release-blocking decision. Azure AI Search security string filters are a GA application pattern, not authentication. Current native token-based ACL/RBAC/Purview options are preview. A production decision must approve source of truth, claim/group resolution, index metadata, update/deletion synchronization, maximum staleness, fail-closed behavior, and test coverage.