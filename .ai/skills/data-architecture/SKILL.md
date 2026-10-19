# Skill — Data Architecture

## Purpose
Define data ownership, logical/physical models, database boundaries, lifecycle, flows and governance.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Domain model
- Bounded contexts
- Components
- APIs/events
- Regulatory/data requirements

## Outputs
- Data domain catalog
- Logical data model
- Database boundaries
- Data flows
- Governance and lifecycle

## Allowed repository areas
06-data-architecture; 14-traceability/architecture

## Dependencies
domain-modeling; bounded-context-design; component-architecture; event-contracts

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
- Data ownership follows domain ownership.
- Do not create databases solely because services exist.
- Separate logical ownership from physical technology.
- Use Mermaid ER/class diagrams for data/domain semantics.

## Quality gate
- Every critical dataset has an owner.
- Data flows are traceable.
- Retention/security requirements are identified.
