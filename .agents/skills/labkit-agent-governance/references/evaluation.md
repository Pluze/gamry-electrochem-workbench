# Evaluating agent guidance

Use the current official [Skills guide](https://learn.chatgpt.com/docs/build-skills),
[AGENTS discovery guide](https://learn.chatgpt.com/docs/agent-configuration/agents-md),
and, for model-specific changes, the requested model's
[official guidance](https://developers.openai.com/api/docs/guides/latest-model).
Fetch the current pages; do not infer a model-specific recommendation from age
or file length alone. Separate official requirements from repository conventions.

Keep positive and negative activation cases that distinguish neighboring jobs.
A mistaken proposed method can still belong to the Skill that corrects it;
activation means ownership, not endorsement. Cross-Skill cases describe genuine
collisions without requiring every possible combination. Include natural user
wording rather than encoding the intended procedure in every prompt.

For material behavior changes, evaluate task outcomes as well as selection:
review stays read-only, existing tests are reused, authorized replacements do
not accumulate wrappers, and PR delivery stops at the requested state. Use an
independent forward pass when available and authorized; provide the task,
instructions, and raw fixtures without the expected answer. Keep side effects
in a temporary workspace and simulate external actions unless authorized.
Record model, cases, observed results, and limits separately from static checks.

Keep durable expectations in `behavior-evals.json`; they are review scenarios,
not assertions that a model has passed. Prefer a few discriminating cases over
wording/heading checks. Report selection accuracy separately from completion,
unnecessary actions, unintended writes, and unnecessary clarification. Only
claim measured improvements supported by comparable before/after evidence.
