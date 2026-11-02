# ADR-012: Authentication and Document Authorization

**Status**: Pending security/data-owner decision; production blocker

## Context

First release is single-organization. Microsoft Entra ID was selected provisionally for user authentication. Document-level authorization is required, but the permission source is undecided.

## Options

- Source-system permission inheritance and synchronization.
- Documentio-managed ACL/metadata and administration.
- Azure AI Search string security filters with trusted application-derived identities (GA pattern; filter itself does not authenticate).
- Azure AI Search native token-based ACL/RBAC, Purview, or SharePoint permission ingestion (preview as documented on access date).

## Decision

No document authorization authority or Search feature accepted. Fail closed if policy/permission data is missing or stale. Do not rely on preview authorization as production-ready without explicit exception and lifecycle review.

## Rationale

Incorrect permission handling can expose source text through results, citations, prompts, answers, caches, or conversation history. The data source and existing permissions were not supplied.

## Consequences

Must define principal claims, group resolution, per-chunk metadata projection, synchronization latency, revocation behavior, caching, deletion, test cases, and audit evidence.

## Dependencies

Identity-owner confirmation, source inventory, ACL policy, data classification, Search GA/preview decision, region and network.

## References

- [Azure AI Search document-level access](https://learn.microsoft.com/en-us/azure/search/search-document-level-access-overview), accessed 2026-11-02.
- [Azure AI Search security filter pattern](https://learn.microsoft.com/en-us/azure/search/search-security-trimming-for-azure-search), accessed 2026-11-02.