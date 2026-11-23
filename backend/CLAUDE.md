# Backend · CLAUDE.md

Stack: Node 22 · TypeScript · NestJS · PostgreSQL · Prisma · Redis · Socket.IO · Stripe + Stripe Connect   <- confirm in ADR-001
Docs: ../project-docs. Read 00-INDEX.md first.
Commands: npm run dev · npm test · npm run lint · npx prisma migrate dev · npm run simulate:sensor

## Owns
- 04-architecture/api-spec.yaml (OpenAPI 3.1) and realtime-events.md — the contracts every app builds against.
- 04-architecture/data-model.md (Prisma schema must match it).

## Rules
- Read the task file and every doc it links before writing code.
- API, socket event or schema change: update api-spec.yaml / realtime-events.md / data-model.md FIRST.
- Unclear? Add it to 05-delivery/blockers.md, set task status: blocked, stop.
- Done = every acceptance criterion has a passing test.
- After a task: update task status, implementation-plan.md, changelog.md.
- One error format everywhere: { "error": { "code", "message", "details" } }.
- Money in minor units (pence) with a currency field; never hard-code £.
- Every queue write emits its socket event after the DB commit, and writes an AuditLog row with source (user | staff | sensor | admin).
- Passcodes: 4–6 digits, one-time, business-specific, expiry from admin settings (30–60 s); store only a hash.
- Stripe and FootfallCam webhooks/pushes: verify signature or token, idempotent by event id / UUID.
- Respect TEST / LIVE env: test mode uses Stripe test keys and fake data only.
- Rate-limit auth, passcode verify and payment endpoints.

## Never
- Edit merged migrations · commit secrets or Stripe keys · invent requirements · weaken a test to make it pass.
