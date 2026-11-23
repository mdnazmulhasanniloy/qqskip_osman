---
description: Prompt 4 · Architecture, data model, API and realtime contracts, ADRs (use /model opus)
---
Read 02-product/, 03-design/, 01-discovery/client-docs/qskip-spec.md and 01-discovery/vendor/footfallcam/.
Stack (from meeting-notes, confirm in ADR-001): backend NestJS + PostgreSQL + Prisma + Redis + Socket.IO;
customer-app and business-app React Native Expo; website Next.js; admin React; Stripe + Stripe Connect; Apple IAP; Google Maps; FCM.

Write in project-docs/04-architecture/:
- system-architecture.md: components, data flow, auth (JWT + refresh, roles), hosting, TEST/LIVE mode, Mermaid diagram.
- data-model.md: every entity with fields, types, relations, indexes, Mermaid ERD. Start from the spec's core tables
  (Users, Businesses, Queues, Passes, Points, Visits, VerificationTokens, Messages, RefundRequests, Notifications,
  AuditLogs, QueueRatings, Subscriptions) and add what the PRD needs (Categories, QueueEntries, Reservations,
  Contracts, Payouts, Sensors, SensorEvents, StaffMembers, Settings…).
- api-spec.yaml: OpenAPI 3.1, every endpoint the screen specs need, one error format, pagination, auth,
  requirement IDs per endpoint (x-requirements).
- realtime-events.md: every socket event, room, payload and who emits it (queue, chat, notifications, sensor status).
- integrations.md: Stripe, Stripe Connect, Apple IAP, Google Maps, FCM, email/OTP, FootfallCam WebSocket push.
- infra-deployment.md: staging + production, CI/CD, monitoring, logging, backups.
- adr/ADR-001-stack.md, ADR-002-payments-and-commission.md, ADR-003-queue-wait-time-and-accuracy.md,
  ADR-004-sensor-gateway.md, ADR-005-passcode-verification.md (context, decision, alternatives).

Then check every screen spec has the endpoints and events it needs; list gaps at the end.
Open questions → blockers.md. Show me the outline first.
