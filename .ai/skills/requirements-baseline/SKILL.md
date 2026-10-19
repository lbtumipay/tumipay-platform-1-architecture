# Skill — Requirements Baseline

## Purpose
Normalize product and functional sources into an architecture-ready baseline without inventing business rules.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Product requirements
- Product scope
- Functional documents
- Existing architecture drivers
- Legacy references when explicitly provided

## Outputs
- Requirements catalog
- Product/solution inventory
- Channel inventory
- Capability inventory
- Architectural drivers
- Ambiguities, assumptions, open questions
- Requirements traceability baseline

## Allowed repository areas
01-context/business-context; 01-context/architecture-drivers; 14-traceability/requirements; 14-traceability/capabilities

## Dependencies
repository-discovery

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
- Preserve source terminology.
- Separate product statements from architectural implications.
- Never invent acceptance criteria or business rules.
- Assign stable REQ IDs.
- Stop progression when critical scope ambiguity remains.

## Quality gate
- Every requirement has a source.
- Ambiguities are explicit.
- No invented business rules.
- Requirements can map to capabilities.
