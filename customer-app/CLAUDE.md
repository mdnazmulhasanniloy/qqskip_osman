# Customer app · CLAUDE.md

Stack: React Native (Expo) · TypeScript · Expo Router · TanStack Query · Zustand · Socket.IO client · react-native-maps (Google) · Stripe RN SDK · Apple IAP (iOS subscription)   <- confirm in ADR-001
Docs: ../project-docs. Read 00-INDEX.md first.
Commands: npx expo start · npm test · npm run lint · npm run typecheck

## Design
- Figma frame size 440×960 (iPhone 16 Pro). Tokens: 03-design/design-system.md. Never hard-code colors.
- Screen spec for every screen: 03-design/screen-specs/customer-*.md. Image reference: 01-discovery/figma-screens/customer_*.png.
- Bottom tabs: Home · Passes · Points · Inbox · Profile.

## Rules
- Read the task file and every doc it links before writing code.
- Build against api-spec.yaml types (generated client), never hand-write response shapes. Endpoint missing → mock server + blocker.
- Live data (queue position, wait, passcode) comes from socket events in realtime-events.md, not polling.
- Every screen handles loading, empty, error and offline states; errors from the spec: payment failed, code expired, queue full, business closed, no internet, location denied.
- Unclear? Add it to 05-delivery/blockers.md, set task status: blocked, stop.
- Done = every acceptance criterion has a passing test (component or E2E).
- After a task: update task status, implementation-plan.md, changelog.md.

## Never
- Store tokens outside secure storage · log personal data · put Stripe secret keys in the app · invent requirements.
