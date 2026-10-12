# Durable Records and Templates

Use the smallest set of files that keeps project knowledge clear. Adapt paths and names to local conventions.

## Stable Project Contract

```markdown
# Project Contract

## Goal
Who uses the system, what problem it solves, and what successful use looks like.

## Main Flow
1. Input and actor
2. Processing and important decisions
3. Stored facts and state changes
4. User-visible output or artifact

## Components
| Component | Owns | Receives | Produces | Must not do |
| --- | --- | --- | --- | --- |

## Rules and Boundaries
- permissions and data ownership
- retries, duplicates, cancellation, and restart behavior
- security and privacy boundaries
- performance or cost limits

## Acceptance Principles
Observable behaviors that define a useful and truthful implementation.

## Non-goals
Capabilities deliberately outside this contract.
```

Keep this document stable. A bug fix normally changes the current-state record and next plan, not the contract.

## Current-State Record

```markdown
# Current State

| ID | Requirement | Location | Classification | Current behavior | Evidence | Impact | Proposed handling | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
```

Allowed classifications include `implemented`, `partial`, `missing`, `pseudo-implemented`, `redundant`, `risk`, and `unverified`. Use evidence labels such as `static`, `reproduced`, `real-entry`, `failure-injected`, or `not-checked`.

## Next-Slice Plan

```markdown
# Next Slice

## Selected slice
- ID and requirement:
- User-visible outcome:
- Current behavior:
- Target behavior:
- Allowed scope:
- Exclusions:

## Acceptance
- normal path:
- relevant failure or cancellation:
- duplicate or restart behavior:
- evidence a non-specialist can inspect:

## Dependencies and risks

## Follow-up candidates
```

Keep one selected slice. Candidate follow-ups are not promises.

## ADR

```markdown
# ADR-XXXX: <decision>

Status: proposed | accepted | superseded

## Context
What problem and constraints require a decision?

## Options considered
What serious alternatives were checked and why they were not selected.

## Decision
What will be used and where the boundary lies.

## Consequences
Benefits, costs, new risks, migration work, and responsibilities that remain project-owned.

## Confidence and revisit trigger
What is uncertain and what evidence would cause a new decision.
```

Do not edit an accepted ADR to erase history. Add a superseding ADR when the decision changes.

## Human-Facing Handoff

Use a short summary after each slice:

```text
Completed: <user-visible change>
Proven by: <real entry point and key scenarios>
Not proven: <clear limits>
Not included: <scope excluded from this slice>
Next: <single highest-priority slice>
```
