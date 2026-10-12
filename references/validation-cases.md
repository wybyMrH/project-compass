# Skill Validation Cases

Use these small scenarios to check that the skill still produces the intended behavior after an instruction change. The cases are behavioral probes, not application tests.

## Case 1: Empty repository

Input: an empty folder and a request such as "build a service that accepts one text file and shows a summary".

Expected behavior:

- classify the repository as empty or nearly empty;
- ask only questions that change the first outcome, such as user, input type, summary source, and persistence;
- create a small draft contract with assumptions and open questions;
- propose one walking slice, such as local text upload, stored request state, and a visible placeholder result;
- avoid inventing a full platform, multi-tenant model, or production quality claim.

Failure signals: a large architecture appears before the first outcome, assumptions are hidden, or the agent starts coding without an observable acceptance condition.

## Case 2: Half-built and contradictory repository

Input: a README says the service uses PostgreSQL, configuration points to SQLite, an endpoint returns `done` immediately, and tests only mock completion.

Expected behavior:

- identify the contradiction and likely source of truth;
- classify the immediate completion as pseudo-implemented or risky until a real completion fact is observed;
- record the finding in the current-state record with evidence;
- select a bounded slice that establishes authoritative state and real completion;
- keep the database migration, UI redesign, and unrelated cleanup outside the slice.

Failure signals: choosing a database from the README alone, calling the endpoint complete because the response says so, or rewriting the stable contract to match the shortcut.

## Case 3: Well-documented repository

Input: the repository has rules, a stable contract, current-state entries, a next-slice plan, and an accepted ADR. The user asks to fix duplicate retries.

Expected behavior:

- read the existing records and relevant callers first;
- preserve the stable contract unless the requested behavior changes it;
- define one slice around the duplicate side effect and its authoritative key;
- verify the real entry point, a duplicate request, and restart or recovery when relevant;
- update current state and the next plan only after the evidence is available.

Failure signals: regenerating all project documents, implementing every retry path at once, or treating a unit mock as proof of recovery.

## Case 4: Technical candidate evaluation

Input: a project needs PDF structure extraction and is considering two public libraries.

Expected behavior:

- compare both candidates against the actual input and output contract;
- record source URLs, versions, licenses, runtime cost, failure behavior, and project-owned rules;
- run or propose the smallest isolated proof with fixed non-sensitive input;
- make adoption conditional on evidence and define the old path's exit condition.

Failure signals: adding both libraries to production, relying on popularity alone, or saying the library guarantees the product's evidence or quality rules.

## Case 5: Verification failure

Input: the normal path appears to work with a deterministic provider, but a timeout leaves the external result unknown.

Expected behavior:

- keep the slice open or reduce the completion claim;
- record the unknown state and reconciliation requirement;
- avoid blind retry and avoid hand-editing the final state;
- state exactly what the fixture proved and what a real provider still needs to prove.

Failure signals: marking the run complete because a notification arrived, retrying without an idempotency rule, or deleting the failing scenario.

## Case 6: Plain-language handoff

Input: a technically correct slice has been verified.

Expected behavior:

- explain the visible effect first;
- distinguish completed, proven, not proven, excluded, and next;
- use the user's language where practical and explain unavoidable terms;
- link evidence without dumping logs or internal implementation detail.

Failure signals: a list of changed files with no user outcome, unexplained jargon, or a claim of full completion when a stated boundary remains.

## Regression checklist

After any skill edit:

- run `quick_validate.py`;
- check that all reference links resolve;
- scan for local paths, project names, credentials, and session identifiers;
- run each case as a short dry run and record pass/fail outside the skill repository;
- inspect the diff for new universal rules that came from only one project.
