# Starting Modes

Use this reference during the one-time takeover when project documentation is missing, contradictory, or unusually large.

## Empty or Nearly Empty Repository

First inspect the repository rather than creating a full system design:

- identify whether it is truly empty, a scaffold, or a placeholder;
- preserve existing package metadata, licenses, and user files;
- ask for or extract the smallest useful product statement;
- write a short draft contract with explicit assumptions and open questions;
- propose one demonstrable walking skeleton or research spike for a later agent;
- identify only the runtime, persistence, and interface pieces that a later agent would need for that slice.

The initialization deliverable may be a decision record, a project map, a health-check plan, or a thin end-to-end path proposal. It does not need to be a complete application, and this mode does not implement the proposed path.

## Partially Documented Repository

Find the current source of truth by comparing:

- README and setup instructions;
- package manifests and entry points;
- active code paths and public interfaces;
- recent commits or issue references, when available;
- tests that exercise real behavior;
- dated reports and generated evidence.

Mark contradictions instead of silently choosing the most convenient statement. Move durable rules into the stable contract or `AGENTS.md`; move current defects into the current-state record; keep historical evidence outside the core records unless the user explicitly needs it.

## Well Documented Repository

Do not rewrite stable documents at every turn. Read the relevant sections, inspect their code consumers, and verify the next planned slice. Change the contract only when the product goal, state meaning, component responsibility, or external contract truly changes. Record the reason and migration impact.

## Conversation Checkpoint

At the end of discovery, present a compact checkpoint before generating durable project rules:

```text
I understand the project as: <one plain-language paragraph>
The next user-visible outcome is: <one sentence>
The evidence I have is: <files, commands, or runtime observations>
The uncertain points are: <questions or assumptions>
The proposed first slice is: <scope and exclusions>
```

Ask only questions that could change the scope, safety, data contract, or acceptance result. Continue with reversible discovery while waiting for answers.

## Project-shape checkpoint

Also state, without pretending to provide specialist implementation advice:

```text
The project appears to be: <engineering shape, with confidence>
The important surfaces are: <user, device, API, CLI, worker, model, or other observed surfaces>
The concerns a later agent should investigate are: <project-specific questions>
The evidence for this routing is: <files, commands, or observations>
```

This checkpoint routes future investigation. It must not become a generic catalog of every possible software discipline.
