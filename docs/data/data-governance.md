# Data Governance

**Status**: Pending data-owner decision. “Portfolio project” does not establish that the data is synthetic or non-sensitive.

Before data use, identify the data owner, classification, source rights, permitted purpose, residency/jurisdiction, regulatory obligations, access groups, retention, legal holds, deletion, backup, and model-service handling terms. The approved corpus must be synthetic or explicitly authorized. Keep a field-level inventory for source, extracted text, table cells, metadata, embeddings, prompts, answers, logs, caches, and backups.

Access controls apply end to end; permission metadata itself may be sensitive. Search index, processed Delta data, model prompts, and observability stores need explicit owners and access policies. No compliance certification, data residency, or deletion guarantee may be claimed without service/configuration review and test evidence.

Decision owners and blockers are listed in [open questions](../project-management/open-questions.md); requirement coverage is in [DR and SEC requirements](../product/requirements.md).