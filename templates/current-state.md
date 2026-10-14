# Current State Record

Use this record for a concrete requirement or task. Do not populate it from guesses.

Keep this as the current snapshot: update or replace affected entries instead of appending a report for each stage. Carry forward unresolved findings and evidence still needed to assess the project. Remove obsolete or resolved detail once its useful facts are reflected in the current summary; use version control for prior snapshots when available. Retain history explicitly required by repository policy.

Document readiness: `[unfilled template / reviewed scope]`. A placeholder row is not a finding. Do not classify features as missing merely because a project is empty and its requirements are undecided.

## Review scope

State what concrete requirement is being checked and how far the evidence reaches. An empty repository with an open product has no feature gaps to classify yet.

- Requirement or task: `[To be confirmed]`
- Review date: `[To be confirmed]`
- Evidence boundary: `[files, commands, runtime paths]`
- Coverage limits: `[what was not inspected or exercised]`

| ID | Requirement or contract point | File/module/boundary | Classification | Observed behavior | Evidence level | Impact | Proposed handling | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `[ID]` | `[To be confirmed]` | `[To be confirmed]` | `implemented / partial / missing / pseudo-implemented / redundant / risk / unverified` | `[To be confirmed]` | `static / unit / contract / real-entry / failure-injected / browser-visible / not-verified` | `[To be confirmed]` | `[To be confirmed]` | `open` |

## Findings in plain language

Turn technical observations into a readable explanation that can support a user decision. Keep diagnosis separate from implementation work.

For each important finding, explain:

1. What the user or system needs.
2. What happens now.
3. What should happen.
4. Why the difference matters.
5. Evidence and affected boundary.
6. A proposed next action, without claiming it is completed.

## Review coverage and closure criteria

- Files/modules reviewed and depth of review: `[static inventory / relevant code and consumers read / runtime exercised]`
- Files or boundaries not checked: `[To be confirmed]`
- What evidence would close each finding: `[To be confirmed]`
- Last checked revision or date when relevant: `[To be confirmed]`

A file scan is not a semantic audit. During later slices, update evidence for affected files and do not reuse stale verification as current proof.

## Removal or consolidation candidates

Use this only when a real cleanup candidate has consumers and evidence to inspect. Similar names or shorter code are not enough reason to remove something.

Record consumers, unique behavior, coverage, compatibility needs, and an exit condition before removing or merging anything.
