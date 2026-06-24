# init-sudoku2t — shared foundation

Generated deterministically by DevOps from the approved project-decomposition.

**Stack:** TypeScript (npm workspaces)
- install: `npm install`
- build: `npm run build`
- test: `npm test`

## Subsystems (one feature team each)
- **backend** — Backend API & Persistence: Implements all HTTP API endpoints (GET /puzzle, POST /validate, POST /scores, GET /leaderboard), puzzle generation, validation logic, SQLite persistence, and leaderboard ordering. Owns the backend server and database.
  - owns: packages/backend/**
  - dependsOn: contracts
- **frontend** — Frontend SPA: Implements the browser-based SPA: interactive 9x9 Sudoku board, difficulty selection, puzzle fetching, result submission, leaderboard display, and optional client-side validation. Owns the web application.
  - owns: packages/web/**
  - dependsOn: contracts
- **contracts** — Shared Contracts Package: Defines all TypeScript interfaces and types for HTTP request/response payloads used between Backend and Frontend. Acts as the single source of truth for API contracts.
  - owns: packages/contracts/**
  - dependsOn: none

## Shared contracts
- packages/contracts
