# Development Workflow

**Status**: Spec Kit documentation workflow approved as the planning convention; implementation workflow awaits approval.

For documentation changes: update the owning source artifact, preserve requirement IDs, cite sources, check links/diagrams, and run Spec Kit analysis after task generation. The analyze skill is read-only. Checklist marks are reviewer-owned.

Before implementation: resolve security/data/region/workload decisions, approve the plan/ADRs, confirm project structure and test thresholds, and obtain explicit owner approval. Implementation work must use reviewed tasks and test evidence. Do not run `/speckit-implement` in the current phase. No branch protection, PR checks, or release strategy is configured or claimed.