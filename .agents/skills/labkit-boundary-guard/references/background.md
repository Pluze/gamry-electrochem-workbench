# Background execution

Use `labkit-performance-profiler` first and reject background execution when
foreground blocking has not been measured in the affected workflow. Do not
infer a responsiveness problem from callback length, a progress message, or a
single unmeasured run.

Accept a background boundary only when the work is one of these shapes:

- a UI-free computation that receives and returns data-shaped values without
  retaining App state, graphics, Runtime, or `CallbackContext` handles;
- a long-lived service with natural exclusive ownership of a resource, such
  as one device connection, whose client communicates through data-shaped
  commands and events.

Before accepting either shape, require explicit progress, failure,
cancellation, close cleanup, replacement and stale-result behavior. Preserve
deterministic outputs with direct parity evidence. Reject the design when the
new task lifecycle exceeds the measured responsiveness benefit, when an
existing transactional run-to-completion path already meets that benefit, or
when it is expected to isolate a hung MATLAB client. Process-isolated GUI or
diagnostics must be started by the user or environment, never by repository
production shell code.
