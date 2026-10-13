# Agent Development Rules

This file defines how future AI agents work in this repository. During installation, adapt paths and language to local conventions and remove installer instructions. The remaining rules must work without calling the setup skill again. Keep current status and task diaries in the appropriate records, not in this file.

## Reading order

1. Read this file.
2. Read `docs/project-spec.md`: stable goals, responsibilities, inputs/outputs, state, exceptions, constraints, and acceptance principles.
3. Read the relevant sections of `docs/current-state.md`: evidence-backed findings and remaining limits.
4. Read `docs/next-stage-plan.md`: the current bounded plan, if the user has agreed one.
5. Use `docs/templates/adr.md`, `docs/templates/technical-research.md`, and `docs/templates/handoff.md` when a real decision, comparison, or handoff warrants a record. Read actual accepted records before changing their decisions.

Installer: replace these links with existing equivalent paths when appropriate. Empty template sections are pending, not confirmed requirements or executable instructions. On a new requirement, clarify and fill only the relevant sections before using them as a contract or plan.

## Understand before changing

- Restate the user's requested outcome in plain language.
- Separate confirmed requirements, assumptions, observations, contradictions, and unknowns.
- Ask focused questions when an answer could change scope, data, safety, architecture, or acceptance.
- Diagnose the problem and its impact before proposing a fix. A discovered gap is not permission to implement it.
- Inspect the relevant entry points, consumers, configuration, and tests. Scale exploration to the task.
- Keep discovery, solution design, implementation, and acceptance as distinct stages. If the user asks only for discovery or planning, end with findings or a plan. Put newly discovered unrelated problems in current state for a future slice.
- Carry forward decisions the user has already confirmed. Ask about missing material choices; do not ask them to approve the same agreed scope again.

## Project-aware research

- Infer the concerns that matter from the actual project shape and the concrete requirement.
- Use official documentation and mature public projects when a technical question needs evidence.
- Compare fit, ownership, failure behavior, cost, license, maintenance, and exit or rollback conditions.
- Do not add a framework or specialist capability because it is popular, and do not keep duplicate production paths without an exit condition.
- Record source URLs, research date, version or commit, adoption boundary, and the smallest proof that would establish fit. Dependency availability is not proof of correct integration.

## Bounded implementation

- Work on one observable outcome at a time.
- State the allowed scope, explicit exclusions, affected ownership boundaries, and risk-based checks before coding.
- Split work according to the actual project shape, dependencies, size, and evidence needs. Do not force frontend, backend, mobile client, worker, data pipeline, or model work into one generic slice. Frontend and backend implementation and acceptance are separate stages. When end-to-end behavior is needed, add a later integration stage after each boundary has its own evidence. A backend contract may be a prerequisite for frontend work, but it does not make the two boundaries one stage.
- Use the project's own verification surface: API/worker and persistence checks for backend work, browser-visible interaction and layout/accessibility checks for frontend work, lifecycle/permission/offline/restart checks for mobile work, and the relevant real boundary for other project forms. One layer's test is not proof of another layer's behavior.
- Use enough detail to define behavior, acceptance, and ownership; avoid premature function-by-function or line-by-line tasks. Break a large outcome into independently verifiable slices, without inventing unnecessary work.
- Preserve authoritative business state. UI, cache, notification, mock, fixture, and manually edited state are not proof of the underlying fact.
- Define duplicate, retry, restart, permission, persistence, and recovery behavior when relevant.
- Keep configuration/diagnostic surfaces separate from runtime dashboards or result-reading surfaces when the product has those different jobs. A visual redesign should state its user task and evidence instead of inheriting backend terminology or raw nested data.

## Verification and handoff

- Exercise the supported real entry point when practical and label the evidence level.
- A passing unit test or mock does not prove a boundary it does not exercise.
- Distinguish code inspection, unit/contract tests, real entry-point checks, controlled failures, and user-visible checks. Record environment, fixtures, manual setup, skipped checks, and what each result proves. Zero discovered tests and unavailable environments are not passing results.
- Check the result and the process that produced it. Record what remains unverified.
- Do not bypass a gate, weaken acceptance, silently inject final state, or rely on historical success reports to manufacture a passing current result. A failed check keeps the related claim open.
- For generated content, use deterministic checks of format and required evidence first, then representative examples and semantic evaluation where needed. If using a model judge, record its rubric and limits and calibrate against human-reviewed cases; an unavailable or uncertain judge is not an automatic pass. Do not impose this on projects that do not generate such content.
- Inspect redundancy before deleting or merging code, tests, or documents; retain evidence until replacement coverage is proven.
- Report completed, proven, not proven, excluded, and next in the user's language. Preserve the established language of documents being extended.
- Explain an issue as: requested outcome, observed behavior, expected behavior, impact, evidence, proposed action, and limits. Explain necessary terms and connect reasons to actions. For visible behavior, provide a readable result or actual UI evidence when feasible.

## Records and safety

- Update the stable specification only when product intent, state meaning, ownership, or an external contract changes.
- Update current state, next-stage plan, ADR, research, or handoff records only when a real requirement, finding, decision, or completed slice justifies it.
- After each completed slice, update its current-state entries and the one next plan. Do not turn candidate follow-ups into authorization to execute a whole backlog.
- When a slice is accepted, inspect the full submitted and unsubmitted scope, update the relevant records, and commit or push safe code, public configuration, and documents when user and repository policy authorize it. Keep local configuration, secrets, test scripts, and test results out of the published scope when policy says they are local-only.
- For a high-risk or multi-boundary slice, use an independent read-only review when available and authorized. The reviewer checks evidence and scope; it does not silently implement the work.
- Keep secrets, local configuration, runtime data, private conversation material, logs, screenshots, and temporary test output out of committed project knowledge unless explicitly required.
- Preserve the repository's test and evidence policy. Reusable regression tests and temporary execution artifacts have different purposes; do not universally prohibit committing tests. Check consumers before removing old records or tests, and map unique coverage to its replacement.
- Commit or publish only within user authorization and repository policy. Inspect the actual diff and staged scope; preserve unrelated user changes.

## Language and validation conventions

- New human-readable documents, headings, table explanations, pending markers, and reports use `[the invoking user's language]`. Extend existing documents in their established language. Keep identifiers, paths, code, and commands unchanged.
- Project-specific startup and validation commands: `[confirm from repository evidence when a concrete task needs them]`. Do not invent commands during setup or claim syntax checks prove runtime behavior.
