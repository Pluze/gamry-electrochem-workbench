# Release publication

Read only for release notes, release dispatch, publication, or asset verification. Use `docs/develop/release.md` for the supported release contract. A PR merge does not itself request a release.

## Coverage

Treat release notes as a complete tag-to-tag reader summary. Identify the
immediately preceding published GitHub Release rather than assuming the nearest
tag or latest merged PR is the baseline, verify both tag targets and ancestry,
and inspect the complete `<previous-published-tag>..<release-tag>` log and
changed paths. Inventory every structured Change record and every App, facade,
or launcher version transition in that range, then classify each user-visible
addition, change, retirement, compatibility condition, and user action under
Highlights, Fixes, or Upgrade Note. Record non-user-visible classifications in
the release work record, not the public notes.

Draft from that inventory and reconcile each item against the tagged source,
current manuals, and Change records; do not reconstruct release scope from one
PR body, merge subject, or memory. Normalize GitHub Markdown before writing.
After creating or editing the Release, read back its title, tag, body, state,
and assets and repeat the inventory-to-body comparison. A valid tag and asset
do not compensate for an incomplete user-facing summary.


## Version and publication constraints

- Version semantics belong only in dedicated facade/App version metadata,
  dependency requirements, saved-data migration branches, current
  compatibility documentation, and release records. Do not encode versions in
  package, folder, file,
  function, class, type, protocol, test, or current-architecture names; use one
  stable semantic name and let the version contract express compatibility.
- Before a task-branch PR is merge-ready, source changes to a
  versioned app/facade or launcher update its source version and current owning
  manual. Compare the PR base and head: each existing component advances by
  exactly one direct patch, minor, or major step. Record the direct transition
  in one structured change record for the accepted logical change; a
  cross-component change uses one record and lists every affected component.
- Change records preserve the human explanation of why a change happened, its
  accepted choice, relevant rejected alternatives, net behavior, user and
  developer impact, compatibility, and remaining limits. When a later change
  replaces an earlier choice, link it with `supersedes`; do not create a
  separate decision record. Change records do not preserve commit order, raw
  test inventories, hashes, or CI mechanics.
- Each published LabKit version owns one GitHub Release matching its `vX.Y.Z`
  tag. GitHub is the single source for that published version summary; do not
  create a parallel page under `docs/`, maintain an unreleased changelog, or
  duplicate Change narratives.
- Before drafting or publishing release notes, identify the immediately
  preceding published release tag and audit the complete
  `<previous-published-tag>..<release-tag>` boundary. Reconcile its commits,
  changed paths, structured Change records, and component version transitions
  so every added, changed, or retired user-visible App, workflow, public
  contract, compatibility condition, and required user action is represented
  in Highlights, Fixes, or Upgrade Note. Explicitly classify remaining changes
  as non-user-visible in the release work record. Never infer release scope
  from only the latest PR, merge commit, branch, or remembered delivery.
- After writing or editing a GitHub Release, read back the published title,
  tag, body, and assets and compare the body once more with that complete tag
  boundary before considering the release complete.
- New release tags are `vX.Y.Z`; do not rename published legacy tags. Release
  titles contain only `VX.Y.Z` with an uppercase `V` and relevant `Highlights`,
  `Fixes`, `Upgrade Note`, and `Validation` sections.
- Treat release notes as a user-facing product summary, not a release audit.
  Describe observable behavior, affected workflows, compatibility, and actions
  a user may need to take. Do not publish commit or run identifiers, commands,
  test inventories, CI architecture, internal package movement, hashes, byte
  counts, or maintainer-only evidence; keep those in the PR, workflow record,
  or release asset verification.
- Start the manual `Release` workflow only after developer-led interactive App
  validation, successful required PR validation, and a successful lightweight
  `Continuous Integration` main-push run for the exact squash commit. It then
  creates the validated tag and a draft GitHub Release. Review its notes and
  asset before publishing; ordinary CI never creates tags, and CI runners never
  install optional Toolboxes.
- Release assets come from the tag blob, not the worktree. Verify byte count
  and SHA-256 before and after upload; replace a mismatched asset without moving
  a published tag.
