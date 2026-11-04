# Shared Home Bill Splitter

A TypeScript bill-splitting application built with Hono, Cloudflare Workers, D1, React, and TanStack Router.

## Development

This repository follows the assignment stack:
- Hono API on Cloudflare Workers
- Cloudflare D1 (SQLite)
- React + Vite + TanStack Router
- TypeScript, Vitest, and Biome

The implementation is being built in small stages. See the **Decisions** section for the reasoning behind key design choices.

## Decisions

1. **Store money as integer cents.** This avoids floating-point rounding problems when bills are split.
2. **Persist member order explicitly.** The order members join a home determines who receives remainder cents.
3. **Make payment updates conditional and idempotent.** A payment must be safe to retry and must not be applied twice.

## Setup

```bash
pnpm install
pnpm dev
```

Run checks:

```bash
pnpm check
pnpm typecheck
pnpm test
pnpm build
```
