# Skill — Reliability Architecture

## Purpose
Define resilience, availability, failure behavior, disaster recovery and capacity expectations.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Components
- Integrations
- Critical business flows
- NFRs

## Outputs
- Resilience patterns
- Failure models
- Availability targets
- DR model
- Capacity considerations

## Allowed repository areas
08-reliability; 11-cross-cutting/idempotency; 11-cross-cutting/error-handling; 11-cross-cutting/messaging

## Dependencies
integration-architecture; component-architecture; event-modeling

## Operating procedure
1. Read `AGENTS.md` and this Skill.
2. Inspect existing artifacts before creating new ones.
3. Identify source, ownership, related IDs, and affected artifacts.
4. Preserve existing terminology and repository conventions.
5. Classify ambiguity as Defined, Derived, Assumption, or Pending Decision.
6. Create the smallest coherent set of artifacts required by the task.
7. Cross-reference related artifacts instead of duplicating content.
8. Run the quality gate below before declaring the work complete.

## Rules
- Specify timeout, retry, backoff, circuit breaker, bulkhead, queues, DLQ, idempotency, RTO/RPO where supported.
- Avoid blanket retries.
- Tie controls to failure scenarios.

## Quality gate
- Critical failure modes have mitigation.
- Reliability requirements are explicit or pending decisions.
