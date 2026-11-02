# Monitoring

**Status**: Proposed signals; platform, alert thresholds, and owners pending.

Candidate signals: accepted/rejected source count; stage duration and error category; oldest backlog age; retry/dead-letter count; extraction partial rate; embedding tokens/throttles; index write failures and freshness lag; retrieval empty/filtered counts; authorization denials; answer abstentions/citation checks; model latency/errors/quota; conversation-store failures; and per-stage cost.

Use a correlation ID across intake, run, extraction, transformation, embedding, indexing, retrieval, and generation. Do not log raw document/query/answer content unless an approved classification and retention policy permits it. Alerts need actionable threshold, owner, severity, and runbook. No dashboards or alerts are configured.