# Next Stage Plan

Fill this after a requirement and priority are agreed. Keep one current plan and replace its contents when the agreed next stage changes; do not append completed stage reports or create a numbered series of plans. Candidate follow-ups are not promises. If no next stage is agreed, leave that status explicit.

Document readiness: `[unfilled template / proposed / agreed]`. Until a real plan is available, every section stays pending and no feature is selected.

## Selected slice

Describe one coherent outcome that can be independently built, checked, and explained. Include necessary internal components; for example, a backend result may require an API, domain logic, and persistence together. Split unrelated outcomes or distinct acceptance responsibilities, while avoiding separate stages for each function, file, or technical step. If the project has separate backend and frontend boundaries, keep their implementation and acceptance in separate stages; record a later integration stage only when end-to-end proof is required.

- ID and requirement: `[To be confirmed]`
- Observable user or system outcome: `[To be confirmed]`
- Current behavior: `[To be confirmed]`
- Target behavior: `[To be confirmed]`
- Allowed files, modules, or boundaries: `[To be confirmed]`
- Explicit exclusions: `[To be confirmed]`
- Boundary owned by this stage and reason for the split: `[To be confirmed]`
- Prerequisite stage and handoff contract: `[Not applicable / To be confirmed]`
- Why this stage is neither too large nor fragmented: `[coherent outcome, necessary components, dependencies, and independent acceptance; To be confirmed]`

## Acceptance and evidence

Choose checks that match the boundary. API and persistence work needs real request/state evidence; frontend work needs browser-visible interaction and layout checks; mobile work may need lifecycle, permission, offline, and restart checks. Do not mark one layer proven because another layer's check passed.

- Normal path: `[To be confirmed]`
- Relevant failure or cancellation: `[To be confirmed]`
- Duplicate, retry, restart, permission, or recovery checks: `[To be confirmed]`
- Evidence a non-specialist can inspect: `[To be confirmed]`
- Evidence level and limits: `[To be confirmed]`

### Generated-output evaluation (when applicable)

Use this only for work that produces content whose meaning or evidence must be judged. Deterministic validation and semantic quality are different claims; a model judge does not replace human calibration or the underlying evidence.

- Deterministic format, contract, and evidence checks: `[Not applicable / To be confirmed]`
- Representative fixed dataset or examples: `[Not applicable / To be confirmed]`
- Semantic evaluation, model judge, and human calibration: `[Not applicable / To be confirmed]`
- What an unavailable, invalid, conflicting, or uncertain evaluation means: `[To be confirmed]`

## Dependencies and decisions

List decisions that must be made before this slice and the public or project-specific evidence needed. Do not smuggle an unapproved framework or design into this section.

- Required user decisions: `[To be confirmed]`
- Technical research or ADR prerequisites: `[To be confirmed]`
- Security, data, or migration risks: `[To be confirmed]`

## Completion and fallback

Define what counts as complete, what remains open, and how to stop or roll back if the evidence fails. A commit or a passing mock is not a completion gate by itself.

- Artifacts and observable results to deliver: `[To be confirmed]`
- Criteria for calling this slice complete: `[To be confirmed]`
- Current snapshots to replace or refresh, and fallback or rollback boundary: `[To be confirmed]`
- Disposable test/run artifacts to inspect and clean after verification: `[Not applicable / To be confirmed]`

## Follow-up candidates

List possible later work without choosing it for the user. Frontend work that follows a backend stage must name its own design, interaction, and browser-validation scope; backend acceptance does not close the frontend stage.

- `[Candidate only; not a promise]`
