# Skill — Bounded Context Design

## Purpose
Define explicit model boundaries and ownership around domains.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Domain model
- Capabilities
- Business terminology
- Existing integrations

## Outputs
- Bounded Context catalog
- Responsibilities
- Aggregates/value objects
- Commands/events
- Data ownership
- CTX IDs

## Allowed repository areas
02-domain/bounded-contexts; 03-platform-architecture/diagrams

## Dependencies
domain-modeling; capability-modeling

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
- A bounded context is a semantic boundary, not automatically a deployment unit.
- Define responsibility and model language.
- Identify invariants and ownership.
- Use Mermaid for context maps and domain/entity models.

## Quality gate
- Each context has clear responsibility.
- Ownership and boundaries are explicit.
- No unjustified shared kernel.
