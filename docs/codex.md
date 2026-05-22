# Codex Usage Guide

Use this guide to install the `code-standards` skill for Codex without adding
any extra coding rules.

## Supported Rule

This skill currently enforces only one rule: Java string case conversion and
Western-digit number formatting must pass `Locale.ROOT` or `Locale.ENGLISH`.

## Install for One Repository

From the target repository root, copy the skill into Codex's repository skill
folder:

```bash
CODECHECK=/path/to/codecheck
mkdir -p .agents/skills
cp -R "$CODECHECK/.cursor/skills/code-standards" .agents/skills/code-standards
```

Codex scans `.agents/skills` from the current working directory up to the
repository root. Restart Codex if the new skill does not appear.

## Install for All Repositories

Copy the skill into your personal Codex skill folder:

```bash
CODECHECK=/path/to/codecheck
mkdir -p ~/.agents/skills
cp -R "$CODECHECK/.cursor/skills/code-standards" ~/.agents/skills/code-standards
```

Personal skills are available across repositories for the current user.

## Invoke the Skill

Use explicit invocation when you want Codex to apply this rule directly:

```text
$code-standards
```

In Codex CLI or IDE, you can also run `/skills` or type `$` and select the
`code-standards` skill when it is available.

Example prompts:

```text
$code-standards review this Java change for Locale usage
```

```text
Check whether this Java code formats Western digits with Locale.ROOT or Locale.ENGLISH.
```

## Update the Skill

After pulling updates in this repository, replace the copied skill folder in the
target location with the updated `code-standards` folder. Do not edit the copied
skill to add unrelated rules.
