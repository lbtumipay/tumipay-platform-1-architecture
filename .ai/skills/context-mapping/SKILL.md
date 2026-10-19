# Skill — Context Mapping

## Purpose
Model relationships between bounded contexts and define dependency direction and integration semantics.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Bounded contexts
- APIs/events
- Data ownership
- Business flows

## Outputs
- Context map
- Relationship types
- Upstream/downstream
- ACL/published language definitions

## Allowed repository areas
02-domain/bounded-contexts; 03-platform-architecture/diagrams; 05-api-and-integration/integrations

## Dependencies
bounded-context-design; integration-architecture

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
- Evaluate Customer/Supplier, Conformist, ACL, Published Language, OHS, Shared Kernel.
- Do not introduce shared ownership casually.
- Use Mermaid for context maps.

## Quality gate
- Every relationship has direction and rationale.
- Integration contracts align with context relationships.
