# Project Compass

An open-source Codex skill that installs durable AI development rules and reusable project-document templates into a repository.

It establishes how future agents:

- clarify the user's goal before deciding product behavior;
- distinguish confirmed requirements, assumptions, evidence, and unknowns;
- read the relevant project and code boundaries;
- find and evaluate public technical references when a real question requires them;
- plan and implement one bounded, observable slice at a time;
- verify both the result and the process that produced it;
- keep stable specifications, current findings, next plans, decisions, research, and handoffs separate;
- explain the work in language the user can follow.

Project Compass is a one-time setup. It does not implement a feature, choose a framework, or invent a product from an empty folder. It installs the workflow and blank structures. When the user has already agreed on requirements or a plan, the agent fills only the supported sections; otherwise the sections remain visibly pending for later conversations.

## Installed framework

The main output is a repository `AGENTS.md` plus the three primary records:

- `docs/project-spec.md`: stable product and technical contract;
- `docs/current-state.md`: evidence-backed findings for a real task;
- `docs/next-stage-plan.md`: one agreed, bounded next slice.

Supporting templates for ADRs, technical research, and handoffs are kept separate from actual records until they are needed. Equivalent existing documents should be preserved and reused.

The generated human-readable documents use the invoking user's language. Existing documents keep their established language when extended.

## Use

Install the skill in the Codex skills directory and invoke `$project-compass` once when preparing or refreshing a repository's agent workflow. It is not intended for every feature implementation.

## License

MIT. See [LICENSE](LICENSE).
