# Skill — Component Architecture

## Purpose
Translate bounded-context responsibilities into platform components without assuming microservices.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Bounded contexts
- Capabilities
- Context map
- Platform principles

## Outputs
- Component catalog
- Responsibilities
- Boundaries
- Dependencies
- Interfaces
- Component diagrams

## Allowed repository areas
04-components; 03-platform-architecture/logical-architecture; 03-platform-architecture/diagrams

## Dependencies
bounded-context-design; context-mapping; architecture-modeling

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
- A component may be a service, module, worker, event processor, or other unit.
- Separate architectural role from implementation details.
- Use C4 Container/Component views for software structure.
- Avoid premature deployment decisions.

## Quality gate
- Responsibilities are cohesive.
- Dependencies have direction.
- Components trace to contexts/capabilities.
