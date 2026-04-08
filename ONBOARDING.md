# ONBOARDING

## Purpose

This guide helps new contributors (human and AI) work safely in this repository with consistent project rules and Cursor commands.

## Repository Guidance Files

- `AGENTS.md`: repo-wide operating guidance for AI agents.
- `.cursor/rules/*.mdc`: focused, persistent rules that apply by scope (`globs`) or globally (`alwaysApply`).
- `.cursor/commands/*.md`: reusable slash commands for common workflows.

## Quick Start

1. Read `README.md` for project setup and architecture context.
2. Read `AGENTS.md` before making code changes.
3. Review relevant rule files in `.cursor/rules/`.
4. Use commands in `.cursor/commands/` for consistent execution and review.
5. Keep changes minimal, test behavior changes, and document assumptions.

## Current Cursor Rules

- `architecture.mdc`: architecture constraints for project structure and dependencies.
- `conventions.mdc`: code conventions for TypeScript/components.
- `do-not-touch.mdc`: protected files and restrictions.
- `action-manager-state.mdc`: state updates must go through `actionManager.dispatch()`.
- `canvas-rendering.mdc`: rendering must remain on Canvas 2D pipeline.
- `typescript-safety.mdc`: strict typing and type import conventions.
- `module-boundaries.mdc`: package boundaries and utility reuse guidance.
- `testing-requirements.mdc`: tests required for behavior changes.
- `change-scope.mdc`: keep changes focused and minimal.

## Rule Usage Notes

- Rule scope is controlled by front-matter:
  - `globs`: where a rule applies (for example `packages/**/*.ts`).
  - `alwaysApply`: if `true`, rule applies in every session.
- Keep rules concise and actionable.
- Include a `How to verify` section in rule content for consistency.

## Current Cursor Commands

- `rules-check.md` -> `/rules-check`
  - Reviews changes against `AGENTS.md` and all `.cursor/rules/*.mdc`.
  - Returns violations, risk level, and a compliance checklist.
- `implement-safe.md` -> `/implement-safe`
  - Implements a request with minimal changes while enforcing repository rules.
  - Accepts user prompt via `$ARGUMENTS`.

## Recommended Workflow

1. Start with `/implement-safe <your task>`.
2. Apply the smallest correct change.
3. Add/update tests for behavior changes.
4. Run `/rules-check` before finalizing.

## Protected File Reminder

Certain files are protected by policy in `do-not-touch.mdc` and `AGENTS.md`. Any change to protected/core files requires explicit approval plus stronger verification.

## Maintenance

- When adding new `.cursor/rules` files, update this document.
- When adding new `.cursor/commands`, add usage notes here.
- Keep examples and paths aligned with the current monorepo layout.
