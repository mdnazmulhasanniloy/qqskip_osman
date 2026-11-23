# Admin · CLAUDE.md

Stack: React (Vite) · TypeScript · React Router · TanStack Query + TanStack Table · a UI kit (e.g. shadcn/ui)   <- confirm in ADR-001
Docs: ../project-docs. Read 00-INDEX.md first.
Commands: npm run dev · npm test · npm run lint · npm run build

## Scope (spec §7 + Figma sidebar)
Dashboard · Businesses (approve / reject / suspend, contract, payments, sensors, accuracy, notes) · Categories (comment #29) ·
Users (view, block, passes, points, export, delete) · Payments (transactions, commission, refunds, chargebacks, failed, VAT) ·
Refunds (pending/approved/rejected/escalated, override) · Support (chats, tickets, escalations) · Fraud · Sensors (status, alerts, installs, returns) ·
Analytics · Knowledge Base · Activity Log · Settings (commission %, points rules, plan prices, passcode expiry, notification templates).

## Design
- Only screenshots exist (01-discovery/figma-screens/admin_image_*.png). Follow their layout; for screens with no screenshot use the UI kit and mark the screen spec "no design" (B-016).

## Rules
- Read the task file and every doc it links before writing code.
- Standard patterns: list page = filters + server-side paginated table + detail drawer; every destructive action asks for confirmation and is audit-logged.
- Every admin action that changes money, status or settings writes an AuditLog entry (backend).
- Unclear? Add it to 05-delivery/blockers.md, set task status: blocked, stop.
- Done = every acceptance criterion has a passing test.
- After a task: update task status, implementation-plan.md, changelog.md.

## Never
- Show full card or bank details · invent requirements · weaken a test.
