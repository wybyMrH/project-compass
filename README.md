# Project Compass

An open-source Codex skill for the one-time initialization of software projects that are empty, partially documented, or already organized. It turns unclear requirements and repository facts into durable project rules that future agents can use.

It helps an AI coding agent:

- understand a repository before changing it;
- clarify goals in language developers and non-specialists can follow;
- separate the stable project contract from current problems and next work;
- identify missing, duplicated, risky, and pseudo-implemented behavior;
- research public technical options without blindly adding frameworks;
- define how future agents implement one vertical feature slice at a time;
- define how future agents verify both the result and the process that produced it;
- leave a plain-language handoff with remaining limits and unknowns.

The skill does not require `AGENTS.md` or pre-existing project documents. It can bootstrap the minimum records when a project has none, while preserving an established documentation system when one already exists.

## Included records

- repository rules in `AGENTS.md`;
- a stable project contract;
- a current-state record;
- a next-slice plan;
- short ADR decision records;
- local evidence and temporary reports kept outside durable project knowledge.

## Use

Install the skill in the Codex skills directory, then invoke it explicitly with `$project-compass` for the first serious takeover of a repository, or when its durable agent documentation needs to be reconciled. It is not intended to be loaded for every ordinary feature implementation.

The skill is intentionally method-oriented. It does not prescribe a framework, programming language, document path, test runner, branching model, or specialist discipline. It asks the initializing agent to infer the project's shape and investigate only the technical concerns that the project actually raises.

## Design principles

1. Understand before editing.
2. Keep product intent, current facts, and next work separate.
3. Prefer evidence over confident wording.
4. Define and later deliver one observable slice at a time.
5. Verify real process and outcome.
6. Remove duplication only after proving ownership and coverage.
7. Keep durable documentation readable to people.

## License

MIT. See [LICENSE](LICENSE).
