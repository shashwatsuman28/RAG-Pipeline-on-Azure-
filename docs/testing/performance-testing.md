# Performance Testing

**Status**: Design required; no target or benchmark exists.

The initial planning signal is 1,000 concurrent users and 50,000 total users; it is unverified and is not an SLO. The plan must additionally define corpus size/file mix, ingest arrival rate, query rate, conversation distribution, embedding/model token volume, read/write mix, region, cold/warm state, and test duration.

Measure p50/p95/p99 latency for upload acceptance, extraction, indexing freshness, retrieval, generation, and end-to-end response separately. Record throughput, error and throttle rate, queue/backlog age, Search units/vector size, model quota consumption, Databricks compute, and cost. Set pass/fail targets only after owner approval. Do not select App Service/AKS capacity from concurrent user count alone.