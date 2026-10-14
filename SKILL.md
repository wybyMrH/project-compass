---
name: project-compass
description: Install a durable AI development rule set and reusable project-document templates. Use once when preparing a repository for future agent work; fill project documents only from user-confirmed requirements and evidence, and leave them open when the product is not yet defined.
metadata:
  short-description: Install agent rules and project document templates
---

# Project Compass

Use this skill once when a repository needs a durable framework for future AI development. It installs or refreshes the repository's agent rules and the document templates that later conversations will fill.

The skill has two possible handoff states:

- **Known work**: the user has already agreed on a concrete product goal, development direction, or next feature. Fill only the relevant template sections with confirmed statements, evidence, and clearly marked assumptions.
- **Open work**: the user has not yet agreed on the product details or implementation plan. Install the rules and blank templates with prompts and `[To be confirmed]` markers. Do not invent a product contract, technology choice, current gap, next feature, or ADR.

This is a one-time setup for later agents. It does not implement features, perform a broad code audit, select a stack, or turn a repository name, chat history, README, or code shortcut into product requirements.

## Install the Framework

1. Read existing repository instructions and preserve useful local conventions. Inspect enough of the repository to find instruction files, established document paths, supported commands, and language conventions. An empty repository needs no invented architecture.
2. Create or update the repository's main agent instruction file, normally `AGENTS.md`, using [templates/AGENTS.md](templates/AGENTS.md). Preserve each operative rule while translating and adapting it; do not reduce it to a brief summary. Future agents must not need this skill again. Persist confirmed repository conventions and lasting user policies. Obey temporary task restrictions during this run, but keep one-run scope, evaluation-directory restrictions, and machine-specific tool locations out of permanent rules unless the user explicitly makes them lasting project policy.
3. Install the three main document structures and supporting blank templates described in [templates/README.md](templates/README.md). Preserve equivalent existing documents and names; update them in place without losing unique content. For a repository with no such documents, use `docs/project-spec.md`, `docs/current-state.md`, `docs/next-stage-plan.md`, and `docs/templates/` for supporting record templates. Keep the files under `docs/templates/` blank and reusable; copy one to an actual decision, research, or handoff path before filling it. These are documentation locations, never invented source paths, modules, or startup commands.
4. Assess readiness per section, not by repository emptiness: an empty repository can have confirmed requirements; an existing codebase can have unclear goals. Fill relevant sections from user-confirmed requirements or plans and directly observed facts. Put unconfirmed details in open questions. Route facts by role: lasting work rules to `AGENTS.md`, agreed behavior to the specification, observed capability and verification to current state, selected work to the plan, and this run's result to the current handoff. Leave unknowns visibly pending. For a confirmed irrelevant section, use one short not-applicable explanation instead of a block of pending fields; retain the reusable source structure for future use. Setup must not wait for product discovery.
5. Remove or archive only obsolete copies created by an earlier version of this framework after checking references and preserving historical evidence that the repository still needs. Do not delete business code or tests during this setup unless the user explicitly asks for a separate cleanup task.
6. Re-read the installed rules and templates, check links and commands, and report what was installed, filled, and still open. Check consistency across readiness, current behavior, exclusions, evidence, and next action; changing a heading alone does not refresh a record. Review which linked artifacts will actually accompany a checkout or publication. Keep source templates blank and machine-specific configuration local.

## Rules the Installed `AGENTS.md` Must Establish

The repository rules should teach every later agent to:

- begin with the user's desired outcome and explain it in plain language;
- separate confirmed requirements, assumptions, observations, contradictions, and unknowns;
- ask focused questions before settling behavior that affects scope, data, safety, architecture, or acceptance;
- read the relevant project documents and actual entry points before changing code;
- diagnose the problem and show its impact before proposing a solution; discovering a gap is not permission to fix it;
- infer project-specific concerns from the actual surfaces and runtime, then find suitable official documentation or mature public projects when a concrete technical question needs research;
- compare reuse and local implementation by fit, ownership, failure behavior, cost, licensing, and maintenance, without listing technologies as mandatory in advance;
- define one bounded, observable implementation slice at a time, with explicit exclusions and risk-based checks. Size it around a coherent result that can be independently verified: include necessary internal components, split unrelated outcomes, and avoid fragmenting the work into individual functions or files;
- split slices from the project's actual boundaries, dependencies, size, and evidence needs rather than applying a fixed recipe. Frontend and backend implementation and acceptance are separate stages; when end-to-end behavior is needed, add a later integration stage after each boundary has its own evidence. Mobile lifecycle, worker, data, and model work may need different stages of their own;
- use layer-appropriate evidence: real API/persistence/worker checks for backend work, browser interaction/layout/accessibility checks for frontend work, lifecycle/permission/offline/restart checks for mobile work, and the corresponding real boundary elsewhere;
- verify the real supported path and relevant failure, retry, restart, duplicate, permission, persistence, and read-back behavior when applicable;
- distinguish authoritative business state from UI, cache, notification, mock, fixture, or manually edited state;
- inspect redundancy before removing or merging code, documents, or tests, and retain evidence until replacement coverage is proven;
- update the appropriate stable specification, current-state record, next-stage plan, ADR, and handoff record only when a real requirement, finding, decision, or completed slice justifies the change;
- report completed, proven, not proven, excluded, and next in the user's language, while preserving the established language of documents being extended;
- maintain current state, the single next-stage plan, and the current handoff as replace-in-place snapshots. On a stage change, refresh all affected fields together and reconcile the related records; do not leave contradictory old behavior, exclusions, or verification claims. Carry forward unresolved findings and still-relevant evidence. Preserve accepted ADR history and useful regression tests;
- keep verification commands and prerequisites in one canonical project location. Reusable scripts discover tools or accept local environment/argument configuration rather than embedding one machine's paths. Durable reports include the result, environment, limits, and reproduction method; local-only screenshots or logs are optional evidence, not required links in shared documents;
- at stage completion or when temporary artifacts accumulate, inspect and clean reproducible test/run caches, disposable logs, scratch files, and build output according to repository policy. Confirm ownership and that no active process or retained evidence needs them; preserve business data, user files, secrets, useful tests, and decision history;
- after each accepted slice, refresh the relevant snapshots, inspect old paths and redundant documents/code, and commit or push safe code, public configuration, and documents when the user and repository workflow authorize it. Keep local configuration, secrets, test scripts, and test results within the repository's stated local-only policy;
- keep secrets, local configuration, runtime data, private conversation material, logs, screenshots, and temporary test output out of committed project knowledge unless explicitly required.

Existing equivalent records satisfy the framework; avoid duplicate document systems. The templates are a shared vocabulary for later work, not a claim that the project already has a goal or an implementation.

## Template Selection

Use [templates/README.md](templates/README.md) to decide which template to install. The normal set is:

- `AGENTS.md` for permanent agent rules;
- `project-spec.md`, `current-state.md`, and `next-stage-plan.md` for the three main records; install their empty structures now and fill them only when the relevant facts are available;
- `adr.md`, `technical-research.md`, and `handoff.md` as supporting templates; keep them separate from actual decision, research, and acceptance records until used.

Do not fill `project-spec.md`, `current-state.md`, `next-stage-plan.md`, `adr.md`, or `technical-research.md` with guesses. If the user has not provided the relevant content, install the empty structure and leave the questions visible.

## Language Rule

Translate the supplied template headings, explanations, table columns, example prose, and pending markers into the invoking user's language, including the still-empty sections. This also applies to new rules and the handoff. When extending an existing repository document, preserve its established language so it does not become mixed-language. Keep file paths, identifiers, code, commands, and standard technical terms as written. Record the language policy in the installed `AGENTS.md` for later agents.

## Future Development Flow

The installed rules should make the later workflow explicit:

1. Clarify the request and write a short requirement brief.
2. Read the relevant contract and inspect the relevant code and runtime boundary.
3. Record current evidence and contradictions when the task needs them.
4. Research public options only for a concrete decision; record sources and a bounded proof.
5. Agree on one small slice, its exclusions, and its acceptance evidence.
6. Implement and verify the real path, including relevant failure or recovery behavior.
7. Update only the records whose facts changed, review redundancy and security boundaries, and hand off plainly.

The initialization establishes this flow. A later user-agent conversation supplies the product details and decides which templates become authoritative.

## Validation

Before handing off, confirm:

1. The repository contains the rules and templates needed for later work, without invented product decisions.
2. Populated sections are traceable to user-confirmed requirements or repository evidence.
3. Empty sections visibly distinguish unknowns from completed work.
4. New human-readable content uses the invoking user's language; extended documents keep their established language.
5. References, paths, and commands resolve, and no private chat history, secrets, runtime data, or unrelated files were copied.
6. Core record roles and short purpose descriptions remain present, and every operative rule survives adaptation. Confirmed irrelevant sections are condensed to one explanation instead of a pending checklist; unknown applicability remains pending, never guessed. The reusable source structures stay complete. Keep small updates brief and avoid duplicating facts across documents.
7. The translated output contains no leftover explanatory prose from another language, except code, paths, identifiers, commands, and standard technical terms intentionally kept as-is.
8. Permanent rules contain no one-run restrictions or private tool paths; specifications contain no implementation progress or test results. Related snapshots agree, shared links work without ignored local artifacts, and tool prerequisites can be supplied without editing reusable scripts.

Do not claim that a product is understood, a feature is planned, or a technology is selected merely because the framework was installed.

When changing this skill, run the official validator and independently exercise [references/validation-cases.md](references/validation-cases.md). Keep test workspaces outside the skill repository.
