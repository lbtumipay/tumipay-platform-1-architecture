# Skill — Domain Modeling

## Purpose
Transform capabilities into domains, subdomains, entities, relationships, actors, processes, and glossary terms.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Capability map
- Requirements
- Legacy evidence
- Business terminology

## Outputs
- Domain map
- Subdomain classification
- Domain glossary
- Entity/relationship model
- DOM IDs

## Allowed repository areas
02-domain/domain-model; 02-domain/glossary; 02-domain/capabilities

## Dependencies
capability-modeling; legacy-analysis

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
- Keep business semantics primary.
- Do not infer bounded contexts automatically.
- Use Mermaid for domain/entity models.
- Record unresolved business meaning as open questions.

## Quality gate
- Domain boundaries are explainable.
- Terms are consistent.
- Entities have business meaning and ownership candidates.
