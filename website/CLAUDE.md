# Website · CLAUDE.md

Stack: Next.js (App Router) · TypeScript · Tailwind · TanStack Query · Stripe Checkout / Connect onboarding   <- confirm in ADR-001
Docs: ../project-docs. Read 00-INDEX.md first.
Commands: npm run dev · npm test · npm run lint · npm run build

## Scope
- Marketing: Home, How it works, Pricing, For Business, Customer app info, Book demo, Contact.
- Legal: Terms, Privacy, Refund, Cookie, Sensor disclosure.
- Business signup (10 steps, spec §5): account, details, map pin, opening hours, plan, contract, queue setup, Stripe Connect, terms, submit → pending approval.
- Business web dashboard (spec §6): subscription, billing, invoices, analytics, staff, profile, upgrade/downgrade/cancel. No Figma yet (B-023).

## Design
- Figma frames 1440 wide. Tokens from 03-design/design-system.md. Images: 01-discovery/figma-screens/web_*.png.

## Rules
- Read the task file and every doc it links before writing code.
- Marketing pages are static/SSG and SEO-ready (titles, meta, OG images). Dashboard pages are authenticated.
- Prices and plan features come from the API / admin settings, not hard-coded copy.
- Unclear? Add it to 05-delivery/blockers.md, set task status: blocked, stop.
- Done = every acceptance criterion has a passing test; Lighthouse check on marketing pages.
- After a task: update task status, implementation-plan.md, changelog.md.

## Never
- Invent legal text (blocked until client supplies it) · commit secrets · invent requirements.
