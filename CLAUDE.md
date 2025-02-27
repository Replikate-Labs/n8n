# n8n Development Guide

## Build & Development Commands
- Build all: `pnpm build`
- Dev mode: `pnpm dev` (backend + frontend)
- Dev backend only: `pnpm dev:be`
- Dev frontend only: `pnpm dev:fe`
- Run single test: `N8N_LOG_LEVEL=silent jest packages/cli/test/path/to/test.test.ts`
- Lint: `pnpm lint`
- Format: `pnpm format`
- Typecheck: `pnpm typecheck`

## Code Style Guidelines
- Indentation: Tabs with width of 2
- Quotes: Single quotes for JS/TS, double for JSX
- Semicolons: Always use
- Line width: 100 characters max
- TypeScript: Use strict typing
- Imports: Group by external/internal, alphabetize
- Naming: camelCase for variables/functions, PascalCase for classes/interfaces
- Error handling: Use try/catch with specific error types
- Format on commit: Code is auto-formatted by Biome on commit
- Vue files: Use Prettier formatting

## Monorepo Structure
This is a pnpm monorepo with packages in `packages/` directory. Main packages:
- `cli`: Main n8n server
- `nodes-base`: All standard nodes
- `workflow`: Core workflow engine
- `editor-ui`: Frontend Vue application