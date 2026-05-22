---
name: code-standards
description: Provides repository-agnostic code standards for implementation, review, testing, and delivery. Use when writing, modifying, refactoring, or reviewing code to keep changes simple, secure, maintainable, and consistent with the existing codebase.
---

# Code Standards

Use this skill when a task involves code changes, code review, refactoring,
tests, build configuration, or delivery readiness. Apply the repository's local
patterns first, then use these standards to fill gaps and keep quality
consistent.

## Operating Principles

- Understand the existing structure, naming, framework choices, and helper APIs
  before editing.
- Keep changes scoped to the user's request and the affected ownership boundary.
- Prefer simple, explicit code over clever abstractions.
- Preserve shipped public interfaces and persisted data formats unless the task
  explicitly asks for a breaking change.
- Treat tests, linters, type checks, and build scripts as part of the change,
  not as optional cleanup.
- Surface uncertainty with concrete risks, affected files, and verification
  gaps.

## Implementation Workflow

1. Inspect the relevant files and adjacent tests before deciding on an approach.
2. Identify the smallest behavioral change that satisfies the request.
3. Follow existing project conventions for names, layout, errors, logging,
   dependency injection, and test style.
4. Add or update tests when behavior changes, bugs are fixed, or regressions are
   plausible.
5. Run the narrowest useful verification first, then broaden when the blast
   radius is shared or user-facing.
6. Summarize what changed, which checks ran, and any residual risk.

## Quality Bar

- Code should be readable without requiring broad context from the author.
- Functions and modules should have one clear responsibility.
- Error paths should be intentional and observable where appropriate.
- Inputs that cross trust boundaries should be validated or normalized.
- Locale-sensitive operations should pass an explicit locale when output must be
  stable across user or server regional settings.
- Security-sensitive data must not be logged, committed, or exposed in errors.
- New dependencies should be justified by clear value and added through the
  repository's package manager.
- Compatibility shims should be reserved for shipped behavior, stable APIs, or
  persisted data.

## References

Load these files when deeper guidance is needed:

- `references/coding-standards.md` for detailed engineering conventions.
- `references/review-checklist.md` for a pre-delivery and code review checklist.
