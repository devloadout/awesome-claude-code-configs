# CLAUDE.md — Next.js (App Router) + TypeScript

<!--
  DROP-IN TEMPLATE — DevLoadout / Agentic Coding Starter Kit
  Copy this file to your repo root as `CLAUDE.md`.
  Edit the 3 lines marked <<FILL IN>>. Delete this comment block when done.
-->

## Project

<<FILL IN: one sentence on what this app does and who uses it.>>

Stack: Next.js (App Router), TypeScript, React Server Components, Tailwind CSS.
Package manager: <<FILL IN: pnpm | npm | yarn>>.
Deploy target: <<FILL IN: Vercel | self-hosted | …>>.

## Architecture rules (follow exactly)

- **Server Components by default.** Only add `"use client"` when a component needs state,
  effects, or browser APIs. Push client boundaries as far down the tree as possible.
- **Data fetching lives in Server Components or Route Handlers**, never in `useEffect`.
- **Mutations go through Server Actions** (`"use server"`), not ad-hoc API routes, unless an
  external client needs the endpoint.
- Co-locate components with their route in `app/`. Shared UI goes in `components/`.
- No business logic in components — extract to `lib/`.

## Conventions

- Use the existing path alias `@/*`. Never write deep relative imports (`../../../`).
- Tailwind only for styling — no CSS modules, no styled-components, no inline `style={{}}`.
- Validate all external input with `zod`. Type-only is not enough at runtime boundaries.
- Errors: throw in Server Components/Actions and let `error.tsx` catch; don't swallow.

## Commands

- Dev: `<<FILL IN: pnpm dev>>`
- Typecheck: `pnpm tsc --noEmit`
- Lint: `pnpm lint`
- Test: `pnpm test`

**Always run typecheck and lint before telling me a task is done.**

## What NOT to do

- Don't add dependencies without asking — check if the capability already exists.
- Don't create `pages/` directory files; this is App Router only.
- Don't disable TypeScript with `any` or `@ts-ignore` to make errors go away — fix the type.
- Don't reformat files you didn't change.
