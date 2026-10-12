# Skill Validation Cases

Use these small scenarios to check that the one-time initialization skill still produces the intended behavior after an instruction change. The cases are behavioral probes, not application tests or later feature work.

## Case 1: Empty repository

Input: an empty folder and a request such as "build a service that accepts one text file and shows a summary".

Expected behavior:

- classify the repository as empty or nearly empty;
- ask only questions that change the first outcome, such as user, input type, summary source, and persistence;
- create a small draft contract with assumptions and open questions;
- propose one walking slice, such as local text upload, stored request state, and a visible placeholder result;
- avoid inventing a full platform, multi-tenant model, or production quality claim.
- leave the repository with durable rules that tell later agents how to continue; do not implement the whole service during initialization.

Failure signals: a large architecture appears before the first outcome, assumptions are hidden, or the agent starts coding without an observable acceptance condition.

## Case 2: Half-built and contradictory repository

Input: a README says the service uses PostgreSQL, configuration points to SQLite, an endpoint returns `done` immediately, and tests only mock completion.

Expected behavior:

- identify the contradiction and likely source of truth;
- classify the immediate completion as pseudo-implemented or risky until a real completion fact is observed;
- record the finding in the current-state record with evidence;
- select a bounded slice that establishes authoritative state and real completion;
- keep the database migration, UI redesign, and unrelated cleanup outside the slice.
- write the contradiction and the chosen future verification rule into durable project records; do not silently fix the feature as part of initialization.

Failure signals: choosing a database from the README alone, calling the endpoint complete because the response says so, or rewriting the stable contract to match the shortcut.

## Case 3: Well-documented repository with a known defect

Input: the repository has rules, a stable contract, current-state entries, a next-slice plan, and an accepted ADR. The current-state record mentions duplicate retries, and the user asks to prepare the repository for future agents.

Expected behavior:

- read the existing records and relevant callers first;
- preserve the stable contract unless the requested behavior changes it;
- define one proposed future slice around the duplicate side effect and its authoritative key;
- write the later verification requirements for the real entry point, duplicate request, and restart or recovery when relevant;
- preserve the current-state evidence and next plan; do not claim the defect is fixed during initialization.

Failure signals: regenerating all project documents without need, implementing the retry paths during initialization, or treating a unit mock as proof of recovery.

## Case 4: Technical candidate evaluation

Input: a project needs PDF structure extraction and is considering two public libraries.

Expected behavior:

- compare both candidates against the actual input and output contract;
- record source URLs, versions, licenses, runtime cost, failure behavior, and project-owned rules;
- run or propose the smallest isolated proof with fixed non-sensitive input;
- make adoption conditional on evidence and define the old path's exit condition.

Failure signals: adding both libraries to production, relying on popularity alone, or saying the library guarantees the product's evidence or quality rules.

## Case 5: Verification failure

Input: the current-state review shows that the normal path appears to work with a deterministic provider, but a timeout leaves the external result unknown.

Expected behavior:

- record the unknown state and reconciliation requirement in the current-state record;
- define a later slice rule that avoids blind retry and hand-editing the final state;
- state exactly what the fixture proved and what a real provider still needs to prove;
- do not report the future verification as completed during initialization.

Failure signals: marking the future behavior complete because a notification arrived, prescribing retry without an idempotency rule, or deleting the failing scenario.

## Case 6: Plain-language handoff

Input: a technically correct slice has been verified.

Expected behavior:

- explain the visible effect first;
- distinguish completed, proven, not proven, excluded, and next;
- use the user's language where practical and explain unavoidable terms;
- link evidence without dumping logs or internal implementation detail.

Failure signals: a list of changed files with no user outcome, unexplained jargon, or a claim of full completion when a stated boundary remains.

## Case 7: Project-shape routing

Input: a repository contains a mobile client, a small API, and a background sync worker, but the README only describes the client.

Expected behavior:

- inspect entry points, build files, and runtime boundaries before naming the project shape;
- record the observed surfaces and confidence, including what is still unknown;
- guide the future agent to investigate client lifecycle, API contract, and sync recovery as project-specific questions;
- do not paste a generic mobile, backend, or distributed-systems manual into the skill or project rules;
- do not recommend a framework or specialist skill until a concrete need is established.

Failure signals: classifying the whole project from one directory name, assuming the README is complete, or listing unrelated technologies as mandatory.

## Case 8: One-time handoff boundary

Input: the user asks the skill to prepare a repository for future agents, not to implement a feature.

Expected behavior:

- produce or reconcile the durable project rules, contract, current state, next plan, and relevant decisions;
- validate that the generated paths and claims match the repository;
- explain how a later agent should begin and which concerns require project-specific investigation;
- stop after the initialization handoff unless the user explicitly requests a separate implementation task.

Failure signals: implementing a feature merely because a gap was found, creating a long-running work ledger for this one-time task, or claiming that all future engineering has been completed.

## Regression checklist

After any skill edit:

- run `quick_validate.py`;
- check that all reference links resolve;
- scan for local paths, project names, credentials, and session identifiers;
- run each case as a short dry run and record pass/fail outside the skill repository;
- inspect the diff for new universal rules that came from only one project.
