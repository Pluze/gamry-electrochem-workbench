# Evidence design

Read when creating or materially changing tests, fixtures, or App workflow coverage.

Use calculation/parser/migration, presenter/renderer/callback/state, generic
hidden-GUI structure, and App workflow as distinct evidence semantics rather
than substitutes ordered only by cost. Every App requires at least one bounded
native core journey from its production source boundary to a useful result,
continuation, or supported failure. Add further journeys only for distinct
user goals, reachable state-dependent chains, or failure/recovery boundaries.
Hidden GUI does not prove native dialog, visual quality, pointer feel,
real-data suitability, or scientific validity.

Audit a changed App with `labkittest.appEvidence`. Every custom declared signal
requires an exact native-runtime operation; callback-name matching cannot
satisfy the GUI inventory. Require an owning
assertion over domain state, presentation, artifact, or supported failure.
Treat the report as an omission detector: a matched call or absence of an
exception is not passing evidence. Do not generate a control
Cartesian product; partition equivalent values and combinations by scientific
meaning, reachable workflow state, failure risk, and platform sensitivity.

For every new or materially changed test, identify the independent oracle and
one plausible production counterfactual that should make it fail for the
intended reason. Reject fixture/consumer tautologies, implementation-shaped
counts, and assertions added only to increase coverage. Use mutation testing
or a deliberate temporary mutation when proportionate, but evaluate assertion
sensitivity rather than optimizing a mutation score.

Apply the output-assertion boundary in `tests/AGENTS.md`. During failure
diagnosis, preserve the captured transcript, identify the producer-owned value
or record, and rerun the smallest evidence after moving the assertion to that
semantic boundary. Do not assign an extra line to a runtime, platform, or
framework until the retained diagnostic supports that cause.

For fixtures, apply `tests/AGENTS.md`: reuse ordinary values and owner-local
builders; share only across real specification consumers. Do not add fixture
protocols or retire a supported outcome merely because a fixture looks awkward.
