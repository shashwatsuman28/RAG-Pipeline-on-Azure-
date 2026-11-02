# Coding Standards

**Status**: Proposed standards; language tooling awaits project structure approval.

- Keep service adapters behind narrow interfaces and preserve provider/model/API versions in results.
- Use explicit typed contracts for source identity, revisions, extracted elements, chunks, permissions, and failures.
- Make ingestion and index mutation idempotent; avoid broad retries without commit reconciliation.
- Fail closed when authorization context or required permission metadata is unavailable.
- Treat document text as untrusted; never allow it to override system policy or permissions.
- Redact content and secrets from logs; use correlation IDs and structured stage outcomes.
- Keep tests deterministic and separate retrieval relevance from generation quality.
- Pin dependencies and document official lifecycle/support evidence for external APIs.

Formatter, linter, typing strictness, test framework, code layout, and branch/review protections require owner approval; no project tooling is configured yet.