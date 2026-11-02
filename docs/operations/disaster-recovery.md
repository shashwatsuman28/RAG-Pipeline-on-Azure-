# Disaster Recovery

**Status**: Strategy requirements only; no backup topology or RTO/RPO is approved.

Owners must determine whether the authoritative raw source can be replayed, which derived outputs are rebuildable, which conversation state must survive, how search indexes and model deployment configuration are recreated, and what backup/restore regions and retention apply. Define failure scope (component, zone, region, identity, data corruption), recovery precedence, consistency checks, communication, and restore test cadence.

Measure observed RTO and RPO in a controlled exercise and compare to approved targets. Do not claim high availability or disaster recovery based only on candidate Azure service SLAs. No backup or failover resources are provisioned.