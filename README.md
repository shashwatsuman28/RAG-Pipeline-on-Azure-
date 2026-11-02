# Documentio

Documentio is a proposed enterprise document intelligence and retrieval-augmented generation platform on Microsoft Azure. This repository is in the **documentation phase**. No application code, Azure resources, or deployment artifacts have been created.

## Status

- Confirmed planning inputs: single-organization first release, Microsoft Entra ID selected provisionally for user authentication, portfolio project, Python, Azure service candidates, and an unverified planning signal of 1,000 concurrent / 50,000 total users.
- Pending approval: authoritative document permissions, corpus/data classification, region, retention, workload limits and SLOs, model deployments, search configuration, hosting, budget, networking, client/UI scope, and application structure.
- No requirements are approved for implementation until the owners resolve their blockers and review the architecture.

## Start Here

- [Documentation index](docs/README.md)
- [Product specification](specs/001-documentio-platform/spec.md)
- [Implementation plan](specs/001-documentio-platform/plan.md)
- [Future tasks](specs/001-documentio-platform/tasks.md)
- [Open questions](docs/project-management/open-questions.md)
- [Technical research and sources](specs/001-documentio-platform/research.md)
- [Project constitution](.specify/memory/constitution.md)

## Spec Kit

This project uses GitHub Spec Kit 1.2.6 with GitHub Copilot skills. Use the reviewed skills in sequence: `/speckit-constitution`, `/speckit-specify`, `/speckit-clarify`, `/speckit-plan`, `/speckit-tasks`, `/speckit-checklist`, `/speckit-analyze`. Do not invoke `/speckit-implement` until the project owner approves the documentation and architecture. The bundled workflow includes implementation and must not be run as a whole for this project phase.

## Scope

This repository contains planning and documentation only. See [scope](docs/product/scope.md), [architecture status](docs/architecture/overview.md), and [quality gates](docs/project-management/roadmap.md) before proposing implementation work.