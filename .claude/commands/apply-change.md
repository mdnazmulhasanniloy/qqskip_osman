---
description: Change request · docs first, then tasks. Usage /apply-change <notes file>
---
New client notes in project-docs/01-discovery/meeting-notes/$ARGUMENTS.
Update every affected doc (PRD, design, api-spec.yaml, realtime-events.md, data-model.md) and add an ADR if a decision changed.
List what changed. Create tasks for the new work and flag existing tasks that are affected.
If it conflicts with what's already built, add it to 05-delivery/blockers.md. Add a changelog line.
