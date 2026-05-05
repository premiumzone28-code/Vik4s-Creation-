# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Vikas Creation Dashboard (`artifacts/vikas-dashboard`)

Premium dark-themed Project Management Dashboard for Vikas Creation creative agency.

**Stack**: React + Vite + Tailwind CSS v4 + Framer Motion + Lucide React + TypeScript  
**Port**: 5000 (workflow: "Vikas Dashboard" — do NOT use restart_workflow on artifact-managed workflow, it always fails health check)

**Design** (mobile-first, max-width 480px):
- Compact pill-shaped dark header: VC logo + "Vikas Creation" + green "● ADMIN" pill
- Dashboard: "Projects Overview" title, "MANAGE AND TRACK ALL ONGOING WORK" subtitle, filter dropdown, white "+ New Project" button, empty state with doc icon
- Bottom navigation: floating pill bar — DASHBOARD (home icon, active) + Shield icon
- Create New Project form: CLIENT NAME, CONTACT NUMBER, PROJECT DESCRIPTION, PROJECT TYPE dropdown, CATEGORY dropdown, PRIORITY dropdown, Cancel + Submit
- Project Details: info card, file uploads, feedback/comments chat

**Auth**: Admin login — admin / admin123 (login-protected admin panel)

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
