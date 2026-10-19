# Skill — Capability Modeling

## Purpose
Identify and structure business capabilities independently of implementation technology or service boundaries.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Requirements baseline
- Product scope
- Business processes
- Legacy evidence

## Outputs
- Capability map
- Capability catalog
- Classification
- Dependencies
- CAP IDs

## Allowed repository areas
02-domain/capabilities; 14-traceability/capabilities

## Dependencies
requirements-baseline; legacy-analysis

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
- Do not name capabilities as microservices.
- Distinguish capability from feature, product, process, and component.
- Preserve business language.
- Use Mermaid for capability relationships when useful.

## Quality gate
- Capabilities cover the validated scope.
- Each critical capability traces to requirements.
- No implementation assumptions are embedded.
