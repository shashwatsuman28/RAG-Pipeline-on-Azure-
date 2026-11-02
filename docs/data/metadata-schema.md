# Metadata Schema

**Status**: Proposed conceptual fields; not an approved physical schema.

| Field group | Candidate metadata | Governance status |
|---|---|---|
| Identity | document ID, source revision, chunk ID, processing run, pipeline/chunk version | Required concept; exact identity source pending |
| Provenance | source reference, page/sheet/slide, element/range, extraction model/API, observed timestamp | Preserve where source/model provides it |
| Content | media type, original display name, chunk text, table structure, extraction state | Sensitivity and searchable/displayable fields require approval |
| Embedding | provider/model/deployment version, dimensions, content digest, embedding generation | Model and dimensions pending ADR-006 |
| Authorization | permission authority, policy version, allowed principal/group/scope representation, synchronized time | Sensitive; authority and freshness pending ADR-012 |
| Lifecycle | active/superseded/deletion-requested/deleted/held, retention expiry, legal hold reference | Pending data owner and legal policy |
| Operations | state, correlation ID, retry count, error category, stage timestamps | Minimize and redact content/identifiers per policy |

Azure AI Search requires a unique string key and vector dimensions matching the actual model output. Vector fields cannot be filterable; authorization filters need separate filterable non-vector fields or supported token-based permission features. Physical index schema and all retrievable fields remain pending. See [data model](../../specs/001-documentio-platform/data-model.md).