# Skill — Architecture Diagramming

## Purpose
Select and produce the correct diagram notation for each architecture artifact. C4 is mandatory for software structure; Mermaid is mandatory for behavior and domain/semantic models.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Architecture artifact being modeled
- Scope and audience
- Existing diagram conventions

## Outputs
- C4 diagrams for software architecture
- Mermaid diagrams for processes, sequences, domain/entity/context/event/state/data flows
- Diagram metadata and cross-references

## Allowed repository areas
03-platform-architecture/diagrams; 03-platform-architecture/logical-architecture; 03-platform-architecture/physical-architecture; 04-components/**/diagrams; relevant domain/API/data folders

## Dependencies
repository-discovery; architecture-modeling

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
- C4: System Context, Container, Component, and appropriate Deployment views for software structure.
- Mermaid: process, sequence, state, entity/aggregate, context map, event flow, data flow.
- Do not use generic flowcharts for software architecture when a C4 view applies.
- Every diagram must state title, purpose, scope, and related artifacts.
- Prefer Mermaid source committed as text.
- Keep diagrams consistent with the underlying models; never let a diagram become an independent source of truth.

## Quality gate
- Diagram notation matches intent.
- Names match canonical artifacts.
- Relationships are supported by the model.
- Diagram source is versionable and readable.
