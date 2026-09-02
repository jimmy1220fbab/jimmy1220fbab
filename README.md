# Jimmy Wang

**AI Product Manager.** I ship AI products as complete commercial systems — the generative
pipeline, the deterministic guardrails that make it safe to sell, the payment and entitlement
layer, and the growth loop that feeds it.

Previously PM for audio products at ASUS, where I owned hardware from IC platform selection
through mass production. Before that I founded and ran a consumer products company for four
years — 40,000+ paying customers, NT$60M+ cumulative revenue, a six-person team, and up to
NT$500K/month in performance marketing that I owned end to end.

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

The interesting part of an AI product is rarely the model call. It is everything that has to
be true before you can charge money for the output. All three products have the same five
layers — which is the argument that this is a method, not three lucky shots.

| | **Fauve** | **Zyras** | **Vocuz** |
|---|---|---|---|
| **AI pipeline** | Intent router → anchor match → grade graph | Classifier → executor, with dynamic tool loading | Curriculum planner → per-slide generation → media |
| **Determinism guardrail** | AI decides *what* the look is; deterministic color code decides *how* to land it | Proposed writes are validated, then paused for human approval before they commit | Structured schema per slide; truncated output is treated as failure and escalated |
| **Failure handling** | Async grading and export jobs, cancellable | Durable job phases that resume after approval | Classified retryable errors, exponential backoff, model escalation, multi-provider TTS fallback |
| **Unit economics** | Per-account AI usage metering and an internal AI-cost dashboard | — | Per-model pricing table; every generation is costed and written to a ledger, paired with MRR snapshots |
| **Commerce** | Stripe, Apple IAP and Google Play billing, each with server-to-server notifications | Stripe checkout and webhooks | Stripe subscriptions, one-off course purchases, bundles, refunds |
| **Growth loop** | Retention and win-back crons, ad-spend sync | Daily project health and digest notifications | Behavior profiles → segments → lifecycle email → ad audiences → back to acquisition |
| **Surfaces** | Desktop, iOS, Android, web | Web | Web, 3 languages |

Each case study opens with the full system diagram for that product, then walks through the
decisions that shaped it. Source code is private; the case studies are the public artifact.

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
and LUT business sold worldwide. Managed a six-person team, an office and warehouse, and the
acquisition funnel end to end. Fauve is the AI-native evolution of FlexPresets, built on that
customer base.

**Founder & Director — Zyras Global Pte. Ltd.** (2026–present)
Singapore-registered company operating Fauve.

MS and BS in Electrical Engineering, National Taiwan Ocean University.

---

*I use Claude Code and OpenAI Codex daily to map systems, prototype workflows, evaluate
implementation trade-offs, and ship production changes.*
