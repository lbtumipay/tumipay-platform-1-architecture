# Skill — Legacy Analysis

## Purpose
Use legacy use cases and documentation as evidence of current behavior while keeping legacy architecture separate from the target architecture.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Legacy use cases
- Legacy APIs/components
- Legacy data and integrations
- Incident or behavior documentation when supplied

## Outputs
- Legacy capability/use-case inventory
- Current flow descriptions
- Legacy dependency map
- Legacy-to-target mapping candidates
- Migration considerations and gaps

## Allowed repository areas
04-components; 05-api-and-integration/integrations; 06-data-architecture; 14-traceability

## Dependencies
repository-discovery; requirements-baseline

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
- Do not copy legacy boundaries automatically.
- Distinguish current behavior from desired behavior.
- Preserve evidence and cite source artifacts.
- Flag behavior that must be confirmed.

## Quality gate
- Current behavior is documented.
- Legacy limitations are separated from requirements.
- Candidate target mappings are explicitly labeled.
