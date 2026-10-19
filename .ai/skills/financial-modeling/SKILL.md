# Skill — Transaction and Financial Modeling

## Purpose
Model money movement, transactions, accounts, balances, ledger entries, settlement, fees, refunds, reversals, currency and FX without inventing accounting policy.

## Scope
This Skill performs only the responsibility described above. It must not silently redesign unrelated areas of the platform.

## Inputs
- Product/functional requirements
- Payment use cases
- Account/domain model
- Existing financial behavior

## Outputs
- Transaction model
- Financial state machines
- Ledger model
- Balance model
- Financial event model
- DATA/DOM traceability

## Allowed repository areas
02-domain; 06-data-architecture; 05-api-and-integration/events; 03-platform-architecture/diagrams

## Dependencies
domain-modeling; bounded-context-design; event-modeling

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
- Treat financial correctness as critical.
- Evaluate double-entry where appropriate.
- Never invent accounting rules.
- Distinguish transaction state from financial posting state.
- Use Mermaid for financial flows and entity relationships.

## Quality gate
- Money movement can be explained end-to-end.
- Balance semantics are explicit.
- Missing accounting rules are pending decisions.
