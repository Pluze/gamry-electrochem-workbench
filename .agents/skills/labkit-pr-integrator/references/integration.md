# Integration mechanics

Read for authorized branch replay, merge, or post-merge cleanup. Ordinary PR preparation uses the entrypoint.

A merge request includes the routine branch work needed to deliver its PRs.
Own that work instead of asking the user to choose Git mechanics:

1. Inventory every requested PR's goal, base/head, complete diff, validation,
   review conversations, component contracts, and associated worktrees. Check
   for active or unpublished work. Decide dependency order from behavior and
   shared contracts, not PR numbers or whether Git reports a textual conflict.
2. After each accepted main update, refresh the remaining boundaries. Replay
   or rebase the next PR on the exact accepted main in its clean task worktree
   or an isolated candidate worktree. Retain the old tip in a recoverable ref
   until acceptance; preserve unrelated dirt and commits.
3. Compare the old and proposed task deltas using the inventory's
   `--previous-head <old-sha>` option and `git range-diff`. Read intersecting
   source, tests, and docs. Reconstruct a coherent file when necessary from
   the accepted contracts and each PR's intended behavior; do not resolve a
   semantic conflict by blindly choosing one side. Identical patches are
   useful evidence, not proof that independently changed contracts compose.
4. Audit the resulting versions, docs, Change records, and source boundaries.
   Run focused evidence for replay or repair; re-plan the final local gate
   when the resulting scope intentionally widens. Previous CI is evidence
   for its original tree only. Refresh the PR title/body for the accepted
   result and publish a necessary non-fast-forward task update with the exact
   old-SHA lease prescribed by AGENTS.md. Verify local and remote heads just
   before updating; on a changed head, inspect and incorporate the new work
   or stop for uncertain ownership rather than overwriting it.
5. Require fresh CI and review/conversation resolution for the proposed head,
   then merge with an explicit Conventional Commit squash subject and an
   expected-head check. Verify the exact main policy run before advancing to
   the next merge and cleaning up accepted work.

Routine baseline drift, replay, file reconstruction, and task-branch leases
within the authorized outcome do not need another permission question. Ask
when evidence cannot resolve a product/scientific choice, ownership, or an
external permission boundary. Never bypass main protection, CI, or review.


## Accepted-task cleanup

After merge, verify resolved SHAs, the exact main-push policy run, dependent
PRs, unmerged commits, and the task's registered worktrees. Close the task in
this order:

1. Inspect each task-owned linked worktree. Remove it only when its contents
   are accepted, or when any remaining dirt is verified disposable validation
   output with no unaccepted work. Include candidate trees and recovery refs
   owned only by that accepted PR; preserve independent active tasks.
2. Delete the local task branch only after no linked worktree uses it and the
   accepted squash commit is verified.
3. Verify GitHub's automatic remote-head deletion. Delete a remaining remote
   branch only when it is the exact accepted head; never infer cleanup safety
   from a branch name.
4. When the primary checkout is clean, fast-forward it to the accepted
   `origin/main` commit and verify clean alignment. Stop and report unrelated
   local work instead of switching, cleaning, or overwriting it.

Do not recycle a merged branch or leave a completed task's worktree, local
branch, or remote branch as normal residue.
