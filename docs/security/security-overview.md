# Security Overview

**Status**: Requirements baseline; detailed policy decisions pending security and data owners.

Documentio is a single-organization first-release proposal with a user authentication provider selected provisionally as Microsoft Entra ID. Document-level authorization remains mandatory, while its authority and synchronization are unresolved. Every query must fail closed if required authorization data is absent or stale. Authorization must cover all retrieved evidence, citations, caches, transcripts, exports, and logs.

Primary concerns include malicious documents and prompt injection, unauthorized retrieval/citation, identity confusion, permission drift, credential compromise, sensitive telemetry, service/network exposure, dependency supply chain, and incomplete deletion. Security requirements are in [spec.md](../../specs/001-documentio-platform/spec.md); threat cases are in [threat-model.md](threat-model.md).