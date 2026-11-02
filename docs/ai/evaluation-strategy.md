# Evaluation Strategy

**Status**: Evaluation dimensions defined; datasets and thresholds pending owner approval.

| Dimension | Example evidence | Must remain distinct from |
|---|---|---|
| Extraction | Field/element completeness, location accuracy, partial/error classification by fixture | Retrieval and answer quality |
| Retrieval | Recall@k, precision@k, nDCG, authorized-source rate, stale-result rate | Generation correctness |
| Grounded generation | Claim support, citation precision/recall, abstention correctness, unsupported-claim rate | Retrieval relevance |
| Authorization | Unauthorized result/citation/context/answer influence count; expected zero for test fixtures | General answer quality |
| Robustness | Duplicate/retry convergence, throttling recovery, stale ACL, prompt injection, partial failure | Availability target |
| Operations | Throughput, p50/p95/p99, error/throttle rate, backlog, RTO/RPO, measured cost | Research-only capability claims |

Every evaluation run records dataset/version, model/deployment and API version, embedding dimensions, index settings, region, sample size, prompt version, evaluator method, and date. A result is “researched” unless executed against an authorized runtime and fixture. Product/security owners approve gates before implementation exit criteria.