# Project Document Templates

Install these structures during setup, reusing equivalent repository documents. They are structures, not completed project knowledge. Keep source and runtime paths unknown until they actually exist or the user confirms a design.

## What each template is for

- `AGENTS.md` is the permanent operating rulebook. It explains how later agents clarify, research, split, implement, verify, clean up, and hand off work. It is not a product status report.
- `project-spec.md` is the stable agreement about what the product should do and what each boundary owns. It changes slowly and only when confirmed product intent or a public contract changes.
- `current-state.md` is the evidence ledger for a real task. It explains what the code does now, where it differs from the agreed behavior, and what remains unverified. It is not a backlog of guesses.
- `next-stage-plan.md` is the short execution plan for one agreed slice. It defines the observable result, limits, checks, dependencies, and completion gate. It is not permission to execute every follow-up.
- `adr.md` records one consequential decision, its alternatives, consequences, confidence, and revisit trigger. It is not a place to make an unconfirmed preference look final.
- `technical-research.md` records a concrete comparison of public options and the smallest proof needed to judge fit. It is not a technology catalog.
- `handoff.md` makes the result readable: what changed, what proves it, what is still unknown, what was excluded, and what comes next.

## Recommended use

1. Always install or update `AGENTS.md` so later agents know the workflow.
2. Install `project-spec.md`, `current-state.md`, and `next-stage-plan.md` as the three main records. Mark them as unfilled templates unless confirmed requirements, directly inspected evidence, or a user-agreed plan is available for that section. A brief product idea does not supply an architecture, a finding, or a selected slice.
3. Install `adr.md`, `technical-research.md`, and `handoff.md` under a documentation template directory, separate from actual decision or completion records. Keep these source templates blank. Fill a copied record only for a real decision, concrete comparison, or handoff.
4. Map each role to the actual installed or existing document path in `AGENTS.md`. Do not link to a path that was never created. Use relative repository paths so the framework is portable.
5. Keep placeholders visibly unfilled. Do not create issue IDs, feature backlogs, recommended stacks, or speculative ADRs simply to fill the structures.
6. Keep current state, the next-stage plan, and the current handoff as replace-in-place snapshots, updating only what changed. Carry forward unresolved findings and useful evidence; keep accepted ADR history separately. Do not accumulate a new stage report for every update.
7. Keep source structures reusable, but make filled records proportional to the task. Unknown sections stay pending; confirmed irrelevant sections use one short explanation. Do not duplicate unused handoff sections or generated-output evaluation checklists in ordinary CRUD plans. Keep commands in one canonical location rather than repeating them across every record.
8. After a stage change, reconcile all affected fields and related records. Keep product agreements in the specification, observed progress/evidence in current state, and selected work in the plan. Temporary task restrictions remain effective for the run but are not permanent project policy unless explicitly designated.

Translate headings, section descriptions, pending markers, and prose into the invoking user's language when materializing a template. Check the final document for leftover explanatory sentences in the source language. Keep identifiers and filenames stable where the repository depends on them.

## Project-shaped slicing

The templates do not assume that every repository uses the same layers or the same number of stages. During a real requirement conversation, identify the actual boundaries, dependencies, size, and evidence needs, then split the plan accordingly. Frontend and backend implementation and acceptance are separate stages; if end-to-end behavior matters, add a later integration stage after both have their own evidence. A web product may need a backend contract and persistence slice before a separate frontend design and browser-validation slice; an Android project may need a local state/lifecycle slice before scanner or notification UI; a worker or data pipeline may need its own recovery and artifact checks. Record why the split exists and the evidence that each slice can be understood on its own.

Choose a coherent independently verifiable result. Necessary internal components can belong together; unrelated outcomes and distinct acceptance responsibilities should be separated. Neither a whole subsystem nor a single function is the default stage size. At stage boundaries, inspect and clean reproducible temporary test/run artifacts while retaining required evidence and useful regression coverage.

Do not fill placeholders from a repository name, generic assumptions, a copied example, or an unreviewed chat transcript.
