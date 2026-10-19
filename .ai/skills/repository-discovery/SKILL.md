# Skill — Repository Discovery

## Purpose
Map the repository before architectural construction. Establish structure, conventions, sources, existing artifacts, Skills, standards, ADRs, traceability, and gaps.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Repository tree
- README and instructions
- Existing architecture artifacts
- Existing Skills or agent instructions
- User-provided source directories

## Outputs
- Repository Discovery Report
- Source Inventory
- Existing Architecture Inventory
- Gap and Risk Inventory
- Proposed execution sequence

## Allowed repository areas
Read-only across the repository initially; report should live under 01-context or a clearly designated discovery artifact.

## Dependencies
None; this is the first Skill.

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
- Do not design target architecture during discovery.
- Do not overwrite existing documentation.
- Do not infer missing requirements.
- Identify the authoritative location for each concern.
- Detect duplicate or conflicting sources.

## Quality gate
- Repository structure is mapped.
- Source-of-truth boundaries are identified.
- Existing conventions are captured.
- Gaps and conflicts are explicit.
- Next phase is clearly identified.
