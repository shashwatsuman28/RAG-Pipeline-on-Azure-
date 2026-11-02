# RAG Quality Checklist: Documentio Enterprise Document Intelligence Platform

**Purpose**: Review retrieval and answer-quality requirements independently
**Created**: 2026-11-02
**Feature**: [spec.md](../spec.md)

**Note**: Custom reviewer-owned requirements-quality checklist.
**Review Ownership**: Mark an item `[x]` only after a reviewer confirms the requirement quality criterion.
**Marker Semantics**: `[x]` indicates requirements review, not implementation completion.

## RAG Requirements

- [ ] CHK031 - Are retrieval relevance, answer support, citation correctness, abstention, and user outcomes measured as separate dimensions? [Completeness, FR-004–FR-005, SC-002]
- [ ] CHK032 - Are the approved corpus, query set, relevance labels, evaluators, language coverage, and evaluation cadence specified? [Gap, SC-002]
- [ ] CHK033 - Are ranking and context-construction criteria measurable, including treatment of conflicting, stale, and insufficient evidence? [Clarity, FR-005]
- [ ] CHK034 - Are citations required to resolve to an authorized source revision and precise source location where available? [Traceability, FR-003, FR-005]
- [ ] CHK035 - Are model refusal/abstention criteria defined for no evidence, low-confidence evidence, and dependency failure? [Coverage, FR-005]
- [ ] CHK036 - Are retrieved-document prompt injection and unsafe instruction handling represented in the evaluation requirements? [Security, SEC-003]
- [ ] CHK037 - Are candidate models and embedding dimensions evaluated with versioned benchmark data rather than accepted from catalog claims alone? [Assumption, INT-004]

## Notes

- Retrieval and generation have separate quality gates; no scores have been measured.