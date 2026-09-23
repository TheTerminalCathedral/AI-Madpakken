# Model Routing — Current Mappings

**Status:** EXPERIMENTAL
**Valid as of:** 2026-09-07
**Basis:** a Critical Mass research/evidence record for this routing revision, maintained separately outside this package — it carries the full evidence, source families, and reasoning behind every row below.
**Applies the mechanisms defined in:** `Model_Routing_and_Effort_Policy.md`

---

## What this document is

This is the Madpakken maintainer's (Dan Almer Jensen's) **current routing prior** — the specific (platform, model, effort) choices that currently implement the stable policy — **not doctrine, and not a locally proven optimum.**

- It is a prior to be tested against Dan's own workload, not a measurement of it. No local benchmark has been run.
- It is a **maintainer reference prior, not the preferences or routing defaults of every human using Madpakken.** "Dan" below means the maintainer's own configuration and workload. A human using the package applies the stable policy to their own workload, accounts and tools, and may use this prior only as a dated starting point to re-check.
- Effort labels are **not equivalent across vendors.** "High" on Codex and "high" on Claude Code are different quantities of computation, set against different per-model defaults. Never read a label across the platform column.
- Benchmark-style comparisons cited below run each model inside its own vendor's harness (Codex or Claude Code) — they are not harness-normalised model-vs-model comparisons. They are used here only because Dan also uses each model inside its own vendor's harness, which is the quantity he actually experiences.
- Where two models are listed as alternatives, they are genuine alternatives, not a ranking.
- **A benchmark or vendor observation agreeing with another does not make either claim proven.** Cross-vendor agreement is corroboration, not verification (see `Model_Routing_and_Effort_Policy.md` §H).

## Before using this mapping

Re-check live, at time of use — do not trust this document for any of the following:

1. **Does the named model still exist**, under this name or slug, in the current product?
2. **Is it available in the current account/product tier** being used?
3. **Which effort levels does the actual harness expose** for that model right now? (Harness-exposed effort levels have previously differed from a vendor's own API documentation for the same model.)
4. **Has a newer model generation superseded this mapping?**

None of these facts are re-derived by reading this document. Check current local tool/account state directly.

## Models in scope and their distinguishing role

**OpenAI / Codex**
- **Luna** — mechanical, checkable, repetitive work, where a model is needed at all. Nano-tier positioning.
- **Terra** — bounded ordinary implementation/edit work as an economy option. Mini-tier positioning — a more aggressive economy choice than its name alone suggests.
- **Sol** — analysis, reasoning, and research work, where Astra's agentic premium is not justified. Reported near-parity with Astra on general-intelligence scoring at meaningfully lower per-task cost.
- **Astra** — long-horizon, terminal, tool-rich, computer-use, and demanding agentic execution. **Not a universal Codex default.** Its measured advantage is concentrated specifically in this class of work, not in analysis/reasoning generally.
  - **Residual uncertainty (U6, unresolved):** whether `low` or `medium` effort is the better Codex default for Dan's actual task mix. The product default is `low`; Dan's current configuration runs `medium`; practitioner evidence leans toward `low` for review-style tasks and `medium` for agentic coding. **This mapping preserves `medium` as Dan's current practical setting because it is his existing deliberate configuration, not because it has been shown to be empirically optimal for him.** Resolving this requires a small local comparison (not run; not authorized by this document).

**Anthropic / Claude**
- **Sonnet 5** — suitable for bounded, pattern-following work. **Not established by the underlying research as a cheap universal Claude default** — independently measured at a higher cost per completed task than Opus 5 on one benchmark, from turn/token inflation rather than price.
- **Opus 5** — the ordinary high-capability Claude DID default: implementation, debugging, research/synthesis, architecture, and other work where semantic reasoning matters.
- **Fable 5.1** — a specialist option for a specific, named, exceptionally hard or long task. **Not a standing default** — it carries plan-level rationing and a behaviour (a refusal-classifier stop condition) that can interrupt long autonomous runs; how often that matters for Dan's own work is unmeasured.

---

## Current mapping by role

Effort levels are per-platform; do not compare a Codex effort label to a Claude effort label as though they measured the same thing.

| Role | Platform / model | Effort | Viable alternative | Escalate when | De-escalate when | Rationale (short) | Evidence / status |
|---|---|---|---|---|---|---|---|
| **Mechanical worker** — retrieval, inventory, mechanical/read-only inspection, high-volume repetitive checkable work | Codex — Luna (or no model, where a deterministic check suffices) | low | Terra, low | output stops being uniform, or the result needs interpretation | — | Nano-tier retrieval needs no judgement; prefer the shell wherever it can answer exactly | Vendor positioning + local observation. Confidence: high |
| **Bounded ordinary implementation** — edits inside an existing pattern, covered or coverable by tests | Codex — Terra, **or** Claude Code — Sonnet 5 | medium | Astra, low; Opus 5, medium | architecture must change, or the diff spreads across modules | pattern is fully mechanical → drop a tier | Mini-tier Codex model reported near-parity with Sonnet 5 on repository coding; checkable by tests either way | One secondary-sourced benchmark, not independently verified. Confidence: medium |
| **Ordinary DID executor** — general implementation, debugging with a reproducing test, bounded change | Claude Code — Opus 5 | high (platform default) | Codex — Astra, medium | a second bounded attempt fails, or ambiguity surfaces | routine and test-covered → medium | Vendor guidance (which argues against its own more expensive multi-model pattern) plus a measured step-down to `medium` at roughly half the cost for a small accuracy loss | Vendor-measured, self-critical. Confidence: medium-high |
| **Researcher / synthesist** | Either platform — Opus 5 **or** Sol | medium | Fable 5.1, low | conclusions conflict across sources | — | Research-task effort curves are close to flat; `medium` matches higher-effort accuracy at a fraction of the cost. Astra is explicitly the wrong choice here — Sol reportedly matches it on general capability at meaningfully lower cost | Vendor-measured + independent evaluation. Confidence: high |
| **Long-horizon / terminal / computer-use agent** | Codex — Astra | medium (Dan's current setting — kept, not proven optimal; see residual uncertainty above) | Claude Code + browser/computer tools; Fable 5.1, xhigh (rationed — reserve for a named hard task) | boundary ambiguity appears → **stop and go to the human; do not escalate the model** | — | This is Astra's clearest measured differentiator: long-horizon, tool-rich, computer-use work, at markedly better token efficiency than the alternatives | Independent evaluation + vendor-reported (self-evaluating; weighted accordingly). Confidence: medium |
| **Routine reviewer** | Opposite platform from the task's author, fresh session | low–medium | — | a real finding appears → re-run that area at high effort | — | Review accuracy is reported to hold at lower effort levels; cost/latency rise steeply for a small increase in findings at high effort | Vendor-measured + single practitioner run (n=1). Confidence: medium |
| **Adversarial / evidence-critical reviewer** | Opposite **vendor** from the task's producer, fresh, read-only session | high–xhigh (never below the level you would defend) | — | contradictory evidence appears, or an irreversible claim is at stake → **human** | never de-escalate below defensible | Only a vendor switch materially reduces (not eliminates) common-mode risk; a same-vendor fresh session removes anchoring but no shared blind spot | `LOCAL_SYNTHESIS`, from two research families that disagree on magnitude (residual uncertainty U3, open). Confidence: medium |
| **Architect** — design/architecture, semantic interpretation, requirements ambiguity | Claude Code — Opus 5 | high → xhigh | Codex — Sol, high | several plausible designs carry materially different downstream cost, **or** the interpretation would change accepted scope/meaning → human, not more effort | one clearly correct design → step back to high | Reasoning-ceiling work: each effort step is reported to buy real accuracy, with no free reduction available | Vendor-measured. Confidence: medium-high |

**Two defaults this mapping deliberately does not adopt** (both against the researcher's own initial expectation, per the evidence record):
- **Sonnet 5 as a cheap default.** If the goal is lower-cost Claude work, the evidenced lever is Opus 5 at lower effort, not a smaller model.
- **Fable 5.1 as any standing default.** Reserve it for a consciously chosen, named hard problem.

## Named supersession / revisit triggers

Re-derive this mapping (not just its values, its rows) when:
- a new relevant model generation appears on either platform;
- a local benchmark result contradicts a row above;
- an important platform/harness change occurs (new default effort, new effort level, changed context handling);
- the checkability-partition policy itself (`Model_Routing_and_Effort_Policy.md` §C) is invalidated by evidence;
- a scheduled vendor pricing/availability change occurs. *(Example only, not stored as policy: the evidence record notes one Codex-side promotional price was stated as valid only through 2026-11-21 — the date is not itself a routing rule, it is why pricing is never cached here at all; re-derive current pricing/availability separately, from live sources, whenever a cost decision depends on it.)*

## What this document deliberately omits

No current dollar prices, no Codex credit rates, no Claude plan-usage percentages, no account allowance/credit state, no CLI/product versions, no promotional terms, no context-window product configuration, and no plan-specific limits. Those are Routing Layer 3/4 facts (`Model_Routing_and_Effort_Policy.md` §J) — re-derive them live; do not expect this file to carry them.
