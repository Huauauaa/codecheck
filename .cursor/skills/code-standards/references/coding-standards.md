# Coding Standards

These standards are language-agnostic defaults. Repository-specific conventions
take precedence when they are clear and actively used.

## Understand Before Editing

- Read the code that owns the behavior and the closest tests.
- Trace inputs, outputs, side effects, and error handling before changing shared
  code.
- Check existing helpers, framework features, and internal abstractions before
  adding new ones.
- Respect unrelated user or teammate changes in the working tree.

## Design and Maintainability

- Make the change as local as the problem allows.
- Prefer clear data flow over hidden mutation or global state.
- Use structured parsing and serialization APIs for structured data.
- Extract abstractions only when they remove meaningful duplication or clarify a
  stable concept.
- Keep names specific enough to communicate intent without encoding
  implementation details that may change.
- Avoid speculative flexibility, unused options, and broad rewrites.

## Error Handling

- Fail with actionable messages at boundaries where callers or users can respond.
- Preserve original error context when wrapping or rethrowing.
- Avoid swallowing errors unless the fallback is deliberate and tested.
- Keep retry behavior bounded and safe for repeated execution.

## Security and Privacy

- Treat external input, environment variables, files, network responses, and
  user-provided content as untrusted.
- Do not log secrets, tokens, credentials, private data, or full sensitive
  payloads.
- Prefer allowlists for dangerous operations such as command execution, file
  access, redirects, and dynamic imports.
- Use parameterized APIs for database queries and shell-safe APIs for subprocess
  execution.
- Keep dependency additions minimal and prefer maintained packages.

## Testing

- Add focused tests for new behavior and regression tests for bug fixes.
- Cover edge cases at boundaries: empty input, malformed input, permission
  failures, timeouts, concurrency, and partial failure.
- Match the repository's existing test style and fixtures.
- Avoid brittle assertions that duplicate implementation details.
- If a test cannot be added, document the reason and the manual verification
  performed.

## Documentation

- Update user-facing docs when behavior, commands, configuration, or setup
  changes.
- Prefer examples that can be copied and run.
- Keep comments rare and useful: explain non-obvious intent, tradeoffs, or
  constraints rather than restating code.

## Delivery

- Run formatting, linting, type checks, tests, and builds that are relevant to
  the changed area.
- When verification fails for reasons outside the change, capture the failing
  command and the observed reason.
- Summaries should include changed behavior, verification performed, and known
  follow-up work or risks.
