# Error Handling

**Status**: Required behavior proposed; payload/status codes await API design.

Normalize errors into validation/policy rejection, unsupported/partial extraction, transient throttling, timeout with unknown commit outcome, dependency unavailable, authorization denied, stale/reconciliation required, and terminal internal failure. User-facing responses must not reveal document existence or contents to unauthorized users.

Retries must be bounded and provider-aware, honor retry-after where supplied, use exponential backoff with jitter where appropriate, and never retry non-idempotent work without checking durable state. An accepted response must not imply successful indexing. Expose operation status/correlation ID through a future approved contract. Logs retain safe error category and provider correlation reference, not credentials or document text.