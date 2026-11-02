# Threat Model

**Status**: Initial qualitative STRIDE-style review; owners and acceptance thresholds pending.

| Threat | Trust boundary / impact | Required mitigation evidence |
|---|---|---|
| Unauthorized document retrieval | User -> API/Search; confidential content leakage | Trusted Entra identity; approved permission source; filter/token enforcement; denial tests across all retrieval paths |
| Prompt injection in documents | Search -> model; policy override, disclosure, unsafe tool action | Treat retrieved content as untrusted; no document-granted tools; adversarial corpus evaluation and output checks |
| Permission drift/stale index | Source ACL -> projection; access persists after revocation | Defined synchronization SLA, fail-closed policy, reconciliation and stale-permission tests |
| Forged source/event | Connector/event -> intake; poison or duplicate corpus | Verify source/topic, authenticated connector, revision/ETag, idempotency, accepted formats |
| Credential compromise | Workload -> Azure services; data exfiltration or alteration | Managed identity, least privilege, secret scanning/rotation exception controls, network limits, audit |
| Sensitive logs/prompts | Service -> observability/model; unintended disclosure | Data classification, minimization/redaction, access and retention controls |
| Deletion gap | Lifecycle coordinator -> derived stores/backups; retained content | End-to-end inventory, deletion reconciliation, legal-hold policy, evidence of completion |
| Dependency compromise or API drift | Build/runtime -> providers; supply-chain or incompatibility | Dependency pinning, support/lifecycle review, SBOM/scanning policy and upgrade tests |

This is not a completed security assessment or compliance claim. Security owner must confirm threat actors, risk ratings, controls, test thresholds, and incident response.