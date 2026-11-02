# Contributing

## Current Phase

Contributions are limited to reviewed documentation and Spec Kit artifacts. Do not add application source, deployment scripts, infrastructure definitions, credentials, or Azure resources before project-owner approval.

## Documentation Changes

1. Read the project constitution and the applicable feature specification.
2. Label statements as confirmed, proposed, assumption, pending decision, verified research, or not implemented.
3. Give requirements stable IDs and measurable acceptance criteria; map them to architecture, tasks, and validation evidence.
4. Cite official sources with title, URL, and access date. Distinguish research from runtime testing.
5. Run the relevant Spec Kit skill and check relative links, requirement coverage, diagrams, and status wording.
6. Leave reviewer-owned checklist markers unchecked unless a reviewer has actually reviewed the criterion.

## Spec Kit Workflow

Use the individual Copilot skill commands in the documented sequence. `/speckit-analyze` is read-only. Do not run the bundled `.specify/workflows/speckit/workflow.yml` as a whole: its final step invokes `/speckit-implement`, which is outside the approved phase.

## Review Requirements

Changes affecting security, data handling, identity, region, cost, service/model selection, or operational targets require the relevant product, security, data, or operations owner to resolve the linked open question. Never silently turn a candidate into an accepted decision.