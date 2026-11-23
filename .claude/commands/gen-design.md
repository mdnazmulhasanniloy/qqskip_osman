---
description: Prompt 3 · Design system, screen flow and one spec per screen
---
Using 02-product/prd.md, 02-product/user-journeys.md, 01-discovery/design-tokens.md,
01-discovery/figma-screen-inventory.md, 01-discovery/figma-comments.md and the images in 01-discovery/figma-screens/
(or the Figma MCP server if connected) write in project-docs/03-design/:

- design-system.md: tokens exactly as in Figma (colors, type scale Text XS–7XL, spacing, radius, effects),
  components with variants and states: map pin by queue level, venue card, live wait card, KPI card,
  queue stepper, pass card with rotating code, chip, bottom sheet, sidebar, data table, modal, toast.
- screen-flow.md: navigation map per surface (customer-app tabs, business-app sidebar, website routes, admin routes), as Mermaid.
- screen-specs/<surface>-<screen>.md for every screen in the inventory, plus screens the PRD needs that Figma lacks
  (mark those "No Figma design — blocked by B-xxx" or "build from UI kit").
  Each spec: purpose, requirement IDs, layout, data shown (with source endpoint/event once known), actions,
  and loading / empty / error / success / offline states, plus role restrictions.

Apply figma-comments.md over the screens. New questions → blockers.md. One surface at a time; show me the list of spec files first.
