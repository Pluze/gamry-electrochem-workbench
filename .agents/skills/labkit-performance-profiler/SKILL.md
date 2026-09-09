---
name: labkit-performance-profiler
description: "Investigate or improve LabKit performance, including suspected slowness and existing profileLabKitTarget reports. Measure before making performance claims; correctness-only review does not require profiling."
---

# LabKit Performance Profiler

Read `AGENTS.md`, the measured source path, nearby tests, and `docs/develop/tools/profiling.md`. Use
`labkit-boundary-guard` if ownership moves and `labkit-test-planner` for
validation.

For an existing report, inspect it first and measure again only for a missing
comparison or unresolved claim. For a new measurement, run a narrow scenario with `profileLabKitTarget`, `OpenReport=false`, and an
explicit target. Record the artifact path and distinguish normal from debug
launch. Start with JSON `summaryText`/`AGENT_SUMMARY`; inspect function rows and
parent/child edges only when needed. Source tags mean:

- `project`: editable checkout code;
- `matlab_internal`: MATLAB implementation;
- `external`: other code;
- `profiler_tool`: measurement overhead.

Profile only affected scenarios; separate startup, close, chooser, Run, or
Export measurements when more than one is relevant. Use synthetic inputs. GUI creation has variance, so confirm a shared
framework conclusion with representative repeated runs and focused behavior
tests. Do not optimize a path merely because it has high total time while it
waits for user input or figure close.

For diagnosis-only requests, report the measured cause without editing. For
optimization, change the owner of the measured cost. Report scenario, before/after
evidence, code changes, tests, and any unverified interactive behavior.
