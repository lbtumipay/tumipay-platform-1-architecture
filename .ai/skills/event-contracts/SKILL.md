# Skill — Event Contracts

## Purpose
Formalize integration-event schemas, ownership, versioning and delivery semantics.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Event catalog
- Producers/consumers
- Domain events
- Integration requirements

## Outputs
- Event contract files
- Schema metadata
- Versioning policy
- Consumer/producer mapping

## Allowed repository areas
05-api-and-integration/events; 05-api-and-integration/contracts; 13-standards/api

## Dependencies
event-modeling; api-design

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
- Separate domain events from integration contracts.
- Preserve backward compatibility unless an explicit breaking change is approved.
- Document ordering, delivery, retry, idempotency, correlation and causation.

## Quality gate
- Event catalog and schemas match.
- Producer/consumer ownership is explicit.
- Version changes are traceable.
