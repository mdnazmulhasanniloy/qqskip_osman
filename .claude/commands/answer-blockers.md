---
description: Prompt 7 · Flow client answers into the docs. Usage /answer-blockers <notes file>
---
The client answered blockers in project-docs/01-discovery/meeting-notes/$ARGUMENTS.
For each answered blocker: update every affected doc (prd.md, design, api-spec.yaml, data-model.md, ADRs),
mark the blocker "answered <date> (<where the answer now lives>)" in 05-delivery/blockers.md,
set related tasks from blocked to todo, and add a changelog line. List what changed.
