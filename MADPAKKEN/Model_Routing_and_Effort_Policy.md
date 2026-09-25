# Model Routing and Effort Policy

**Version:** 1.3
**Status:** Stable cross-project operating policy (mechanisms only — no current model names, prices, or account state)
**Scope:** General — for any project using the Human Sandwich Model
**Basis:** Derived from an Information Buffet (formerly Critical Mass) research/evidence record for this routing revision, maintained separately, outside this package and outside this document's authority; §L additionally rests on a maintainer behavioural evaluation (2026-09-25), also maintained outside this package

---

## A. Purpose

This policy answers one question:

> **How should model capability and reasoning effort be selected for an authorized Human Sandwich downstream task?**

It does **not** answer:

> Who has authority to change meaning, scope, acceptance criteria, evidence claims, or protected state?

Human Sandwich authority is unchanged by anything in this document. **Capability does not confer authority.** A more capable model earns wider *implementation* latitude inside an authorized boundary; it never earns the authority to move that boundary.

## B. Task-granular routing

Routing is selected once, for an authorized unit of work — not independently for every internal model call.

Agentic harnesses (Codex CLI, Claude Code, and similar) fan one authorized task into many turns and tool calls. A routing decision re-evaluated per call multiplies its own overhead across every call and forfeits prompt-cache locality for no decision-relevant reason.

Do not build routine per-call model cascades that repeatedly restart from a cheap tier. Fix the (platform, model, effort) triple when the task starts. Change it only by deliberate escalation (§G), not as a background habit.

## C. The checkability partition

Divide work first by **whether a non-model deterministic oracle can decide the relevant correctness question** — not by task type.

**CHECKABLE WORK** (a deterministic oracle exists):
- deterministic validation is available and should be preferred;
- cheaper / lower-compute execution may be appropriate;
- escalate specifically when the oracle detects a failure.

**NON-CHECKABLE / JUDGEMENT-DEPENDENT WORK** (no deterministic oracle exists):
- there is no cheap, reliable failure gate;
- start at a capability/effort level whose result you are willing to defend;
- do not rely on "try cheap first" merely because it looks economical — without a gate, a cheap-first attempt has no mechanism to catch its own failure before the failure enters evidence.

**Epistemic status: `LOCAL_SYNTHESIS`.** This partition is not an established industry standard. It is a locally synthesized policy, supported by the cited mechanism families in the evidence record, and it is the part of this policy a local benchmark should test first. Preserve that status; do not let it be cited as settled practice by repetition.

## D. Deterministic oracle first

Where an exact checker can answer the correctness question, use it before buying more model reasoning.

Examples of a deterministic oracle: tests, hashes, schema validation, file existence, exit codes, protected-path checks, deterministic manifest validation, mechanically inspectable Git state (`git status`, `git diff --exit-code`).

A deterministic oracle is generally both cheaper **and** more independent than a second language model — it shares no training lineage with anything it is checking. Do not use a second model to "verify" something an exact deterministic check already decides.

## E. Difficulty-matched compute (over-effort is a real failure mode)

More reasoning effort is not automatically safer or better.

- **Under-effort** can fail from insufficient depth.
- **Over-effort** can introduce variance, cause the model to reconsider and abandon correct conclusions, increase latency, and waste allowance.
- The effort level that actually helps a given task differs across model families and task types, and does not transfer from one model to another.

Therefore:
- use the lowest effort level that produces the needed result;
- raise effort for a genuine capability need, evidenced by the task, not by habit;
- do not use maximum effort as a ceremonial safety margin;
- do not carry one model family's effort setting mechanically into another model or model generation — re-establish it deliberately when the model changes.

## F. Cost per completed task

Optimise for completed useful work, not price per token.

Account for: retries; turns/tool-call loops; context growth; cache behaviour; human interventions; the tail (a small share of tasks can carry a disproportionate share of total spend).

A cheaper-per-token model is not reliably a cheaper model — turn and token inflation can make it more expensive per completed task than a stronger model used well.

For an individual, the binding constraint is often a local allowance/rate-limit or credit pool rather than a nominal dollar price. Which resource is actually scarce is a fact to re-check against current account state when it matters, not something to encode here.

Do not cache current allowance, credit, or pricing numbers in this document. That is volatile state (§J).

## G. Escalation ladder

**Epistemic status: `LOCAL_SYNTHESIS`.** This ordering is assembled from several independent mechanism families in the evidence record; no single source states it as such. It is a prior, not a proven optimum.

- **Rung 0 — Deterministic check.** Highest independence, lowest cost, no model involved. If this answers the question, stop.
- **Rung 1 — More reasoning effort, same model, same session.** Use where the failure looks capability/depth-limited and this task type is known to benefit from more effort for this model. Not appropriate where the task's effort curve is flat or inverted (§E).
- **Rung 2 — Same model, fresh session.** Use where context drift, anchoring, or self-defence of an earlier answer may be the problem. This removes anchoring; it does not remove any model-level blind spot.
- **Rung 3 — Stronger model, same vendor.** Use where the failure appears genuinely capability-limited. Same-vendor pairs typically correlate more strongly on failure modes than cross-vendor pairs, so this rung buys capability more than it buys independence.
- **Rung 4 — Another vendor.** Use where an undetected correlated error would be consequential and difficult to reverse. This is the rung that materially reduces (not eliminates) common-mode risk.
- **HUMAN TERMINUS — not another capability rung.** Go directly to the human, without climbing, when the problem is authority-shaped rather than capability-shaped.

**Authority-shaped conditions — go straight to the human:**
- accepted meaning, scope, or acceptance criteria would change;
- an evidence or validation claim would be made or changed;
- protected state, custody, or history would be touched;
- previously recorded evidence would be overwritten or deleted;
- a fail-closed rule would be weakened;
- required information is missing and continuing would mean inventing it;
- a prior explicit human ruling would be reversed.

**Core rule: climb for capability; stop for authority.** Reaching a human-authority boundary is never resolved by climbing higher — a stronger model produces a more confident answer to a question it has no authority to answer. Escalation does not mechanically walk every rung once an authority boundary is reached; it goes directly to the human.

## H. Cross-vendor review

Encoded here as **conditions**, not as named current models — see `Model_Routing_Current_Mappings.md` for which models currently fill these roles.

**Useful when:**
- correctness is semantic / judgement-dependent and no deterministic oracle exists;
- falsification or adversarial challenge is the point;
- an undetected correlated error would be consequential or hard to reverse;
- incomplete information creates a material confabulation risk.

**Usually wasteful when:**
- a deterministic check already answers the question;
- the work is bounded, pattern-following implementation already covered by tests;
- the work is mechanical / read-only;
- it is merely a routine second opinion;
- it is being used to manufacture confidence rather than to find a fault.

**Requirements for a cross-vendor (or cross-session) review to mean anything:**
- fresh session;
- read-only review where possible;
- the reviewer does not receive the producer's private reasoning or justification;
- the reviewer receives the task contract, the actual diff/artifacts, the acceptance criteria, and the claims made — not a summary written by the producer;
- the reviewer may legitimately answer **"cannot determine from the evidence"**, and that answer must be treated as a result, not a failure.

**State explicitly, every time this is used:** a second vendor may reduce common-mode risk. It does not create statistical independence. **Two agreeing models are not a verification result.** A review that finds nothing is weak evidence of correctness, not confirmation — the reviewer and producer typically share the same task contract, so neither can find a fault that lives in the contract itself.

## I. Caching / session economics

- Preserve prompt/cache reuse where practical.
- Avoid gratuitous model or effort switching inside an active agentic task — a top-level change can invalidate session cache, and the cost of that is real, not merely inconvenient.
- Model routing decisions should not destroy cache locality without a decision-relevant reason (§B).

No vendor-specific cache figures are stored here; they belong to Routing Layers 3/4 below.

## J. Volatility / re-derivation

This policy separates four layers of routing knowledge by rate of change. **Guidance documents should not mix them.** This routing-layer numbering is local to routing and unrelated to the Human Sandwich roles Layer 1 / COULD and Layer 2 / DID.

- **Routing Layer 1 — Stable routing mechanisms.** Sections A–I of this document. Expected to remain valid across several model generations.
- **Routing Layer 2 — Current model mappings.** Which named model and effort level currently implements each role defined in Routing Layer 1. Stored in `Model_Routing_Current_Mappings.md`, dated, and explicitly marked experimental.
- **Routing Layer 3 — Pricing and credits.** Not stored in canonical routing guidance. Re-derive from current vendor/account sources when a cost decision actually depends on it.
- **Routing Layer 4 — Product and account availability.** Which models, effort levels, and context windows are actually exposed to the current account/harness. Not stored here. Re-derive mechanically (read current config/model-cache state) when needed — it changes faster than any document can track it.

**Current mappings (Routing Layer 2) must be reconsidered when:**
- a relevant new model generation appears;
- a model's behaviour or effort semantics materially change;
- a local benchmark result contradicts the mapping;
- an important platform or harness change occurs (e.g. a new default effort, a new effort level, a changed context window);
- other evidence invalidates a current mapping.

## K. Experimental — residual-judgment routing after task transformation

**Epistemic status: `EXPERIMENTAL FIELD HYPOTHESIS`.** Not an established routing law; see
`VLD_Capability_Substitution_Experimental_v0.1.md` for the full hypothesis, mechanism model,
research basis, and falsifiers. This section records only its operational consequence for
routing.

Downward routing may be considered after task transformation where consequential meaning is
already established, action authority is bounded, important failures are sufficiently
observable/discriminable, escalation remains available, and false-green/common-mode risk is
acceptably controlled.

> Route on residual unbounded judgment after transformation, not on the original task label
> alone.

Counterweight: oracle-poor, semantically open-ended, novel, authority-heavy, or
difficult-to-check work should not be routed downward merely because a VLD workflow exists.

This section does not define current vendor/model mappings — see `Model_Routing_Current_Mappings.md`,
which is unaffected by this addition.

## L. Role-specific conformance for state-changing DID work — provisional

**Epistemic status: provisional.** Derived from one maintainer evaluation (2026-09-25; evidence
record maintained outside this package). Not an established standard.

**Suitability is role-specific.** It is judged by observed behaviour, not by marketing tier,
price, parameter count or presumed intelligence. Bounded assistance is not DID conformance: a
model can be adequate for Layer 1, or for bounded and reversible help, while failing what
state-changing DID work needs.

State-changing DID work can outlive the executor's working context through compaction,
summarisation or truncation. Before such work is routed to a model, that model should have been
observed to:

- **F1** — after lossy context loss, fail closed for state-changing work when no durable
  work-order authority survives (`Human_Sandwich_DID_Context.md` §11);
- **F2** — not fabricate or launder records, tokens, authority or state to satisfy a
  prerequisite after the fact;
- **F3** — when candidate session records conflict, report the discrepancy rather than choosing
  one and acting;
- **F4** — with the DID starter (`README.md` → "DID starter (Layer 1 → a fresh DID)"), ground in
  the canonical foundation before its first mutation.

A model not observed to meet F1–F4 is not demonstrated for that work, whatever its performance on
bounded tasks.

**No Layer 1 floor is established.** The Layer 1 bootstrap failures observed in the same
evaluation did not recur with the official launcher (`README.md` → "Copy this into a fresh
Layer 1") in that evaluation's small samples; they appear interface-caused, not demonstrated
capability limits.

**This section names no models.** Dated observations of concrete models against F1–F4 belong in
`Model_Routing_Current_Mappings.md`, and change as models and harnesses change.
