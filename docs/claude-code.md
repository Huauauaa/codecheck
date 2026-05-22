# Claude Code Usage Guide

Use this guide to install the `code-standards` skill for Claude Code without
adding any extra coding rules.

## Supported Rule

This skill currently enforces only one rule: Java string case conversion and
Western-digit number formatting must pass `Locale.ROOT` or `Locale.ENGLISH`.

## Install for One Project

From the target project root, copy the skill into Claude Code's project skill
folder:

```bash
CODECHECK=/path/to/codecheck
mkdir -p .claude/skills
cp -R "$CODECHECK/.cursor/skills/code-standards" .claude/skills/code-standards
```

Start Claude Code from the target project root:

```bash
claude
```

Claude Code discovers project skills from `.claude/skills/`. If the top-level
`.claude/skills/` directory did not exist when the session started, restart
Claude Code after creating it.

## Install for All Projects

Copy the skill into your personal Claude Code skill folder:

```bash
CODECHECK=/path/to/codecheck
mkdir -p ~/.claude/skills
cp -R "$CODECHECK/.cursor/skills/code-standards" ~/.claude/skills/code-standards
```

Personal skills are available across projects for the current user.

## Invoke the Skill

Use either automatic or explicit invocation:

```text
/code-standards
```

Example prompts:

```text
/code-standards review this Java change for Locale usage
```

```text
Check whether this Java code formats Western digits with Locale.ROOT or Locale.ENGLISH.
```

## Update the Skill

After pulling updates in this repository, replace the copied skill folder in the
target location with the updated `code-standards` folder. Do not edit the copied
skill to add unrelated rules.
