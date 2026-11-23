# Qskip · root CLAUDE.md (docs work)

Run Claude here (`cd qskip && claude --model opusplan`) only for document work: PRD, journeys, design,
architecture, tasks, change requests. Build work happens inside each repo.

Docs: ./project-docs. Read project-docs/00-INDEX.md first.

## Rules
- Use only facts from project-docs/01-discovery. Never invent features, numbers or screens.
- Source-of-truth order is in 00-INDEX.md: client answers > client spec > Figma comments > Figma screens.
- Anything unclear or contradictory → 05-delivery/blockers.md (next B-number), never assume.
- Every requirement has an ID (prefixes in 00-INDEX.md); tasks and endpoints reference those IDs.
- Show the outline first, write the full file after approval.
- After any doc change: add a line to 05-delivery/changelog.md.
- Write docs in English.
