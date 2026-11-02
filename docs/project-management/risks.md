# Risks

**Status**: Initial qualitative register; likelihood/impact scoring and owners require review.

| ID | Risk | Impact | Mitigation / evidence | Owner |
|---|---|---|---|---|
| R-001 | Permission source remains undecided | Unauthorized disclosure or overblocking | Block production design; approve authority, synchronization, fail-closed behavior; test all retrieval surfaces | Security/data, TBD |
| R-002 | Azure AI Search native ACL/Purview options are preview | Production reliance on unsupported lifecycle/SLA | Prefer reviewed GA security-filter pattern if compatible; do not select preview without exception/GA review | Architecture/security, TBD |
| R-003 | v4 extraction output does not uniformly cover desired key-values/tables/Office media | Missing or malformed evidence | Build fixture matrix; choose model per format; classify partial/unsupported and route appropriately | Data owner, TBD |
| R-004 | User scale signal mistaken for SLO/capacity proof | Under/over-provisioning and unplanned cost | Validate workload dimensions and load test; keep host/tier unselected | Product/operations, TBD |
| R-005 | Model availability/quota/retirement differs by region/deployment | Launch blocker or forced migration | Recheck current catalog/region/quota; pin lifecycle policy and maintain re-embedding plan | AI/platform, TBD |
| R-006 | LangChain Azure Search integration path is unverified | Deprecated or incompatible dependency | Validate current official docs/release; isolate behind adapter; direct SDK is a fallback to review | Architecture owner, TBD |
| R-007 | Duplicate/out-of-order events or ambiguous commits corrupt active index state | Duplicate/stale content or loss | Stable revision/idempotency keys, durable run ledger, reconciliation and fault-injection tests | Data engineering, TBD |
| R-008 | Deletion does not reach vectors, caches, conversation, logs, backups | Retention/privacy breach | Inventory derived copies; define deletion window/holds; audit end-to-end purge | Data/security, TBD |
| R-009 | Prompt injection in documents changes model behavior | Unsupported or unsafe answer | Treat retrieved content as untrusted; no document-driven tools; adversarial eval and citations | AI/security, TBD |
| R-010 | Portfolio status interpreted as permission to use actual enterprise content | Exposure or policy breach | Require explicit dataset approval/classification; synthetic corpus default until approved | Project/data owner, TBD |
| R-011 | Region/private networking constraints invalidate candidate service combination | Architecture rework | Resolve jurisdiction and network before ADR acceptance; verify each service/tier path | Security/platform, TBD |
| R-012 | No cost ceiling or budget inputs | Unexpected spend | No provisioning in this phase; cost model and alerts require approved usage/region before deployment | Project owner, TBD |
| R-013 | Conversation retention/access changes not designed | Cross-user leakage or deletion inconsistency | Bind state to identity; define expiry/revocation/deletion; test isolation | Product/security, TBD |
| R-014 | Similar but distinct content identity/revision models cause stale citation | User cannot verify answer source | Define connector IDs, ETag/content digest semantics and versioned citations before indexing | Data owner, TBD |

No risk has been accepted or quantitatively scored; revisit after owner decisions and before implementation approval.