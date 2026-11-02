# User Workflows

**Status**: Proposed workflows for requirement review. Roles are scenario placeholders, not approved identity roles.

## Document Operator: Ingest and Maintain Content

1. Select an approved source and submit it through an approved ingestion boundary.
2. Receive acceptance, rejection, or a processing status with a safe reason and correlation reference.
3. Review extraction/processing outcomes and source provenance; correct or retry failures under the approved policy.
4. Update or request deletion of a source; observe synchronization state and any approved retention/legal-hold exception.

Open: source connectors, operator permissions, approval/quarantine process, and deletion authority.

## Knowledge Worker: Ask and Verify

1. Authenticate with the approved organization identity provider.
2. Ask a question in the approved client (client type pending).
3. Receive a grounded response with references to authorized sources, or a clear insufficient-evidence/dependency response.
4. Open a cited source location if the client and source support it.
5. Continue a conversation within identity-bound context and approved retention limits.

Open: group and document authorization rules, citation interaction, conversation persistence, accessibility/localization, and client scope.

## Failure and Recovery Paths

- Unsupported or malformed input is rejected/quarantined with actionable status.
- Partial extraction is visible as partial, never silently reported as complete.
- Search/model outage results in a safe error or retryable status, not an unsupported answer.
- Permission metadata missing, stale, or changed causes fail-closed behavior until reconciled.
- Retries and reprocessing preserve stable identity and avoid duplicate active records.