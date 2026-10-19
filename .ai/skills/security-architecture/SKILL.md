# Skill — Security Architecture

## Purpose
Embed identity, authentication, authorization, secrets, encryption, tenant isolation, audit, PII and compliance into platform architecture.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Platform context
- Components
- APIs/events
- Data classification
- Compliance requirements

## Outputs
- Security architecture
- AuthN/AuthZ model
- Encryption/secrets model
- Compliance controls
- Security boundaries

## Allowed repository areas
07-security; 13-standards/security; affected architecture diagrams

## Dependencies
architecture-modeling; api-design; data-architecture; integration-architecture

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
- Security is by design.
- Do not invent regulatory requirements.
- Identify security boundaries and trust zones.
- Link controls to assets and flows.

## Quality gate
- Critical assets have protection controls.
- Trust boundaries are explicit.
- Security decisions are traceable.
