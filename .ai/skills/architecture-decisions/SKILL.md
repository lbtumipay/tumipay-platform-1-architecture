# Skill — Architecture Decisions

## Purpose
Capture significant architectural choices in ADRs and maintain the decision log.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Architecture proposals
- Alternatives
- Impact analysis
- Review findings

## Outputs
- ADRs
- Decision log
- Status and supersession links

## Allowed repository areas
12-architecture-decisions/adr; 12-architecture-decisions/decision-log

## Dependencies
architecture-review; all decision-producing Skills

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
- ADRs explain why, not merely what.
- Include context, problem, decision, alternatives, consequences, risks, related requirements and artifacts.
- Do not create ADRs for trivial documentation changes.
- Supersede rather than silently rewrite accepted decisions.

## Quality gate
- Significant decisions are documented.
- Status is explicit.
- Related artifacts link back to the ADR.
