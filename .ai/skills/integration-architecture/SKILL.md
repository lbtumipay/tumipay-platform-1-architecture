# Skill — Integration Architecture

## Purpose
Design resilient interactions with banks, PSPs, acquirers, networks, processors, merchants, and internal/external systems.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- External ecosystem
- Provider behavior
- Component boundaries
- APIs/events

## Outputs
- Integration catalog
- Provider adapter model
- Failure model
- Retry/timeout strategy
- Webhook/polling strategy
- Reconciliation considerations

## Allowed repository areas
05-api-and-integration/integrations; 08-reliability; 04-components; 03-platform-architecture/diagrams

## Dependencies
component-architecture; context-mapping; reliability-architecture

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
- Capture protocol, auth, timeout, retry, backoff, circuit breaker, rate limit, idempotency, webhooks, polling, reconciliation, error mapping.
- Keep provider-specific semantics outside core models using adapters/ACLs where appropriate.
- Use C4 for software structure and Mermaid for interaction sequences.

## Quality gate
- Each integration has an owner and failure behavior.
- Provider-specific coupling is controlled.
- Critical failure paths are documented.
