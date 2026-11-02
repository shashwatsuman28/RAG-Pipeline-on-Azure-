# Requirement Traceability Matrix

**Status**: Proposed architecture mapping. Task IDs refer to unchecked future work in [tasks.md](../../specs/001-documentio-platform/tasks.md); components are proposed and do not imply implementation.

| ID | Proposed component(s) | Future task(s) | Acceptance evidence |
|---|---|---|---|
| FR-001 | Intake coordinator, source store, processing-run ledger | T016, T022, T026 | Ingestion contract and lineage tests |
| FR-002 | Document Intelligence adapter, extraction normalizer | T019-T021 | Format-feature fixture matrix |
| FR-003 | Transformation and chunking | T023-T024 | Provenance and deterministic chunk tests |
| FR-004 | Embedding adapter, Search index, retriever | T027-T031 | Retrieval benchmark |
| FR-005 | Context builder, answer service, citation validator | T033-T036 | Grounding/citation evaluation |
| FR-006 | Identity resolver, conversation store | T014, T035, T041 | Principal-isolation tests |
| FR-007 | Revision reconciler, lifecycle synchronizer, Search writer | T025, T040 | Update/deletion reconciliation |
| FR-008 | Run ledger, telemetry, recovery and operator monitoring | T022, T044-T045, T048 | Injected-failure and telemetry review |
| FR-009 | API contract and authenticated API boundary | T037-T038 | Reviewed versioned contract and API tests |
| FR-010 | Product/client boundary; optional frontend | T011, T039 | Product-approved client scope; T039 conditional |
| NFR-001 | Capacity test harness and service boundaries | T009, T051 | Approved percentile/load report |
| NFR-002 | Host, backup/restore, recovery operations | T009, T046, T049, T051 | Measured availability/RTO/RPO evidence |
| NFR-003 | Intake, processing, Search, model and host capacity | T009, T051 | Approved workload and capacity results |
| NFR-004 | Run ledger, idempotency, reconciliation and recovery | T022, T025, T045 | Retry/ambiguous-commit tests |
| NFR-005 | ADR/research process, dependency and release gates | T010, T027, T047 | Dated regional/API/quota/lifecycle record |
| NFR-006 | Correlation and redacted telemetry | T044, T048 | Synthetic end-to-end trace and redaction review |
| NFR-007 | Cost attribution and budget guardrails | T009, T050 | Dated owner-approved estimate/limits |
| SEC-001 | Entra user authentication and API boundary | T014, T038, T041 | Identity matrix and negative tests |
| SEC-002 | Permission resolver, Search filter/token policy, citations | T014, T030, T041 | Zero unauthorized evidence in test cases |
| SEC-003 | Context builder, prompt boundary, answer service | T033-T036, T042 | Prompt-injection and unsupported-answer evaluation |
| SEC-004 | Data classification and lifecycle controls | T013, T043 | Approved protection matrix and lifecycle evidence |
| SEC-005 | Managed identity, secret handling, telemetry redaction | T017, T028, T044, T047 | Secret/log scan and approved exception ADRs |
| SEC-006 | Network architecture and selected host/service paths | T010, T046 | Approved allow/deny and connectivity tests |
| DR-001 | Source identity/revision, chunks, embedding/index generations | T015, T024, T029 | Repeat/revision lineage tests |
| DR-002 | Extraction provenance and chunk location mapping | T021, T024 | Source-to-element/chunk trace |
| DR-003 | Retention, deletion, conversation and backup lifecycle | T013, T035, T043, T049 | Approved purge/hold/restore evidence |
| DR-004 | Permission metadata and Search projection | T014, T029, T041 | Field inventory and access isolation |
| DR-005 | Idempotency ledger and source reconciliation | T015, T022, T025-T026 | Duplicate/concurrent/out-of-order tests |
| INT-001 | Blob source store and processed-data boundary | T017-T018 | Storage ADR and identity/lifecycle validation |
| INT-002 | Document Intelligence extraction adapter | T019-T021 | v4 compatibility and fixture matrix |
| INT-003 | Approved Python/Databricks processing runner | T023-T024 | Processing strategy ADR and replay test |
| INT-004 | Embedding and chat deployment adapters | T027-T028, T034 | Model/region/quota/quality benchmark |
| INT-005 | Azure AI Search schema, writer, and retriever | T029-T031 | Schema, filter, hybrid and capacity test |
| INT-006 | LangChain adapter boundary | T032-T034 | Current package/API verification and compatibility test |
| INT-007 | Hosting and network decision | T010, T046-T047 | App Service/AKS ADR with workload evidence |
| BR-001 | Single-organization scope boundary | T011, T014 | Product/security review confirms no cross-organization scope is implied |
| BR-002 | Intake policy and authorization context | T014, T016 | Denied/missing policy context cannot activate a source |
| BR-003 | Active revision only after validated pipeline completion | T022, T029, T040 | Partial-failure test preserves prior active state or stays unavailable |
| BR-004 | Authorized evidence only at all retrieval/output boundaries | T014, T030, T041 | Negative-access tests across result, context, citations, and answer |
| BR-005 | Abstain on insufficient, conflicting, or stale evidence | T034, T036 | Reviewed no-answer/conflict dataset produces approved safe response |
| BR-006 | Update/deletion follows approved lifecycle policy | T040, T043 | Reconciliation reports in-scope residuals and approved exceptions |
| BR-007 | No implementation/provisioning without explicit approval | T001, T009 | Owner approval recorded before any implementation or cloud action |
| SC-001 | Extraction adapter and format fixture harness | T019-T021 | 100% fixture outcome/provenance report |
| SC-002 | Retriever and answer evaluation harness | T030-T036 | Per-query retrieval, grounding, citation report |
| SC-003 | Authorization resolver and all retrieval/output paths | T041 | Negative access test report; expected zero leakage |
| SC-004 | Idempotency ledger and ingestion contract | T022, T026 | One active representation per revision |
| SC-005 | Lifecycle synchronizer and deletion reconciler | T040 | Approved-window residual-record report |
| SC-006 | Capacity/reliability/cost validation | T009, T050-T051 | Approved numeric targets and measured report |
| DOC-001 | Product/architecture/security status labeling | T001-T007 | Review finds no proposal silently presented as accepted |
| DOC-002 | Root README and documentation index | T008 | Relative-link and coverage review |
| DOC-003 | System/data-flow diagrams and architecture text | T003 | Diagram/text consistency review |
| DOC-004 | Data model and data lifecycle docs | T004 | Source-to-derived lineage and pending fields review |
| DOC-005 | Research source register and project navigation | T005, T008 | Official source title/URL/date and research-status review |
| DOC-006 | ADR set and status index | T006, T010, T014 | Required ADR fields/status/dependency review |
| DOC-007 | Tasks, validation plan, and future implementation boundary | T002, T012 | IDs, dependencies, completion criteria, no execution review |
| DOC-008 | Open Questions Register | T001, T009-T014 | Each open decision has impact, information needs, and owner/TBD |

All component/task relationships remain proposed until the relevant decision is approved. A missing owner answer leaves the affected requirement unapproved for implementation; it does not remove its traceability.