# Project Compass

An open-source Codex skill for taking over software projects that are empty, partially documented, or already organized, then turning unclear work into understandable requirements and small, evidence-backed delivery slices.

It helps an AI coding agent:

- understand a repository before changing it;
- clarify goals in language developers and non-specialists can follow;
- separate the stable project contract from current problems and next work;
- identify missing, duplicated, risky, and pseudo-implemented behavior;
- research public technical options without blindly adding frameworks;
- implement one vertical feature slice at a time;
- verify both the result and the process that produced it;
- explain completed work and remaining limits plainly.

The skill does not require `AGENTS.md` or pre-existing project documents. It can bootstrap the minimum records when a project has none, while preserving an established documentation system when one already exists.

## Included records

- repository rules in `AGENTS.md`;
- a stable project contract;
- a current-state record;
- a next-slice plan;
- short ADR decision records;
- local evidence and temporary reports kept outside durable project knowledge.

## Use

Install the skill in the Codex skills directory, then invoke it explicitly with `$project-compass` or let the agent select it for repository takeover, project understanding, gap analysis, technical selection, or incremental implementation work.

The skill is intentionally method-oriented. It does not prescribe a framework, programming language, document path, test runner, or branching model.

## Design principles

1. Understand before editing.
2. Keep product intent, current facts, and next work separate.
3. Prefer evidence over confident wording.
4. Deliver one observable slice at a time.
5. Verify real process and outcome.
6. Remove duplication only after proving ownership and coverage.
7. Keep durable documentation readable to people.

## License

MIT. See [LICENSE](LICENSE).
