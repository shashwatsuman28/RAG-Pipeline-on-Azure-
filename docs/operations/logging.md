# Logging

**Status**: Requirements; schema and retention pending classification policy.

Logs should use structured, versioned event fields: timestamp, environment, component, operation, status, safe error category, retryability, source/run correlation IDs (pseudonymous where feasible), provider request ID, latency, and model/API/index version. Do not log secrets, bearer tokens, raw document text, retrieved chunks, or unrestricted user prompts by default.

Data owner and security owner must approve allowed identifiers, content redaction, retention, access, export, and deletion behavior. Log-based debugging must not bypass document authorization.