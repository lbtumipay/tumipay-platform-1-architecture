# Skill — Event Modeling

## Purpose
Model commands, domain events, integration events, state transitions, policies, and event semantics.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Domain model
- Bounded contexts
- Business processes
- Integration requirements

## Outputs
- Event catalog
- Command model
- State machines
- Event flows
- EVENT IDs

## Allowed repository areas
05-api-and-integration/events; 03-platform-architecture/diagrams; 02-domain/bounded-contexts

## Dependencies
bounded-context-design; context-mapping

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
- Command means intent; event means fact that occurred.
- Define producer ownership.
- Define consumers, ordering, idempotency, correlation, causation, versioning.
- Use Mermaid for sequence/state/event flows; contract schemas belong in event-contracts.

## Quality gate
- Events have owners and consumers.
- State transitions are explicit.
- Delivery semantics are documented.
