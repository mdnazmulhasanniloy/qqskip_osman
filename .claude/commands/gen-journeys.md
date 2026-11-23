---
description: Prompt 2 · User journeys and roles/permissions from the approved PRD
---
Using project-docs/02-product/prd.md write:

- 02-product/user-journeys.md: one journey per role, numbered steps, each step tagged with requirement IDs. Must include:
  1. Customer: discover venue on map → filter → venue page → join queue → track position → called → visit → rate accuracy
  2. Customer: buy Q Skip Pass → show rotating passcode → business verifies → points (if subscribed) → review
  3. Customer: reserve a table; request a refund
  4. Business owner: sign up on website (10 steps) → Stripe Connect → admin approves → log in on tablet → go live
  5. Manager / queue updater: run the queue during a busy evening, incl. "queue info outdated"
  6. Scanner: verify passcodes (valid, invalid, expired, already used)
  7. Pro venue: sensor online → automatic queue updates → sensor goes offline → fallback to manual
  8. Admin: approve business, handle refund escalation, fraud alert, change commission
- 02-product/roles-permissions.md: table role × action (view, create, edit, delete, approve) for every module.

New questions → 05-delivery/blockers.md. Show the outline first.
