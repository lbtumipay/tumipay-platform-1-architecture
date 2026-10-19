# Skill — Architecture Traceability

## Purpose
Maintain end-to-end links from requirements through capabilities, domains, contexts, components, contracts, data, security/reliability, and infrastructure.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Stable IDs
- Architecture artifacts
- ADRs
- APIs/events/data artifacts
- Infrastructure artifacts

## Outputs
- Traceability matrices
- Orphan findings
- Missing-link findings
- Impact analysis

## Allowed repository areas
14-traceability/**

## Dependencies
requirements-baseline; capability-modeling; domain-modeling; bounded-context-design; component-architecture; api-design; event-contracts; data-architecture; infrastructure-architecture

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
- Never invent a traceability link.
- Flag broken references.
- Keep IDs stable.
- Trace both forward and backward.
- Identify impact when a source artifact changes.

## Quality gate
- Every critical artifact has a source and downstream impact path.
- Broken references are zero or explicitly tracked.
