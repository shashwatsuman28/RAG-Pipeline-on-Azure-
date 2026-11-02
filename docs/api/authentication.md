# Authentication

**Status**: Microsoft Entra ID selected provisionally for user authentication; identity owner must confirm tenant, claims, protocol, app registration, and roles. This does not resolve service identity or document authorization.

Microsoft Entra ID is the user identity provider in the planning baseline. User authentication establishes identity; it does not by itself establish which documents can be read. The API must derive trusted caller claims from a validated token and must not accept client-supplied principal/group lists as authoritative.

Azure service calls should evaluate managed identity and least-privilege RBAC. Microsoft documents `DefaultAzureCredential` for local development and Azure-hosted identity chains. Document Intelligence v4 Entra auth requires a custom subdomain; verify resource configuration. Azure OpenAI v1 uses a token provider with supported operations. Search query keys are not a substitute for end-user document authorization.

Open: token validation/audience, groups/overage behavior, user lifecycle, app roles, administrator/operator roles, service identities, break-glass support, and authentication failure UX.