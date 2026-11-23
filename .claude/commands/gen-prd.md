---
description: Prompt 1 · Generate the PRD from 01-discovery
---
Read every file in project-docs/01-discovery/: client-docs/qskip-spec.md, figma-screen-inventory.md,
figma-comments.md, design-tokens.md, vendor/footfallcam/footfallcam-notes.md, glossary.md, meeting-notes/,
and every image in figma-screens/. Also read 05-delivery/blockers.md.

Write project-docs/02-product/prd.md with sections:
1 Overview & goals · 2 User roles · 3 Functional requirements · 4 Non-functional requirements · 5 Out of scope · 6 Open questions

Roles: customer, business owner, manager, scanner, queue updater, Qskip admin.
Group functional requirements by surface (customer-app, business-app, website, admin, backend/platform)
and use the ID prefixes listed in 00-INDEX.md (AUTH-01, QUEUE-03…).
For each requirement: ID, one-line user story, acceptance criteria as Given / When / Then, source file (and Figma frame or comment #).

Source-of-truth order from 00-INDEX.md: client answers > client spec > Figma comments > Figma screens.
Use only facts from discovery. Do not invent features or numbers.
Requirements that depend on an open blocker: write them, mark "Blocked by B-xxx".
New unclear or contradictory points → append to 05-delivery/blockers.md (next number), do not repeat existing ones.
Add new domain terms to 01-discovery/glossary.md.

Show me the outline first (sections + requirement IDs with titles). Write the full file after I approve.
