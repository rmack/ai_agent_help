# Phase 4: Physical Architecture

## Purpose

Map the logical architecture to the real execution environment.

Physical architecture defines where and how the logical architecture actually runs. It covers runtime topology, infrastructure, cloud or on-prem services, deployment units, databases, queues, streams, containers, networking, identity, secrets, observability, scaling, and operational controls.

Repository files, folders, dependencies, commands, and implementation sequence should be defined after the runtime and deployment model are clear.

## Input

Use the accepted CONOPS, conceptual architecture, and logical architecture.

## Questions

1. Where will this run: local, on-prem, cloud, edge, or hybrid?
2. What compute model is used: containers, VMs, serverless functions, managed jobs, Kubernetes, scheduled tasks, or another runtime?
3. What deployment units exist, and how are they built, configured, released, and rolled back?
4. What data stores are required: relational database, object storage, cache, search index, warehouse, or another service?
5. How does data move at runtime: APIs, events, queues, streams, files, ETL, pub/sub, or direct database access?
6. What networking, identity, access, secrets, and data-boundary controls are required?
7. What observability, logging, monitoring, alerting, backup, recovery, and scaling expectations apply?
8. What tools, services, dependencies, and environment configuration are required? If new dependencies are required, pause for approval.
9. Is there an existing repository or is this a new project?
10. What files, folders, infrastructure definitions, or configuration files likely need to exist or change?
11. What files or areas should not change?
12. What commands, tests, smoke checks, deployment checks, or operational checks should validate the design?
13. What implementation sequence keeps changes reviewable?

## Produce

Use `templates/physical_architecture.md` and produce:

- runtime environment / topology
- deployment units
- compute, storage, messaging, and network choices
- data movement at runtime
- identity, secrets, access, and data-boundary controls
- observability, scaling, backup, and recovery expectations
- infrastructure/service dependencies
- repository/project structure
- files likely to change
- files that should not change
- tools and environment configuration
- validation commands/checks
- implementation sequence
- risks / stop conditions

## Stop / Continue

After producing the physical architecture, ask:

```text
Does this physical architecture and implementation sequence look right?

Choose one:
1. Revise Physical Architecture
2. Create Architecture Decision Summary
3. Move toward implementation planning
4. Stop and summarize what we have
```
