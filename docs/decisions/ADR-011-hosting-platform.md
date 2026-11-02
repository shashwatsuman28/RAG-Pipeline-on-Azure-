# ADR-011: Application Hosting Platform

**Status**: Pending workload and operations input

## Context

The brief lists Azure App Service and AKS but explicitly requires trade-off analysis instead of an unsupported selection.

## Options

- App Service for managed web/API deployment.
- AKS Automatic for a more managed Kubernetes experience, or AKS Standard when additional cluster/node-pool control is required.
- Revisit alternatives only with owner approval if both fail a documented requirement.

## Decision

No host accepted. Compare after API/worker split, load profile, network constraints, team skills, availability and cost are approved.

## Rationale

App Service lowers platform operations for web/API workloads. AKS Automatic manages more node, scaling, security, and monitoring configuration; AKS Standard exposes more cluster control and operator responsibility. Concurrent users alone are insufficient to size either.

## Consequences

Host affects identity, private networking, autoscaling, background work, CI/CD, support burden, HA, and spend.

## Dependencies

Workload profile, client/API scope, background processing, team skills, networking, region, budget, SLO/RTO/RPO.

## References

- [Azure compute decision guide](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree), accessed 2026-11-02.
- [App Service overview](https://learn.microsoft.com/en-us/azure/app-service/overview), accessed 2026-11-02.
- [AKS overview](https://learn.microsoft.com/en-us/azure/aks/what-is-aks), accessed 2026-11-02.