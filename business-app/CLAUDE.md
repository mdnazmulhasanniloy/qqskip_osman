# Business app · CLAUDE.md

Stack: React Native (Expo) · TypeScript · Expo Router · TanStack Query · Zustand · Socket.IO client   <- confirm in ADR-001
Docs: ../project-docs. Read 00-INDEX.md first.
Commands: npx expo start · npm test · npm run lint · npm run typecheck

## Design
- Tablet first: Figma frames 1194×834 landscape with a left icon sidebar. Must also work on phones (spec).
- Sidebar: Overview · Analytics · Queue Control · Live View · Sensors · Scan · Earnings · Menu · Inbox · Teams · Reviews · Profile.
- Screen specs: 03-design/screen-specs/business-*.md. Images: 01-discovery/figma-screens/business_*.png.
- No signup in this app (Figma comment #32, blocker B-020): login only, "Join us" opens the website signup.

## Rules
- Read the task file and every doc it links before writing code.
- Role checks on every screen and action: owner, manager, scanner, queue updater (02-product/roles-permissions.md).
- Queue Control writes go through the API; UI updates from socket events so several tablets stay in sync.
- Show "Queue info outdated" / "Queue update needed" states exactly as the spec defines.
- Sensor data is read-only here; manual override is allowed only where the PRD says so.
- Every screen handles loading, empty, error and offline states.
- Unclear? Add it to 05-delivery/blockers.md, set task status: blocked, stop.
- Done = every acceptance criterion has a passing test.
- After a task: update task status, implementation-plan.md, changelog.md.

## Never
- Store tokens outside secure storage · invent requirements · weaken a test.
