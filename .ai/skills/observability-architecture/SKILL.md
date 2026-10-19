# Skill — Observability Architecture

## Purpose
Define logs, metrics, traces, business signals, audit signals, alerts and dashboards required to operate the platform.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Components
- APIs/events
- Critical transactions
- Reliability/security requirements

## Outputs
- Logging standards
- Metrics catalog
- Trace propagation
- Alerting requirements
- Business observability model

## Allowed repository areas
09-observability; 13-standards/observability; 11-cross-cutting/auditing

## Dependencies
component-architecture; integration-architecture; reliability-architecture; security-architecture

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
- Observability is part of design.
- Include correlation and transaction identifiers where required.
- Distinguish technical telemetry from business/audit signals.
- Do not prescribe tools unless a platform decision exists.

## Quality gate
- Critical flows are observable end-to-end.
- Signals have owners and purposes.
- Sensitive data is not exposed through telemetry.
