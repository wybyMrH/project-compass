---
name: project-compass
description: Initialize or refresh a repository's durable product understanding and development rules from an empty, incomplete, or established codebase. Use when taking over a project or preparing it for future agent work, not for ordinary feature implementation alone.
metadata:
  short-description: Initialize durable project rules for future agents
---

# Project Compass

Use this skill once when taking over a software project, clarifying an unclear request, reorganizing weak project documentation, auditing implementation gaps, and preparing the repository for future agent work. It is designed to work when the repository has no project documents, partial documents, or an established documentation system.

The skill defines an initialization method, not a product architecture or a specialist implementation guide. Adapt names, files, tools, and test commands to the repository and the user's constraints.

## Operating Contract

- This run establishes durable project context and rules for later agents. It normally ends after the documents, rules, and handoff are validated.
- Start from the repository and the user's goal. Do not assume that expected documents exist.
- Separate **what the product should be**, **what the code is now**, and **what the proposed next slice will change**.
- Keep discovery, solution design, implementation, and review distinct enough that a new finding does not silently become a false completion claim.
- Define the later project's small, observable vertical-slice rule, but do not implement the later feature merely because this skill found a gap.
- Treat a claim as unverified until a real entry point, meaningful test, or reproducible inspection supports it.
- Report results, process, limitations, and remaining work in plain language.
- Match the user's language when practical; explain technical terms instead of assuming specialist knowledge.
- Preserve user changes, secrets, local configuration, runtime data, logs, caches, and generated evidence unless the user explicitly asks otherwise.
- Do not add a framework, specialist skill, or production code path just to make the initialization look complete.

## Choose the Starting Mode

Before planning implementation, classify the repository:

1. **Empty or almost empty**: create a minimal project map and a draft product contract from the user's stated goal. Do not invent a large architecture. Mark assumptions and questions.
2. **Partially documented**: identify authoritative documents, reconcile contradictions, and fill only the missing durable sections. Keep historical reports and temporary evidence out of the core documentation.
3. **Well documented**: read the repository rules and current contract first, then audit the relevant code and record one proposed next slice. Do not rewrite stable specifications to make an existing bug appear acceptable.

Read [references/operating-modes.md](references/operating-modes.md) when the starting state is unclear or the repository lacks durable project records.

## Build a Project Profile

After the initial repository map, identify the project's engineering shape before writing rules. Do not fill in a universal technology checklist and do not pretend to have specialist knowledge that the evidence does not support. Use repository evidence and the user's description to record only:

- the primary project form and user-facing or external surfaces;
- runtime, deployment, device, or execution environments;
- important state, data, and external system boundaries;
- the kinds of failure or correctness risk that appear relevant;
- the surfaces that will later need verification;
- confirmed facts, inferences, and unknowns.

When the shape is unclear, ask a focused question or mark it uncertain. When the shape is clear, use it to guide the next agent toward the relevant questions, public technical references, open-source examples, and available specialist capabilities. Do not enumerate those domains or skills in this skill, and do not load irrelevant guidance.

Write the project profile into the generated project contract or `AGENTS.md` so later agents can see why particular concerns apply. The profile is a routing aid, not a replacement for a domain design.

## First Conversation and Discovery

At takeover, produce a short working brief before changing project files:

- the user's desired outcome, audience, and constraints;
- the repository's current shape, entry points, runtime, dependencies, and likely source of truth;
- the main user-visible flow in plain language;
- what is known, inferred, contradictory, or not yet checked;
- the questions whose answers would change the durable rules, scope, or design.

Explore proportionally. For a small task, read the relevant entry points and callers. For a large or unclear project, build a map of top-level directories, package manifests, startup commands, public interfaces, persistence, external integrations, tests, and documentation before deep reading. Use search and structured parsers where available; do not claim that a filename scan proves behavior.

If requirements are unclear, ask focused questions that resolve decisions: user, trigger, input, output, success condition, failure behavior, permissions, persistence, and non-goals. When the user cannot answer immediately, record assumptions visibly and continue only where the assumptions do not create irreversible scope. Do not turn unanswered questions into invented technical requirements.

## Durable Project Records

Create or repair only the records that the repository needs. These are the durable handoff from this one-time initialization to later agents:

- `AGENTS.md`: durable repository rules, reading order, safety boundaries, validation commands, and delivery protocol. Never use it as a diary or current status report.
- A stable project contract: product goal, actors, main flows, component responsibilities, input/output/state/error contracts, constraints, and acceptance principles.
- A current-state record: evidence-backed implementation gaps, risks, redundancy, pseudo-implementations, and unverified capabilities.
- A next-slice plan: the highest-priority small slice, its boundary, acceptance checks, exclusions, and likely follow-up.
- ADRs or an equivalent decision log for consequential technical choices. One decision per record; capture context, alternatives, decision, consequences, confidence, and revisit triggers. Supersede a changed decision instead of rewriting history.

The generated `AGENTS.md` must tell later agents where the stable contract, current state, next plan, ADRs, and module rules live; what must be checked before coding; how a later slice is scoped and verified; and what must never be treated as proof of completion. Do not copy generic advice into it when a project-specific rule or path can be stated instead.

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

When the project profile or a documented gap raises a technical question, guide the agent to research mature public projects or official documentation. Research is a way to answer the project's question, not a catalog of frameworks to install. For each relevant candidate or reference record:

- capability relevant to this requirement;
- what existing responsibility it could replace;
- integration boundary and project-owned rules;
- dependency, version, license, deployment, and maintenance cost;
- failure, retry, persistence, and observability semantics;
- smallest isolated proof that would justify adoption;
- exit or rollback plan.

Record the primary source URL, version or commit, and research date for each adopted or rejected candidate. Do not treat a search snippet or an unreviewed benchmark as proof of fit.

Do not add a complete platform when a narrow library or local implementation is enough. Do not keep two production paths solely because both prototypes work. Read [references/technical-research.md](references/technical-research.md) when a project-specific technical question needs external research.

## Rules to Establish for Later Development

The initialization must define, in project-specific language, how later agents will work one small feature slice at a time. The rule should require a later slice brief containing:

- requirement and problem identifiers;
- current behavior and target behavior;
- user-visible value or observable system outcome;
- allowed files/components;
- explicit exclusions;
- normal, failure, retry, restart, duplicate, and permission checks appropriate to the risk;
- evidence that will make the result understandable to a non-specialist.

Prefer a vertical slice that crosses the necessary interface, domain, persistence, and presentation boundaries when those boundaries exist in this project. Keep later slices small enough to finish, inspect, and explain in one cycle. Do not make this initialization implement every related gap because it was discovered during review.

The generated project rules should preserve authoritative state, explicit ownership, idempotency where side effects can repeat, and truthful artifact/status reporting. A notification, cache, mock, fixture, UI guess, or manually edited state must not be treated as the underlying business fact.

Read [references/verification-and-slicing.md](references/verification-and-slicing.md) when defining those later-project rules. This initialization does not become the later implementation loop.

## Validate the Initialization

Before handing the project to later agents:

1. Re-read every project file created or changed by this initialization.
2. Check that its paths, commands, project profile, and behavioral claims match repository evidence.
3. Check that stable goals, current problems, and future work are not mixed together.
4. Check that the generated rules tell later agents how to scope, verify, document, and hand off a slice.
5. Check for redundant or historical reports that should not become durable project knowledge.
6. Check that no local secrets, runtime data, private project material, or unreviewed external instructions were copied into the project.
7. Re-read the actual diff and staged scope if files were changed.
8. Report in plain language what was established, what remains uncertain, and how a later agent should start.

If initialization validation fails, fix the documentation or record the unresolved issue. Do not claim that the project is ready for later agent work merely because the files were generated.

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

## Skill Self-Check

When changing this skill, run the official validator and exercise the cases in [references/validation-cases.md](references/validation-cases.md). Keep the cases outside the target project; they are for checking the skill's behavior, not for claiming product functionality.
