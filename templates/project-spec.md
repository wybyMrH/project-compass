# Stable Project Specification

## Status

This section says whether the contract is a blank scaffold, partly agreed, or stable enough to guide implementation. It prevents a template from being mistaken for a finished product definition.

- Document readiness: `[unfilled template / partly confirmed / confirmed]`
- Confirmation source: `[user request, agreed plan, or established authoritative document; no private transcript copy]`
- Version: `[To be confirmed]`
- Last reviewed: `[To be confirmed]`
- Owner or decision authority: `[To be confirmed]`

## Goal and users

Describe who needs what and what success looks like. Do not fill this from a project name or a generic industry assumption.

- User and context: `[To be confirmed]`
- Problem to solve: `[To be confirmed]`
- Successful user-visible outcome: `[To be confirmed]`

## Main flows

Describe the user or system journey from input to observable result. Keep implementation tasks and temporary bugs out of this stable section.

1. Trigger and input: `[To be confirmed]`
2. Important processing and decisions: `[To be confirmed]`
3. Stored facts and state changes: `[To be confirmed]`
4. Output or artifact the user can inspect: `[To be confirmed]`

## Requirements and project shape

Capture only confirmed project characteristics and boundaries. This is where a later agent can record whether work crosses a browser, API, mobile lifecycle, worker, data, or other surface; it is not a list of frameworks or a fixed slicing recipe. Later plans should use these actual boundaries, dependencies, size, and evidence needs to decide their stages.

| Requirement | Confirmed behavior | Relevant boundary or environment | Acceptance principle |
| --- | --- | --- | --- |
| `[To be confirmed]` | `[To be confirmed]` | `[To be confirmed]` | `[To be confirmed]` |

Record only confirmed project characteristics. Inferences about platform, state, devices, or external systems belong in open questions until checked; do not impose layers or a stack that the project does not need.

## Components and ownership

Make responsibility boundaries visible so later slices do not make two components own the same fact. Keep rows at behavior and boundary level rather than designing every function.

| Component or boundary | Owns | Receives | Produces | Must not do |
| --- | --- | --- | --- | --- |
| `[To be confirmed]` | `[To be confirmed]` | `[To be confirmed]` | `[To be confirmed]` | `[To be confirmed]` |

## Input, output, state, and error rules

Define the facts, transitions, failures, retries, permissions, and artifacts that must remain truthful. These rules guide both implementation and verification.

- Inputs and validation: `[To be confirmed]`
- Outputs and artifacts: `[To be confirmed]`
- Authoritative state and ownership: `[To be confirmed]`
- Error, timeout, retry, duplicate, restart, and permission behavior: `[To be confirmed]`
- Security, privacy, performance, and cost constraints: `[To be confirmed]`

## Technical concerns and candidate boundaries

Use this section to record technical questions that follow from confirmed requirements. It is not a stack selection or a list of mandatory frameworks.

- Relevant runtime, device, deployment, or execution surfaces: `[To be confirmed]`
- Data, state, external-system, and permission boundaries: `[To be confirmed]`
- Technical questions that need public research: `[To be confirmed]`
- Candidate options and their ownership boundaries: `[To be confirmed]`
- Decisions already accepted and their ADRs: `[To be confirmed]`

## Acceptance principles

State what a user or supported system boundary must be able to observe. A test command alone is not an acceptance principle.

- `[To be confirmed]`

## Non-goals

Record boundaries that prevent scope from expanding silently. Add items only when they are agreed or clearly excluded by the request.

- `[To be confirmed]`

## Open questions

- `[Unconfirmed product behavior, environment, or material decision]`

## Change rule

Keep this document stable. Change it only when confirmed product intent, state meaning, component responsibility, or an external contract changes. Put current defects and future implementation work in their own records.
