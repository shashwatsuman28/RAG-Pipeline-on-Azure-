# Environment Strategy

**Status**: Proposed requirement; environment count and isolation are pending.

Separate local development, non-production validation, and production identities/data if production scope is approved. Use only synthetic or explicitly authorized data outside approved production controls. Environment boundaries must specify subscription/tenant, region, resource groups, model/search deployments, data stores, identity/RBAC, network, logging, secrets, quotas, cost attribution, and deletion/teardown.

No environment variables, secret names, endpoint values, or cloud resource names are finalized. Local identity must not grant implicit production data access. Portfolio demonstration deployment is not assumed to require Azure provisioning.