# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Artifacts

### CDCP Eligibility Estimator (`artifacts/cdcp-estimator`)
- **Type**: react-vite (served at `/`)
- **Description**: Canada Dental Care Plan eligibility & co-pay estimator — single-file static page (`index.html`) served via Vite
- **Tech**: Tailwind CSS via CDN, vanilla JavaScript (no React used in runtime)
- **Features**: Age-based rollout logic, income brackets, insurance check, JSON-LD schemas, FAQ, disclaimers, accessible UI
- **All logic constants** are in a `CONSTANTS` object at the top of the `<script>` tag in `index.html`

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
