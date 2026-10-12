---
name: project-understanding-delivery
description: Guide an AI coding agent from an empty, incomplete, or well-documented repository to clear requirements, trustworthy project understanding, evidence-backed issue analysis, technical choices, and small verifiable delivery slices.
metadata:
  short-description: Understand projects and deliver one verified feature slice at a time
---

# Project Understanding and Sliced Delivery

Use this skill when taking over a software project, clarifying an unclear request, reorganizing weak project documentation, auditing implementation gaps, researching technical options, or delivering a feature incrementally. It is designed to work when the repository has no project documents, partial documents, or an established documentation system.

The skill defines a working method, not a product architecture. Adapt names, files, tools, and test commands to the repository and the user's constraints.

## Operating Contract

- Start from the repository and the user's goal. Do not assume that expected documents exist.
- Separate **what the product should be**, **what the code is now**, and **what this slice will change**.
- Keep discovery, solution design, implementation, and review distinct enough that a new finding does not silently expand the current slice.
- Prefer one small, observable vertical slice across the relevant layers over a batch of layer-specific work.
- Treat a claim as unverified until a real entry point, meaningful test, or reproducible inspection supports it.
- Report results, process, limitations, and remaining work in plain language.
- Preserve user changes, secrets, local configuration, runtime data, logs, caches, and generated evidence unless the user explicitly asks otherwise.

## Choose the Starting Mode

Before planning implementation, classify the repository:

1. **Empty or almost empty**: create a minimal project map and a draft product contract from the user's stated goal. Do not invent a large architecture. Mark assumptions and questions.
2. **Partially documented**: identify authoritative documents, reconcile contradictions, and fill only the missing durable sections. Keep historical reports and temporary evidence out of the core documentation.
3. **Well documented**: read the repository rules and current contract first, then audit the relevant code and select one planned slice. Do not rewrite stable specifications to make an existing bug appear acceptable.

Read [references/operating-modes.md](references/operating-modes.md) when the starting state is unclear or the repository lacks durable project records.

## First Conversation and Discovery

At takeover, produce a short working brief before changing code:

- the user's desired outcome, audience, and constraints;
- the repository's current shape, entry points, runtime, dependencies, and likely source of truth;
- the main user-visible flow in plain language;
- what is known, inferred, contradictory, or not yet checked;
- the questions whose answers would change scope or design.

Explore proportionally. For a small task, read the relevant entry points and callers. For a large or unclear project, build a map of top-level directories, package manifests, startup commands, public interfaces, persistence, external integrations, tests, and documentation before deep reading. Use search and structured parsers where available; do not claim that a filename scan proves behavior.

If requirements are unclear, ask focused questions that resolve decisions: user, trigger, input, output, success condition, failure behavior, permissions, persistence, and non-goals. When the user cannot answer immediately, record assumptions visibly and continue only where the assumptions do not create irreversible scope.

## Durable Project Records

Create or repair only the records that the repository needs:

- `AGENTS.md`: durable repository rules, reading order, safety boundaries, validation commands, and delivery protocol. Never use it as a diary or current status report.
- A stable project contract: product goal, actors, main flows, component responsibilities, input/output/state/error contracts, constraints, and acceptance principles.
- A current-state record: evidence-backed implementation gaps, risks, redundancy, pseudo-implementations, and unverified capabilities.
- A next-slice plan: the highest-priority small slice, its boundary, acceptance checks, exclusions, and likely follow-up.
- ADRs or an equivalent decision log for consequential technical choices. One decision per record; capture context, alternatives, decision, consequences, confidence, and revisit triggers. Supersede a changed decision instead of rewriting history.

Use the repository's existing names when they are clear. Otherwise use the names above or an equivalent local convention. Read [references/artifacts-and-templates.md](references/artifacts-and-templates.md) for plain-language structures and templates.

## Problem and Evidence Discipline

For each relevant module or file, classify findings as implemented, partial, missing, pseudo-implemented, redundant, risky, or unverified. Tie the finding to a project requirement and a code or runtime observation. Keep these claims separate:

- code exists vs. the user flow works;
- a request was accepted vs. work completed;
- a response was returned vs. an artifact was written and checked;
- a test passed vs. the real entry point and failure path were exercised;
- a citation or identifier is present vs. the content is actually supported;
- a framework can provide a capability vs. this project has integrated and configured it.

Do not delete code, tests, or documents merely because they look similar. Before removal, identify consumers, unique behavior, migration or compatibility needs, and a concrete exit condition. When a useful rule is duplicated, extract it only after confirming semantic equivalence and wiring all existing consumers to the shared implementation.

## Research and Technical Choices

Research mature public projects or official documentation when a dependency, protocol, or technique may replace custom code or materially affect the design. For each candidate record:

- capability relevant to this requirement;
- what existing responsibility it could replace;
- integration boundary and project-owned rules;
- dependency, version, license, deployment, and maintenance cost;
- failure, retry, persistence, and observability semantics;
- smallest isolated proof that would justify adoption;
- exit or rollback plan.

Do not add a complete platform when a narrow library or local implementation is enough. Do not keep two production paths solely because both prototypes work. Read [references/technical-research.md](references/technical-research.md) when evaluating public projects or framework adoption.

## One Slice at a Time

Before implementation, write a slice brief containing:

- requirement and problem identifiers;
- current behavior and target behavior;
- user-visible value or observable system outcome;
- allowed files/components;
- explicit exclusions;
- normal, failure, retry, restart, duplicate, and permission checks appropriate to the risk;
- evidence that will make the result understandable to a non-specialist.

Prefer a vertical slice that crosses the necessary interface, domain, persistence, and presentation boundaries. Keep it small enough to finish, inspect, and explain in one cycle. Do not implement every related gap because it was discovered during review.

Implementation must preserve authoritative state, explicit ownership, idempotency where side effects can repeat, and truthful artifact/status reporting. A notification, cache, mock, fixture, UI guess, or manually edited state must not be treated as the underlying business fact.

Read [references/verification-and-slicing.md](references/verification-and-slicing.md) for slice sizing and process/result verification.

## Finish the Slice

Complete the same loop before choosing another slice:

1. Implement only the agreed boundary.
2. Exercise the real supported entry point for the normal path.
3. Exercise the most relevant failure, interruption, duplicate, restart, and recovery paths.
4. Review whether the result depended on a hidden shortcut, manual state, an unconfigured service, or an unrealistic test helper.
5. Check for redundant paths, dead documentation, accidental secret/runtime files, and unrelated changes.
6. Update the current-state record, next-slice plan, and any decision record.
7. Re-read changed files and inspect the actual diff and staged scope.
8. Commit or publish only when the user's authorization and repository rules allow it.
9. Report in plain language: what changed, what can now be observed, what was verified, what was not verified, and the single best next slice.

If verification fails, record the failure and keep the slice open. Do not downgrade acceptance criteria, delete a failing test, or describe a substitute demonstration as production capability.

## Plain-Language Reporting

Lead with the result a user can understand. For each issue or slice, use this order:

1. Simple statement of the problem or outcome.
2. What the system does now.
3. What it should do.
4. Why the difference matters.
5. Evidence and affected location.
6. Proposed change or completed change.
7. Limits, skipped checks, and next step.

Explain a technical term when first used. Prefer a small table or flow diagram when it reduces ambiguity. Do not inflate certainty with words such as "complete", "guaranteed", or "zero errors" without matching evidence.
