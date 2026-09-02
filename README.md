# Jimmy Wang

**AI Product Manager.** I ship AI products as complete commercial systems — the generative
pipeline, the deterministic guardrails that make it safe to sell, the payment and entitlement
layer, and the growth loop that feeds it.

Previously PM for audio products at ASUS, where I owned hardware from IC platform selection
through mass production. Before that I founded and ran a consumer products company for four
years — 40,000+ paying customers worldwide, NT$60M+ cumulative revenue, a six-person team, and
up to NT$500K/month in performance marketing whose funnel, creative testing and attribution I
owned end to end.

Taipei, Taiwan · [LinkedIn](https://www.linkedin.com/in/jimmy-wang-product/)

---

## Products

### [Fauve](https://github.com/jimmy1220fbab/fauve-case-study) — AI color assistant for creators

Describe a look in plain language or match a reference image; Fauve grades your photos and
video and keeps every layer editable. An agentic editing system interprets requests against
the current grade and persistent project history, then executes real operations — including
refusing the ones it shouldn't run.

Ships on desktop (macOS + Windows), iOS, Android, and web from one repo.
**[ai.flexpresets.com](https://ai.flexpresets.com)** · [Case study →](https://github.com/jimmy1220fbab/fauve-case-study)

### [Zyras](https://github.com/jimmy1220fbab/zyras-case-study) — AI-native NPI operating system for hardware teams

Hardware teams run BOMs in Excel, issues in Jira, and schedules in a separate Gantt tool.
Zyras unifies requirements, NPI stages, BOMs, engineering issues, files, and email into one
project context, then puts a two-stage agent on top of it that can pause mid-execution and
wait for human approval before it writes anything.

**[zyras.io](https://zyras.io)** · [Case study →](https://github.com/jimmy1220fbab/zyras-case-study)

### [Vocuz](https://github.com/jimmy1220fbab/vocuz-case-study) — AI learning platform with a closed-loop growth engine

The platform generates the courses; users buy them cheaply and subscribe to unlock the AI
features. Behind it: a multi-stage content pipeline producing slides, narration, imagery and
quizzes in three languages, and a behavior engine that turns 27 tracked event types into
profiles, segments, lifecycle email, and ad-platform audiences — then measures what all of
it cost.

**[vocuz.ai](https://vocuz.ai)** · [Case study →](https://github.com/jimmy1220fbab/vocuz-case-study)

---

## The same skeleton, three times

The interesting part of an AI product is rarely the model call. It is everything that has to be
true before you can charge money for the output. All three products solve the same problems in
the same order — which is the argument that this is a method rather than three lucky shots.

| | **Fauve** | **Zyras** | **Vocuz** |
|---|---|---|---|
| **Pipeline shape** | Adjust router → anchor match → 4-layer grade graph | `gpt-5-nano` classifier → `gpt-5.2` executor, tools loaded per class | `gemini-3.1-pro` curriculum → Flash Phase 1 → Flash Phase 2 per slide |
| **What keeps it honest** | AI picks *what* the look is; deterministic transfer bakes a 3D LUT and discards the anchor | Proposed writes are validated, then held at `awaiting_approval` until a human commits | Per-slide schema; `MAX_TOKENS` counts as failure and escalates instead of shipping half a sentence |
| **Cost control in the architecture** | 4 layers, 1 model call; a 100-clip batch is one grade; corrections route to free on-device paths | Classify once, load only that category's tools; 5 granular tools consolidated into one `mutate_*` | Route by task — Pro for one-shot cross-lesson reasoning, Flash for the ~1,500 per-slide calls |
| **Failure design** | Async grading and export jobs, cancellable | Durable phases: `classifying → executing → awaiting_approval → resuming` | Classified retries, layout demotion, 3-tier context fallback, 3 TTS providers |
| **Measured** | Per-call tokens and USD in `ai_cost_ledger`; internal AI-cost dashboard | Daily health scoring with stated inputs | `api_cost_logs` × `mrr_snapshots` = margin per generated course |
| **Consistency across surfaces** | One color spec ported to 6 renderers, held by golden-file and ~231 pixel-parity tests | One project context; discipline axis (EE/ME/SW/FW/PM/QTR) slices every artifact | Content split by language rows, not forked courses |
| **Commerce** | Perpetual licence across 9 currencies; Stripe + Apple IAP + Google Play; `active → grace → locked` enforced server-side | Stripe checkout and webhooks | Subscriptions, one-off purchases, bundles, refunds |
| **Surfaces** | Desktop, iOS, Android, web | Web | Web, 3 languages |

Each case study opens with the system diagram and a request-lifecycle sequence, then walks
through the architecture and the decisions behind it. Source code is private; the case studies
are the public artifact.

---

## Background

**Product Manager, Audio Products — ASUS** (2024–2025)
Owned wireless audio, over-ear headsets and licensed collaboration products end to end:
market requirements, IC platform and algorithm partner selection, cross-functional execution
across ID/ME/EE/FW/acoustics, NPI and pilot production, and commercial planning including
pricing, margin and demand forecasting.

**Founder & General Manager — VAUDICA CO., LTD.** (2022–2026)
Built and ran two businesses: SKINCASE, a mobile accessories brand taken through the full
physical product lifecycle from tooling to fulfillment, and FlexPresets, a photography presets
and LUT business I ran for five years and sold worldwide. Managed a six-person team, an office
and warehouse, and the acquisition funnel end to end. Fauve is the AI-native evolution of
FlexPresets.

**Founder & Director — Zyras Global Pte. Ltd.** (2026–present)
Singapore-registered company operating Fauve.

MS and BS in Electrical Engineering, National Taiwan Ocean University.

---

*I use Claude Code and OpenAI Codex daily to map systems, prototype workflows, evaluate
implementation trade-offs, and ship production changes.*
