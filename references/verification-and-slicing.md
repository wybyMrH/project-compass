# Slicing and Verification

## Slice Shape

A useful slice has one observable outcome and a bounded owner. It may cross several layers, but it should not combine unrelated product behavior, platform migration, broad cleanup, and new infrastructure.

Good slice examples:

- accept one request, persist its authoritative state, and show its real completion;
- consume one completed upstream result once, then persist a report;
- parse one supported document type and expose evidence-linked facts;
- apply one mastery rule and unlock one next step.

Avoid slices such as "rewrite all persistence", "finish the whole workflow", or "add every quality check".

## Process and Result Checks

For normal-risk backend or workflow changes, choose checks from this list:

- real supported entry point;
- success and expected failure;
- duplicate request or notification;
- restart or resume after a meaningful boundary;
- cancellation or timeout when applicable;
- authoritative state versus UI/cache/notification projection;
- artifact declaration, write, and physical read-back;
- permissions, redaction, and path ownership;
- absence of manual database edits or test-only state injection;
- no extra external side effect on recovery.

Not every slice needs every check. Explain which were selected and why. A fixture may isolate a provider or remote host, but it must not fake the behavior that the slice claims to deliver.

## Evidence Levels

Use explicit labels:

- `static`: source or configuration inspection;
- `unit`: focused behavior without the real boundary;
- `contract`: public shape and state transition;
- `real-entry`: supported CLI, HTTP, UI, or worker path;
- `failure-injected`: controlled interruption or dependency failure;
- `browser-visible`: a user can inspect the result through the interface;
- `not-verified`: no meaningful evidence yet.

State the environment, fixture, and limitations. "All tests passed" is not a substitute for the evidence level of the user flow.

## Completion Gate

Before calling a slice complete, confirm:

- the target behavior is observable;
- the normal path was exercised through the intended boundary;
- the most relevant failure or recovery behavior was checked;
- duplicate side effects are controlled where applicable;
- the result is not dependent on hand-written final state;
- documentation says what is still unverified;
- unrelated changes and local secrets are excluded.

If a check fails, keep the slice open or reduce the claim. Never make the report look complete by weakening the gate.
