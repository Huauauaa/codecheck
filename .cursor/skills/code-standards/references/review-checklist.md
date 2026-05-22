# Review Checklist

Use this checklist before delivering or reviewing code changes.

## Fit for Request

- The change directly addresses the user's request or reported issue.
- Behavior changes are intentional and documented where needed.
- Unrelated formatting, rewrites, and dependency churn are avoided.
- Existing public APIs, persisted formats, and compatibility expectations are
  preserved unless a breaking change is explicit.

## Code Quality

- The solution follows local naming, architecture, and framework patterns.
- Control flow is readable and avoids unnecessary cleverness.
- Shared logic is tested and placed in the right ownership boundary.
- New abstractions have a clear reason to exist.
- Dead code, debug logging, and temporary scaffolding are removed.

## Reliability

- Error paths are handled deliberately.
- Async, concurrent, or retrying code is bounded and race-aware.
- Edge cases and invalid inputs are covered or intentionally rejected.
- Resource cleanup is reliable for files, network connections, locks, timers,
  and subscriptions.

## Security

- Inputs crossing trust boundaries are validated, parsed, or normalized.
- Secrets and private data are not logged or committed.
- Permission checks and authorization boundaries remain intact.
- Dependencies are necessary, current, and introduced through the package
  manager.

## Tests and Verification

- Relevant automated tests were added or updated.
- Existing focused tests pass for the changed area.
- Linting, formatting, type checks, and builds were run when applicable.
- Manual verification steps are documented if automated coverage is not
  available.

## Delivery Notes

- The final summary states what changed and why.
- The final summary lists verification commands and their results.
- Residual risks or follow-up items are explicit and actionable.
