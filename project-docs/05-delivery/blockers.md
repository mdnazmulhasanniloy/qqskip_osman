# Blockers

Format: `B-xxx · status · question`. Status: open | answered (date, where the answer lives) | partial.
Claude: never guess an open blocker. Add new ones at the end with the next number. When the client answers,
run `/answer-blockers` so the answer flows into the PRD or an ADR.

## Scope and business

- **B-001 · partial** · Launch country. Spec prices in GBP and mentions VAT → assume UK. Confirm country, timezone, VAT rate, and whether US cities on the Figma map are placeholders.
- **B-002 · answered 2026-11-23 (client-docs/qskip-spec.md §1)** · All four surfaces are in scope: customer app, business app (tablet + mobile), website (marketing + onboarding + business dashboard), admin.
- **B-003 · partial** · Sensors: in scope for Pro plan (spec §5 "Sensors included", "Sensor management"). Vendor = FootfallCam. Open: see B-025 to B-030.
- **B-004 · answered 2026-11-23 (spec §8)** · Stripe for passes, Stripe Connect for business onboarding and payouts, Apple IAP for iOS customer subscription, Stripe webhooks for payments, subscriptions, refunds, payouts.
- **B-005 · partial** · Commission 15% / business 85%, editable in admin settings (spec §7, §8). Open: who sets the pass price (business or admin)? How does Pro "smart pricing" work?
- **B-006 · answered 2026-11-23 (spec §4, §5, §7)** · Refund flow: customer request → business approve/reject + note → admin override → result. Statuses pending, approved, rejected, escalated. Open detail: refund window and partial refunds? (Figma pass card says "Non-refundable".)
- **B-007 · open** · What exactly does the customer subscription (£5.99/mo, £49.99/yr) unlock besides points?
- **B-008 · partial** · Points only for subscribers; rules set in admin. Open: default points per action, rewards catalogue, who funds rewards.
- **B-009 · open** · Business Kit (tablet + sensor): free with Pro or charged? Who ships, installs, tracks returns?

## Queue logic

- **B-010 · open** · Wait-time formula when there is no sensor; how "accuracy %" is calculated (spec: from "Was wait time accurate?" ratings).
- **B-011 · open** · Is the queue purely virtual? Can a business reorder, call next, or remove a customer? How is "called" communicated?
- **B-012 · partial** · Error cases given (queue full, business closed, code expired, payment failed, no internet, location denied). Open: no-show rule, after how many minutes the "Queue info outdated" banner appears.

## Unclear Figma comments

- **B-013 · open** · Comments #36, #31, #23: which pages exactly are removed? Comment #26 "queue size = maximum capacity": is queue size a setting or a live count?
- **B-014 · open** · Comment #34 "update" and #28 "modify chat system": what should change? Spec wants business chat, support chat, quick replies, escalate.
- **B-015 · open** · AI: #27 removes an AI feature, #35 adds AI short bio, spec adds an AI chatbot, Figma has "AI recommendation". Which AI features stay?
- **B-016 · open** · Admin has screenshots only. Need designs or approval to build from a UI kit for: Businesses, Users, Tickets, Staff, Payments, Refunds, Fraud, Sensors, Knowledge Base, Activity Log, Settings. Admin roles?
- **B-017 · open** · Login methods: email + password + OTP only, or also Google / Apple sign-in? Languages: English only?
- **B-018 · answered 2026-11-23 (spec §1)** · Business app runs on tablet and mobile. Open detail: iPad as well as Android tablet?

## Spec vs Figma conflicts

- **B-019 · open** · Map pin colors: spec 3 levels (green <10, orange 10–25, red >25 min) vs Figma 4 levels (<10, 10–20, 20–30, 30+).
- **B-020 · open** · Business signup: spec says "App + Website"; Figma comment #32 says website only.
- **B-021 · open** · AI chatbot in spec vs comment #27 "remove ai feature".
- **B-022 · open** · Points card has "Passcode for visit verification": how is a visit verified without a pass, and how many points?
- **B-023 · open** · Business web dashboard (spec §6) has no Figma design. Designer will provide, or reuse business app design?
- **B-024 · open** · Apple IAP takes 15–30%: same £5.99 on iOS or different price?

## Sensors (FootfallCam)

- **B-025 · open** · Which model per venue/plan? 3D Pro2 gives occupancy only; queue length needs Pro3 (+Pro1).
- **B-026 · open** · Device push sends IN/OUT events. Can Pro3 queue metrics be pushed from the device, or only read from the V9 cloud API?
- **B-027 · open** · Who buys, installs and calibrates devices? Venue internet (Ethernet / Wi-Fi / 4G)? Return process?
- **B-028 · open** · When do we get a test device and FootfallCam API / V9 access? Which ACK format does the firmware expect (`OK` or `{status:"ack", uuid}`)?
- **B-029 · open** · Live View: numbers only (recommended for MVP) or real video feed?
- **B-030 · open** · Text for the website "Sensor disclosure" page and GDPR position (FootfallCam claims no personal data, privacy mode).
