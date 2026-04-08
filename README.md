# Cursor Rules

This folder is for Cursor rule files (e.g. `RULE.md`) that provide persistent AI guidance within this repository.

## Pull Request Placement Rule

- Any Cursor-related files included in a Pull Request must be placed under `.cursor/`.
- Rule files must go in `.cursor/rules/`.
- Command files must go in `.cursor/commands/`.

## What Goes In `.cursor/rules/`

- Files with `.mdc` extension only.
- Persistent project guidance and constraints for AI.
- Rules that define architecture, coding conventions, safety limits, testing expectations, and protected files.
- Rules should use front-matter fields such as `description`, `globs`, and `alwaysApply`.
- Examples:
  - `architecture.mdc`
  - `conventions.mdc`
  - `do-not-touch.mdc`
  - `module-boundaries.mdc`
  - `change-scope.mdc`
  - `canvas-rendering.mdc`
  - `action-manager-state.mdc`
  - `typescript-safety.mdc`
  - `testing-requirements.mdc`

## What Goes In `.cursor/commands/`

- Files with `.md` extension only.
- Reusable slash command prompts the team can run in Cursor.
- Commands that describe task workflows (for example: implement safely, run compliance review, prepare PR checks).
- Commands can include `$ARGUMENTS` placeholders for user input.
- Examples:
  - `rules-check.md` -> `/rules-check`
  - `implement-safe.md` -> `/implement-safe`

## Do Not Mix These

- Do not put command prompts in `.cursor/rules/`.
- Do not put `.mdc` rule definitions in `.cursor/commands/`.

