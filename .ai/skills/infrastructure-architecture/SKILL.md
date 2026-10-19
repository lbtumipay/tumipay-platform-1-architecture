# Skill — Infrastructure Architecture

## Purpose
Translate logical platform architecture into AWS, networking, compute, storage, messaging, Kubernetes, environments and deployment architecture.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Logical architecture
- Components
- Security/reliability requirements
- Existing AWS account/environment model

## Outputs
- Physical architecture
- Deployment architecture
- Environment model
- AWS/networking/storage/messaging views
- Infrastructure decisions

## Allowed repository areas
10-infrastructure; 03-platform-architecture/physical-architecture; 03-platform-architecture/deployment-architecture

## Dependencies
component-architecture; security-architecture; reliability-architecture; observability-architecture

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
- Do not assume technology merely because it exists.
- Separate architecture from Terraform/Kubernetes implementation.
- Respect account/environment boundaries.
- Document availability, scaling, security, cost and DR implications.
- Use C4/deployment-style diagrams for software/deployment structure when appropriate.

## Quality gate
- Every deployment unit maps to an architectural component.
- Network/trust boundaries are consistent with security.
- Scaling and failure assumptions are explicit.
