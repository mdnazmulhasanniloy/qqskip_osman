---
description: Prompt 5 · Implementation plan, task files and test plan
---
Read 00-INDEX.md, 02-product/prd.md, 04-architecture/api-spec.yaml, realtime-events.md, data-model.md and 05-delivery/implementation-plan.md (draft milestones M1–M6 incl. M5b).

Rewrite 05-delivery/implementation-plan.md with those milestones, each listing its task IDs.
Create one file per task in 05-delivery/tasks/ (T-001.md, T-002.md…) using this template:

```
# T-0xx · <title>
Stack: backend | customer-app | business-app | website | admin
Milestone: M1
Requirements: QUEUE-01, QUEUE-02
Depends on: T-0yy
Read: prd.md#QUEUE-01, api-spec.yaml#/queues/{id}/join, screen-specs/customer-queue.md
Done when:
- <acceptance criterion as a test>
Status: todo
```

Each task must be small enough to build and test in one session. Backend tasks come before the app tasks that consume them, unless the app can use the mock server.
Write 05-delivery/test-plan.md: which requirements get unit, integration, E2E tests.
End implementation-plan.md with a table requirement ID → task IDs. Flag any requirement with no task. Tasks blocked by an open blocker get Status: blocked.
