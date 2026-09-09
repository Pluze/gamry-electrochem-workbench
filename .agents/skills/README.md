# Repository Skills

Each Skill owns one LabKit workflow. `SKILL.md` contains its discriminating
trigger, core decisions, and completion conditions. Conditional procedures live
in linked `references/`; repeatable operations live in `scripts/`. UI metadata
in `agents/openai.yaml` describes the same scope, including default delivery.
Supporting Skills inherit the requesting task's mode and authorization.

Install the governance tooling with `python3 -m pip install -r .github/requirements.txt`
in a development environment, then run
`python3 .github/scripts/validate_agent_skills.py` and its unit tests.
PyYAML is a development/CI dependency only. The parser accepts standard YAML,
including reordered/multiline fields and supported optional metadata; LabKit
additionally requires UI name, short description, and invocation prompt.

The validator checks entrypoints, names, YAML semantics, local links and Skill
routes in entrypoints/references, reachable references, activation/behavior
scenario structure, and repository AGENTS chains against Codex's default
32 KiB budget. It includes intermediate scopes and override precedence, but
does not measure user-global instructions or custom host fallback settings.
Generated artifacts and independent private workspaces are outside this catalog.

`evals.json` supplies meaningful positive/negative activation examples;
`activation-evals.json` covers neighboring-workflow collisions.
`behavior-evals.json` records expected task outcomes and unwanted actions.
These are fixtures for review, not evidence that a model passed. Use the
[governance evaluation procedure](labkit-agent-governance/references/evaluation.md)
for independent trials. Structural checks cannot establish activation accuracy,
scientific judgment, correct authorization, or successful completion.
