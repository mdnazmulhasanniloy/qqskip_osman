# Qskip — Claude Code starter kit

এই folder টা আপনার Playbook এর structure এ সাজানো। এখানে Figma analysis, client এর spec,
FootfallCam এর notes, blocker list, প্রতিটা repo র `CLAUDE.md` আর সব prompt slash command হিসেবে আছে।
বাকি docs (PRD, design, architecture, tasks) Claude Code নিজেই এখান থেকে বানাবে।

## ভেতরে কী আছে

```
qskip/
├─ CLAUDE.md                  # root: শুধু docs এর কাজের নিয়ম
├─ .claude/commands/          # /gen-prd /gen-journeys /gen-design /gen-arch /gen-tasks /answer-blockers /apply-change
├─ project-docs/
│  ├─ 00-INDEX.md             # Claude সবার আগে এটা পড়ে
│  ├─ 01-discovery/           # কাঁচা input (তৈরি আছে)
│  │  ├─ figma-link.md, figma-screen-inventory.md, figma-comments.md, design-tokens.md
│  │  ├─ figma-screens/       # ← Figma থেকে PNG export করে এখানে রাখবেন
│  │  ├─ client-docs/         # client spec (.docx + .md)
│  │  ├─ vendor/footfallcam/  # sensor notes (+ Pro2 datasheet PDF এখানে রাখুন)
│  │  ├─ meeting-notes/       # তারিখসহ client note
│  │  └─ glossary.md
│  ├─ 02-product/ 03-design/ 04-architecture/   # খালি, Claude বানাবে
│  └─ 05-delivery/            # blockers.md (B-001–B-030), implementation-plan.md (draft), changelog.md, tasks/
├─ backend/  customer-app/  business-app/  website/  admin/
│     প্রতিটায়: CLAUDE.md + .claude/commands/ (/next-task /review-task /sync-docs)
```

## ধাপে ধাপে

**ধাপ 0 · প্রস্তুতি (আজ)**
1. Zip টা খুলে `qskip/` folder টা আপনার কাজের জায়গায় রাখুন, তারপর `git init` করুন।
2. Figma থেকে সব frame PNG করে `project-docs/01-discovery/figma-screens/` এ রাখুন (নাম কীভাবে দেবেন সেটা ওই folder এর README তে আছে)। অথবা Figma Dev Mode MCP connect করুন।
3. FootfallCam Pro2 datasheet PDF টা `vendor/footfallcam/` এ রাখুন।
4. `05-delivery/blockers.md` থেকে open প্রশ্নগুলো client কে পাঠান।
5. Stack চূড়ান্ত করুন। প্রয়োজন হলে প্রতিটা `CLAUDE.md` এর `Stack:` line আর `meeting-notes/2026-11-23-kickoff.md` বদলে নিন।

**ধাপ 1 · Docs বানানো (root থেকে, plan mode এ)**
```bash
cd qskip
claude --model opusplan
```
প্রতিটা command আলাদা session এ চালান, মাঝে `/clear` দিন, আর output review করে তারপর পরেরটায় যান:
1. `/gen-prd` → outline approve করুন → PRD review করুন → client sign-off নিন
2. `/gen-journeys`
3. `/gen-design`
4. `/model opus` তারপর `/gen-arch` → API spec আর realtime events খুব মন দিয়ে review করুন
5. `/gen-tasks` → requirement → task table এ কোনো gap থাকা চলবে না

**ধাপ 2 · Repo তৈরি (একবার)**
প্রতিটা repo তে প্রথম task টা সাধারণত project scaffold করা (যেমন `npx create-expo-app`, `nest new`, `create-next-app`)।
`/gen-tasks` এগুলো T-001 হিসেবে বানাবে। এই kit এর `CLAUDE.md` গুলো আগে থেকেই আছে, তাই `/init` চালালে আমাদের file টা overwrite না করে শুধু command গুলো merge করুন।

**ধাপ 3 · Build loop (প্রতিদিন, যেকোনো repo তে)**
```bash
cd backend
claude --model opusplan --add-dir ../project-docs
```
1. `/next-task` → plan approve করুন → Claude build আর test করবে → status `review` হবে
2. `/clear` তারপর `/model opus` তারপর `/review-task T-0xx` → আপনি নিজে review করে merge করুন
3. `/clear` করে পরের task

Backend আগে শুরু করুন (M1, M2)। M3 তে চারটা frontend একসাথে চালানো যায়।

**Client উত্তর দিলে বা নতুন কিছু চাইলে**
1. Note টা `01-discovery/meeting-notes/YYYY-MM-DD.md` এ রাখুন।
2. `/answer-blockers YYYY-MM-DD.md` অথবা `/apply-change YYYY-MM-DD.md` চালান (root থেকে)।
3. প্রতি সপ্তাহে প্রতিটা repo তে `/sync-docs` চালান।

## নিয়ম (Playbook এর ৬টা)
Docs আগে, code পরে · contract আগে · অনুমান না করে blockers.md এ লেখা · test pass না হলে task done না · প্রতিটা change মানুষ review করে · উত্তর পেলে docs এ তুলে রাখা।
