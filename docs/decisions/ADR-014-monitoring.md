# ADR-014: Monitoring and Evaluation Telemetry

**Status**: Proposed; owners, retention, and thresholds pending

## Context

FR-008/NFR-006 require operators to identify stage, status, and actionable failures without exposing prohibited content.

## Options

- Azure Monitor/Application Insights candidate for Azure service/app telemetry.
- Databricks-native pipeline observability if Databricks is selected.
- Search/model provider metrics plus application correlation events.
- Approved external observability service if policy requires it.

## Decision

No telemetry vendor, plan, retention, alert threshold, or dashboard is accepted. Require structured safe correlation across the full source-to-answer path and separate quality evaluation datasets.

## Rationale

Platform choice and data-classification policy determine available signals, privacy, retention, access, and costs.

## Consequences

Need redaction policy, stable correlation IDs, operator ownership, alert/runbook design, cost monitoring, and data-deletion treatment for telemetry.

## Dependencies

Host, Databricks decision, classification, retention, operations owners, budget, SLOs.

## References

- [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview), accessed 2026-11-02.
- [Azure Databricks Lakeflow observability](https://learn.microsoft.com/en-us/azure/databricks/ldp/observability), accessed 2026-11-02.