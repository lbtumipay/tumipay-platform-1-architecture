# Skill — Architecture Review

## Purpose
Review architecture artifacts for consistency, completeness, coupling, ownership, security, reliability, observability, and traceability without silently changing decisions.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Changed architecture artifacts
- Related requirements
- ADRs
- APIs/events/data models
- Diagrams

## Outputs
- Review findings
- Severity classification
- Required corrections
- Approval/readiness status

## Allowed repository areas
14-traceability/architecture; 12-architecture-decisions/decision-log; affected artifact locations

## Dependencies
All modeling and technical Skills

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
- Findings: CRITICAL, HIGH, MEDIUM, LOW, INFO.
- Do not silently fix significant architectural decisions.
- Identify contradictions and missing ownership.
- Validate diagrams against models.
- Validate cross-references.

## Quality gate
- No unresolved critical findings.
- High findings have owners or remediation plans.
- Traceability and diagram consistency are checked.
