---
name: labkit-agent-governance
description: "Audit or maintain LabKit AGENTS.md, repository Skills, metadata, evaluations, agent scripts, and an active migration ledger. Product-code review and reader documentation use their own workflows."
---

# LabKit Agent Governance

Establish the requested mode: audit reports findings without editing; maintenance
changes the specified guidance. Read the affected entrypoints and applicable
ancestor rules. Read linked resources, metadata, evaluations, validator, or
script tests when affected or needed to resolve a concrete uncertainty.

## Assign one authority

Keep cross-cutting invariants in root rules, scoped invariants in the narrowest
applicable `AGENTS.md`, repeatable procedure in its Skill, and fragile repeatable
mechanics in its owning script. Current user behavior belongs in help/manuals;
an active retirement roadmap belongs only in `.agents/migration_guide.md`.
Search existing owners before adding guidance. Remove duplicate procedure and
retire obsolete instructions with the workflow they governed.

Distinguish an explicit durable user policy from a one-off correction. Honor the
former; promote the latter only when repeated current evidence supports a
stable rule. Write from the accepted result, not discarded proposals.

## Design for selection and execution

Descriptions name the job and discriminating trigger, with exclusions only for
likely collisions. Match the body, UI default prompt, and evaluation cases to
the same scope and delivery mode. Supporting Skills inherit the caller's mode.
Give open-ended work outcomes and decision criteria; reserve fixed sequences
for fragile operations. State inputs, completion, and genuine stopping bounds.
Link substantial conditional procedures at their point of use; keep simple
Skills self-contained and avoid loading every reference by default.

## Verify the change

For edits, run `python3 .github/scripts/validate_agent_skills.py`, its unit tests,
changed script paths, and `git diff --check`. Run `docsCheck` when documentation
rules or discovery change, or reuse the final gate that includes it. The
validator checks repository structure and instruction-chain size, not model
judgment. Read [evaluation guidance](references/evaluation.md) when changing
activation or behavior expectations or auditing model outcomes.

Finish an audit with severity, evidence, failure scenario, and proposed owner.
Finish maintenance with changed authorities, measured structural improvement,
behavioral evidence and its limits, plus any unresolved policy decisions.
