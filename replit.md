# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

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

## Artifacts

### LevelUp.AI (artifacts/levelup-ai)
AI-powered student productivity mobile app built with Expo/React Native.

**Features:**
- Dashboard with study streak, stats, and quick access tools
- AI Doubt Solver — ask any question, get step-by-step explanations via OpenAI
- Quick Notes Generator — AI generates structured study notes by subject & topic
- AI Mock Test Generator — 40-mark MCQ tests (10 questions × 4 marks) with auto-scoring
- Study Planner — personalized daily/weekly schedule generation via AI
- Progress Tracker — tracks tests, scores, streak, study time, weak/strong subjects
- Profile management with avatar picker and grade selector

**Tech:**
- Expo Router (file-based routing)
- AsyncStorage for local persistence
- OpenAI GPT-4o-mini via EXPO_PUBLIC_OPENAI_API_KEY
- Dark purple glassmorphism theme
- Inter font family

**Required secrets:** OPENAI_API_KEY (passed as EXPO_PUBLIC_OPENAI_API_KEY in dev script)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
