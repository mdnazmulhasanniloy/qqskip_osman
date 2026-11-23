---
description: Prompt 6 · Build the next task for this repo. Usage /next-task (or /next-task T-014)
---
This repo's task Stack value is its folder name (backend, customer-app, business-app, website or admin).
If $ARGUMENTS names a task, use it. Otherwise pick the next task in ../project-docs/05-delivery/tasks/
whose Stack matches this repo folder, Status: todo, and all dependencies done.

Read it and every doc it links. Plan first. After I approve:
- implement it following CLAUDE.md
- write a test for each acceptance criterion, run them, fix until all pass
- set Status: review, update implementation-plan.md and changelog.md
If anything is unclear: add it to blockers.md, set Status: blocked, and stop.
