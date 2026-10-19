# TumiPay Platform 3 — Architecture Agent Instructions

## Mission

This repository is the source of truth for TumiPay Platform 3 platform architecture. AI agents must use the existing repository structure and evolve the architecture progressively from requirements to infrastructure.

## Scope boundary

This repository describes platform architecture. Component repositories describe implementation, tests, deployment implementation, and component-specific engineering workflows.

## Mandatory modeling sequence

Requirements → Capabilities → Domains → Bounded Contexts → Context Mapping → Domain/Event Model → Transaction/Ledger → Components → Integrations → APIs/Events → Data → Security/Reliability/Observability → Infrastructure.

Do not jump directly from product requirements or legacy use cases to microservices.

## Source classification

Every important architectural statement must be classified when ambiguity exists:

- 🟢 Defined by Source
- 🔵 Derived by Architecture
- 🟡 Architectural Assumption
- 🔴 Pending Decision

Never convert an assumption or inference into a business requirement.

## Diagram policy

Use C4 for software architecture structure:

- System Context
- Container
- Component
- Deployment where C4-style deployment modeling is useful

Use Mermaid for behavior and semantic/domain modeling:

- business processes
- flowcharts
- sequence diagrams
- state machines
- domain/entity models
- aggregates/value objects
- bounded-context relationships
- context maps
- event flows
- data flows

Do not use a generic Mermaid diagram when a C4 software-architecture view is required. Do not force C4 onto business processes or domain behavior.

## First-run behavior

Before creating architecture artifacts, run `repository-discovery`. The first result must be a repository discovery report and an execution plan. Do not create hundreds of files in one run.

## Change discipline

Before changing an artifact:

1. Inspect related artifacts.
2. Check source and ownership.
3. Check traceability.
4. Identify affected decisions, APIs, events, data, security, reliability, and infrastructure.
5. Create/update an ADR when a significant architectural decision changes.
6. Run architecture review and traceability checks.

## Stable IDs

Use stable IDs such as REQ-XXX, CAP-XXX, DOM-XXX, CTX-XXX, COMP-XXX, API-XXX, EVENT-XXX, DATA-XXX, ADR-XXX. Do not change referenced IDs casually.

## Quality gate

A phase is complete only when its artifacts are internally consistent, linked to their sources, and have no unresolved critical findings.
