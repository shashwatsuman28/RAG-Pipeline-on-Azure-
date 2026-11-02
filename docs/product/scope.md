# Scope

## Candidate First-Release Scope

- Single enterprise organization, confirmed as the first-release tenant boundary.
- Ingestion and provenance for an owner-approved document corpus.
- Candidate initial inputs: PDF, Microsoft Word, tables, and structured documents, subject to precise format/size approval and service testing.
- Extraction, transformation, chunking, embedding, indexing, keyword/vector/hybrid retrieval, and grounded conversational responses.
- Incremental synchronization, deletion handling, failure recovery, monitoring, and evaluation.

## Pending Scope Decisions

- Actual source connectors and whether a client is a new web frontend, existing application, API-only consumer, or another experience.
- Document classification, whether data is synthetic/public/real, retention, legal holds, deletion, residency, and compliance.
- Identity/group mapping and the authoritative document permission system.
- Corpus size and document limits, 1,000 concurrent / 50,000 total user signal validity, throughput, latency, availability, recovery, region, and cost envelope.
- Production versus portfolio demonstration acceptance, deployment model, and target operating posture.

## Out of Scope for This Phase

Application implementation, API endpoint implementation, frontend, infrastructure as code, Azure resource creation, deployment, credentials, cloud estimates without inputs, and approval of any candidate service/model.

## Explicitly Not Assumed

Multi-tenancy, particular identity claims/groups, document-level ACL source, supported Office features beyond verified model capability, model dimensions, search tier, hosting platform, region, budget, compliance, or production performance.