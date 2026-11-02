# Infrastructure Requirements

**Status**: Candidate services only; no SKU, resource configuration, or infrastructure template is approved.

Candidate categories include source object storage, extraction, optional distributed processing/lakehouse, embeddings and chat model deployments, search/index, application compute, identity, network, monitoring, and optional conversation persistence. Each service needs a role, region, tier/quota, private connectivity, data classification, lifecycle, scaling, backup, owner, and cost guardrail.

Azure AI Search limits and vector capacity vary by tier, region, and service creation date. Document Intelligence limits vary by tier/model. Model deployment availability and quota vary by region and deployment type. The 1,000-concurrent/50,000-total-user signal does not determine infrastructure capacity. See the [official limit sources](../architecture/integration-architecture.md) and [open questions](../project-management/open-questions.md).