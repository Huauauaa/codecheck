# Codecheck

Codecheck is a Cursor Agent Skill repository for code standards.

It currently contains only one rule: in Java, string case conversion and
number formatting that must output Western digits must pass an explicit
`Locale.ROOT` or `Locale.ENGLISH`.

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

## Usage

In Cursor, add this GitHub repository as a remote project rule/skill source.
Cursor will discover `.cursor/skills/code-standards/SKILL.md` and make the
skill available to Agent when the Java Locale rule is relevant.

You can also copy the `code-standards` folder into another repository under
`.cursor/skills/` or `.agents/skills/`.

## Maintenance

Do not add unrelated coding standards until they are explicitly requested.
Keep this repository focused on approved rules only.
