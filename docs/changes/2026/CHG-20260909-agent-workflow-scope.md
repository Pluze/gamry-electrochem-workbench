# Scoped agent workflows

```labkit-change
id: CHG-20260909-agent-workflow-scope
date: 2026-09-09
type: chore
compatibility: compatible
component: repository
supersedes: CHG-20260822-final-state-agent-guidance
```

## Why

Repository instructions should guide the requested outcome without expanding a review into implementation, an existing-test run into test authoring, or a narrow task into every specialist workflow. Detailed delivery and release procedures also consumed the shared instruction budget even when those operations were irrelevant.

The accepted design keeps scoped invariants in directory rules and loads specialist procedures only when their mode applies. Explicit durable user policies can establish a rule directly; repeated evidence remains necessary when promoting a one-off correction. Refactoring protects required scientific meaning and supported user outcomes while allowing a coherent replacement of flawed internal designs, including migration of current consumers and removal of superseded wrappers.

## What changed

The PR integration Skill covers preparation through authorized merge and cleanup, with a default invocation that requests both PR creation and merge. Explicit draft-only or no-merge requests retain their requested stopping state. Supporting Skills inherit the caller's scope and authorization. Testing reuses existing evidence and adds specifications only for relevant gaps; performance work includes diagnosing suspected slowness and reviewing existing reports.

Root guidance delegates conditional integration, publication, background-execution, and evidence procedures to their owning Skills. Governance validation parses standard YAML, checks discoverable references and directory instruction budgets, and distinguishes structural fixtures from independently observed model behavior. Private classes within the existing SDK composition model no longer require a separate approval solely because they are classes; public architecture changes and App state-model conversions retain their explicit decision boundary.

## Impact

Maintainers can request complete structural refactors without preserving incidental internal interfaces merely to reduce the diff. Agent workflows have clearer completion states and require less unrelated instruction loading. Instruction maintainers can use supported YAML metadata without reproducing a fixed textual layout, and receive an error when repository instruction chains exceed the default loading budget.

## Compatibility and limits

LabKit Apps, public MATLAB APIs, scientific calculations, saved data, and runtime dependencies are unchanged. Existing direct invocations of the renamed PR preparation Skill should use `labkit-pr-integrator`. The YAML parser is a development and CI tooling dependency only. Static validation does not establish model compliance, user-global instruction size, custom host discovery configuration, or live GitHub execution behavior.
