# Codecheck

Codecheck is a reusable Cursor Agent Skill repository for code standards.
Install it as a remote skill/rule source to give coding agents consistent
guidance for implementation, review, testing, and delivery quality.

## Contents

```text
.cursor/
`-- skills/
    `-- code-standards/
        |-- SKILL.md
        `-- references/
            |-- coding-standards.md
            `-- review-checklist.md
```

## Skill

The `code-standards` skill helps agents:

- read the existing codebase before changing behavior
- keep changes small, idiomatic, and easy to review
- write safe, maintainable, and testable code
- run appropriate verification before delivery
- review changes against a consistent checklist

## Usage

In Cursor, add this GitHub repository as a remote project rule/skill source.
Cursor will discover `.cursor/skills/code-standards/SKILL.md` and make the
skill available to Agent automatically when code quality guidance is relevant.

You can also copy the `code-standards` folder into another repository under
`.cursor/skills/` or `.agents/skills/`.

## Maintenance

Keep the skill concise and move detailed guidance into `references/` files so
agents can load additional context only when needed. Update the checklist when
team conventions, quality gates, or delivery expectations change.
