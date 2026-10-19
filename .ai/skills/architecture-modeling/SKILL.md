# Skill — Architecture Modeling

## Purpose
Coordinate the progression from requirements and capabilities through domains, contexts, components, interfaces, and infrastructure without collapsing architectural abstractions.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Existing architecture artifacts
- Requirements/capabilities/domains
- Related Skills outputs

## Outputs
- Coherent cross-layer architecture models
- Updated architecture relationships
- Identified dependencies and decisions

## Allowed repository areas
01-context; 02-domain; 03-platform-architecture; 04-components; 05-api-and-integration; 06-data-architecture; 10-infrastructure

## Dependencies
requirements-baseline; legacy-analysis; capability-modeling; domain-modeling; bounded-context-design

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
- Keep Product, Capability, Domain, Bounded Context, Component, and Deployment Unit distinct.
- Do not start from microservices.
- Prefer references over duplicated models.
- Escalate significant decisions to architecture-decisions.

## Quality gate
- Cross-layer relationships are consistent.
- No abstraction is incorrectly equated with another.
- Decisions have owners and traceability.
