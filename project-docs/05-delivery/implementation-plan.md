# Implementation plan (draft — /gen-tasks fills this in)

Milestones, in order:

- **M1 · Backend skeleton + data model** — auth (email, password, OTP), roles, users, businesses, venues, categories, migrations, error format, socket server, TEST/LIVE mode, seed data.
- **M2 · Core API** — venues + map search/filters, queue join/leave/position, queue control, reservations, menu, reviews + accuracy rating, chat, staff roles, audit log. Every queue change emits a socket event. Sensor simulator starts here.
- **M3 · Frontends in parallel** (against api-spec mock server until endpoints exist)
  - customer-app: onboarding, auth, map home, filters, venue, queue tracker, reservation, inbox, profile
  - business-app: login, overview, queue control, verify passcode, menu, inbox, staff, reviews, profile
  - website: home, how it works, pricing, for business, book demo, contact, legal pages, business signup (10 steps)
  - admin: dashboard, businesses (approve/reject/suspend), users, categories
- **M4 · Money** — passes + checkout, rotating passcodes + verify, customer subscription (Stripe + Apple IAP), business plans + contracts, Stripe Connect payouts, 15% commission, refunds, VAT, business finance, admin payments/refunds/chargebacks.
- **M5 · Engagement** — notifications, points + rewards, analytics, marketing (discounts, boost), support tickets, fraud rules, admin settings, business web dashboard.
- **M5b · Sensors (Pro)** — sensor-gateway, occupancy + wait calculation, auto queue update, health + alerts, sensor management (business + admin), Live View (numbers). Real device test.
- **M6 · Hardening + release** — E2E for every journey, load test on one busy venue, compliance (delete account, data export, policies, store data safety), staging + production, CI/CD, monitoring, store releases.
