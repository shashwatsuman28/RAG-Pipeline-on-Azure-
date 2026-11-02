# Integration Testing

**Status**: Proposed test boundaries; service credentials and accounts are not configured.

Future integration suites should verify the supported SDK/API version combinations, identity scopes, long-running extraction polling, source version/ETag handling, Databricks/Unity Catalog storage authorization if selected, embedding dimensions, search index contract, hybrid query filters, and model deployment responses. External dependencies should be replaced with deterministic fakes for retry/idempotency unit tests and isolated test resources only when provisioning is explicitly approved.

Do not use production content or keys. Capture provider request IDs and safe error categories. A green local unit suite does not establish region availability, model quota, private networking, service capacity, or cloud behavior.