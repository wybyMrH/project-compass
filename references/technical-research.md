# Technical Research and Adoption

Use this reference when a public project, framework, hosted service, protocol, or library may replace custom work.

## Research Record

For each candidate, write a short record:

| Question | Answer |
| --- | --- |
| What requirement does it address? | |
| What does the project already do? | |
| What responsibility could it replace? | |
| What must remain project-owned? | |
| Version, license, runtime, and deployment cost? | |
| Failure, timeout, retry, and persistence behavior? | |
| Smallest proof of value? | |
| How is it removed or rolled back? | |
| Adoption decision and confidence? | |

Prefer primary sources: official documentation, source repository, release notes, and license files. Search only as broadly as needed for the current decision. Do not present a search snippet as technical evidence.

## Minimal Proof

An isolated proof should use fixed, non-sensitive inputs and exercise the behavior that matters. It should state:

- what is real and what is a deterministic fixture;
- what environment and versions were used;
- what was measured or observed;
- what the proof does not establish;
- whether the result changes the production plan.

Do not add a dependency to production merely because a proof can run. Record indirect dependencies, licensing, configuration, and the old path's exit condition.

## Decision Questions

Before adopting a framework, ask:

1. Does it remove a real maintenance burden or only move code around?
2. Does its state and failure model match the product's required truth?
3. Can the team explain and test the boundary without relying on defaults?
4. Is the dependency proportionate to project size and deployment constraints?
5. Can the old implementation be retired, or will two production paths remain?

If the answer is uncertain, keep the candidate as a documented option and make the next slice a bounded proof rather than a broad migration.
