# AGENTS.md

## Purpose

Guidance for AI coding agents working in this repository. Follow these rules unless a human explicitly overrides them.

## Architecture Constraints

- Use custom state management via `actionManager`; do not introduce Redux, Zustand, or MobX.
- Perform state updates through `actionManager.dispatch()` only.
- Keep core app state aligned with `AppState` in `src/types.ts`.
- Use Canvas 2D for drawing/rendering flows; do not replace with React DOM drawing.
- Preserve render flow: `Scene -> renderScene() -> canvas context`.
- Do not introduce `react-konva`, `fabric.js`, or `pixi.js`.
- Do not add new npm dependencies without explicit approval.
- Check existing utilities (for example `src/utils/`) before adding external helpers.

## Code Conventions

- Use functional components with hooks only; avoid class components.
- Prefer named exports over default exports.
- Keep TypeScript strict; avoid `any` and `@ts-ignore`.
- Prefer `type` over `interface` for simple types.
- Use `import type { X } from "..."` for type-only imports.
- Use `kebab-case` for utility file names and `PascalCase` for component files.
- Keep tests colocated where practical (for example `ComponentName.test.tsx`).

## Protected Files

Do not modify the following files without explicit human approval:

- `src/core/renderer.ts` (render pipeline)
- `src/data/restore.ts` (file format compatibility)
- `src/actions/manager.ts` (action dispatch system)
- `src/types.ts` (core type definitions)

If protected files must change, require:

1. Understanding of dependencies and downstream impact.
2. Running the relevant test suite.
3. Manual verification of behavior.

## Working Style

- Make focused, minimal changes.
- Do not refactor unrelated code.
- Preserve existing behavior unless asked to change it.
- Flag uncertainty and assumptions in your final update.
