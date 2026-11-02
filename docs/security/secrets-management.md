# Secrets Management

**Status**: Required controls; actual runtime store and pipeline configuration are pending.

Prefer Microsoft Entra ID and managed identity where supported; do not embed keys, connection strings, tokens, or private endpoints in source, tasks, examples, screenshots, telemetry, or documentation. If a static secret is unavoidable, document the exception in an ADR and define vault storage, minimal readers, rotation, expiry, incident response, and local development handling.

Future CI must scan committed content and redact secret-bearing outputs. Azure model API keys are not assumed necessary when the approved v1/SDK Entra flow supports the required calls. Never print or request real credentials in Spec Kit artifacts.