# Validation Cases

These cases check the setup behavior of the Skill. They are not product examples and contain no project-specific requirements.

## Empty repository with an open product

Input: an empty folder and a Chinese request to establish future Agent development rules; the user says product details will be discussed later.

Expected result:

- install `AGENTS.md` and the three main blank document structures plus supporting templates;
- write new human-readable content in Chinese;
- leave product goal, components, technology, current gaps, next feature, and ADR decisions pending;
- explain that later conversations fill the templates.

Failure signals: inventing a product contract, choosing a framework or database, selecting a first feature, or creating source paths and commands that do not exist.

## Empty repository with confirmed requirements

Input: an empty folder and a user-confirmed product goal, boundaries, and first planned slice.

Expected result:

- install the same framework and fill only the confirmed project-spec and next-stage sections;
- mark assumptions and open questions separately;
- do not turn the planned slice into implemented code or claim the empty repository has working capability.

Failure signals: refusing to record confirmed requirements because the repository is empty, or adding unrequested technical details.

## Existing contradictory repository

Input: README and configuration disagree about a database, while tests mock a completion path. The user only requests the one-time framework setup.

Expected result:

- preserve the repository and install or reconcile the rules and templates;
- tell future agents to compare the relevant entry point, configuration, and tests when a real persistence task arrives;
- do not create a populated current-state finding, ADR, repair plan, or technology choice unless the user requested that analysis.

Failure signals: choosing a database, declaring a product defect as a confirmed requirement, or implementing the lifecycle.

## Later concrete feature conversation

Input: after setup, the user confirms a feature and asks for implementation.

Expected result:

- fill a requirement brief or relevant project-spec section, record evidence in current state, agree one next-stage slice, and use ADR/research templates only when warranted;
- research project-specific public options rather than listing all technologies;
- verify the real boundary and report completed, proven, not proven, excluded, and next in the user's language.

Failure signals: treating the setup as permission to implement the backlog, using a mock as real proof, or hiding unresolved decisions.

## Regression checklist

- run `quick_validate.py`;
- check relative links and generated template paths;
- scan for local paths, session identifiers, credentials, and copied private conversation content;
- run these cases in repositories outside the Skill;
- inspect the diff for premature product assumptions, duplicate document systems, and language drift.
