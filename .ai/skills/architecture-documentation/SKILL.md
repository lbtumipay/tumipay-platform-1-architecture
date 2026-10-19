# Skill — Architecture Documentation

## Purpose
Maintain coherent, navigable, consistent architecture documentation and cross-references.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Existing artifacts
- Standards
- Diagrams
- ADRs
- Catalogs

## Outputs
- Updated README/index pages
- Cross references
- Consistent terminology and metadata
- Architecture Blueprint sections

## Allowed repository areas
01-context; 02-domain; 03-platform-architecture; 04-components; 05-api-and-integration; 06-data-architecture; 07-security; 08-reliability; 09-observability; 10-infrastructure; 11-cross-cutting; 12-architecture-decisions; 13-standards; 14-traceability; 15-roadmap

## Dependencies
repository-discovery; architecture-review; architecture-traceability

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
- Do not create a second source of truth.
- Prefer links to canonical artifacts.
- Preserve repository language and structure.
- Ensure diagrams and prose agree.
- Keep Blueprint as consolidated view, not a duplicate of every artifact.

## Quality gate
- Links resolve.
- Terminology is consistent.
- Blueprint references canonical artifacts.
- No unnecessary duplication.
