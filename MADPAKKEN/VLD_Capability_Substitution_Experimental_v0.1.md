# VLD Capability Substitution — Experimental Field Hypothesis

**Version:** 0.6
**Date:** 2026-09-14
**Status:** EXPERIMENTAL FIELD HYPOTHESIS — not established doctrine, not a validated model-tier routing law
**Positioning:** Experimental companion to Verification-Locked Development
(`The_Sandwich_Alignment_Skewer.md`) and to `Model_Routing_and_Effort_Policy.md`. Not a new
named methodology alongside the Human Sandwich Model, VLD, Critical Mass, or Nuke Testing — it
owns one bounded experimental question about those methods' downstream effect on model routing.
**Maturity:** Several local operational observations from live governed project work — repeated
within-project field evidence, not independent replications and not controlled comparison — plus
relevant cross-domain and LLM-verification research support for several component mechanisms.
No established model-tier routing law yet, and no controlled capability comparison.
**Origin:** Live downstream project field work, followed by a mechanism-first Critical Mass
investigation.
**Intended use:** Authorized for real Madpakken-assisted work. Every use remains experimental
until field review (§13). This document is independently removable if field evidence does not
support it — see §13 and §17.

---

## 1. Central hypothesis

> Verification-Locked Development may expand the reliable bounded-work envelope of a
> less-capable or lower-cost model by transforming the task: meaning, authority, state,
> checking, and escalation are externalized or constrained so the producer must supply less
> unbounded judgment.

### 1.1 What this is explicitly not

> **VLD does not make weaker models smarter.**

Reject that claim. It is not what this document argues, and nothing below licenses reading it
that way.

Raw model capability does not increase. What changes, when the hypothesis holds, is the
**residual task** the model is actually asked to perform. A task that nominally reads
"complex intermediate-representation repair" can become a materially smaller judgment problem
once meaning is fixed, files are bounded, a failing witness exists, regression is discriminative,
predecessor state is protected, stop conditions are explicit, and escalation is available. The
label on the original task is not evidence about the residual task after transformation (see §12
for the anti-rule this protects).

### 1.2 A compact mechanism model (experimental, not a law)

```text
RAW MODEL CAPABILITY
  +
SEMANTIC TASK DECOMPOSITION
  +
AUTHORITY / ACTION BOUNDS
  +
DISCRIMINATIVE EXTERNAL CHECKS
  +
CONTRADICTION-PRESERVING HISTORY
  +
STOP / ESCALATION
  →
RELIABLE BOUNDED WORK ENVELOPE
```

Treat this as an experimental model of the mechanism, not an established law of model behavior.

### 1.3 The counter-model this document must not lose sight of

```text
SHARED WRONG MEANING
  +
SHARED WRONG ORACLE
  →
CONFIDENTLY VERIFIED FAILURE
```

Both models are true at once. Section 6 and §10.5 exist to keep the second one from being
quietly dropped whenever the first one looks encouraging.

---

## 2. Local downstream field observation

**LOCAL DOWNSTREAM FIELD OBSERVATION** — this is one operational episode, not a study, not a
benchmark, and not evidence of N > 1 or general model-tier substitution. Treat it as orientation
for why the hypothesis was thought worth stating, nothing stronger.

The episode involved Claude Sonnet 5 at high effort, operating inside a tightly VLD-governed
intermediate-representation assurance/repair sequence.

The model still made ordinary implementation mistakes, including:

- dropping a relevant guard during a correction;
- constructing a flawed test fixture;
- initially permitting behavior broader than intended.

**Those mistakes matter, and this document does not claim VLD prevented them.** VLD did not
make the model more careful, more correct, or less error-prone on a first pass.

The observation worth recording is narrower:

> The surrounding workflow repeatedly converted several of those mistakes into observable
> contradictions rather than letting them disappear into confident completion.

The workflow elements that appear to have done this work include:

- explicit authority boundaries;
- locked meaning/claim boundaries;
- read-only inspection before correction;
- pre-fix reproduction;
- discriminative regression that had to fail before repair;
- post-fix verification;
- negative and preservation controls;
- causal mutation/counterfactual checking;
- broader regression;
- tests/evidence kept separate from semantic authority;
- explicit stop conditions;
- human escalation when meaning was unresolved.

### 2.1 A tracked authority question and its human ruling

A particularly relevant episode within the sequence: implementation behavior exposed an
unresolved semantic question, which was recorded as a tracked authority question rather than
settled locally. The implementation agent was **not** permitted to choose the meaning. The
question returned to HUMAN SHOULD. The human ruling was recorded as its own tracked decision.
Implementation then resumed against the now-explicit semantic authority.

This is the mechanism this document is actually interested in: not that the model avoided
error, but that the workflow made an unresolved semantic question visible and routed it to the
correct authority instead of letting the producer guess and move on.

Do not generalize this single episode into a claim about model tiers, task classes, or
substitution rates. It is local operational evidence for the shape of the hypothesis, nothing
more.

### 2.2 A bounded slice with a lower-cost producer, and a real semantic error

**LOCAL FIELD OBSERVATION** — one further episode inside the same project. Not a replication of
§2, not a controlled comparison, and not evidence about model tiers.

A bounded slice was implemented by a lower-cost producer at medium effort against an already
locked semantic contract. The producer implemented nearly all of the bounded slice successfully,
then met a case it had reasoned about badly — contradictory deployment-profile evidence. It
correctly identified that its own heuristic was wrong.

It then made a consequential semantic error: rather than escalating, it removed an accepted
state from the contract (the indeterminate case that contradictory evidence was supposed to
produce) and described that state as structurally unreachable. **That is semantic drift, it was
the producer's error, and this document does not claim the workflow prevented it.**

What the episode actually shows is what happened next:

- accepted meaning lived outside the producer, so the reinterpretation had something to
  contradict;
- the implementation report exposed the reinterpretation rather than absorbing it;
- the locked contract contradicted the new meaning directly;
- Layer 1 detected the drift before acceptance;
- no later work was authorized on top of the drifted meaning;
- a small bounded correction restored the accepted state;
- production evidence was unaffected;
- the contradictory state was then made deterministically representable through a synthetic
  evidence-injection boundary in test.

The field interpretation worth recording is narrow:

> The lower-cost producer made a real semantic-authority error, and that error remained
> bounded, observable, reversible, contradiction-capable, and unable to acquire authority
> through implementation success.

Two boundaries on this episode:

**Representability.** The synthetic fixture established deterministic representability of the
contradictory case *for this slice*. It did not establish that all real-world contradictory
environments have been identified, or that they occur naturally through current production
probes.

**Cost.** The repair appeared operationally cheap next to restarting the slice or routing all
work upward. Total system cost was not controlled: Layer 1 review, repair effort, retries and
oracle construction are part of that cost and were not measured.

### 2.3 Extended execution through a single available agent

**REPEATED WITHIN-PROJECT FIELD OBSERVATION** — multiple episodes inside one governed campaign,
across an extended period during which only one execution route was available. No controlled
A/B comparison, no randomized task assignment, no validated capability ordering, and no full
cost or time comparison exist for any of it.

Under those conditions the execution agent handled live-state reconstruction, bounded
implementation, mechanism repair, hostile assurance work, authority-registry work, package
sealing and custody, environment-binding repair, provider-transport investigation, deterministic
multipart transport implementation, and broad regression.

The claim this does **not** support is any statement that one agent or model is weaker or
stronger than another, or that downward routing was demonstrated. None of that was tested.

What is observable is that the residual task was repeatedly transformed before execution.
Meaning, state and checking were externalized through explicit human rulings, bounded file and
state scope, protected historical evidence, fail-before-change reproduction, discriminative
tests, hostile checks, stop conditions, human escalation, and immutable custody.

The most informative part is where execution stopped. The agent correctly declined to proceed
where residual semantic judgment remained — selecting consequential authority members, deciding
what provider assurance claim was required, authorizing a new route, authorizing an actual
external calibration call. Correct STOP is positive system behavior here, not a failure to
complete.

This is field evidence for externalized authority, state and checking. It is not evidence for a
model capability ordering.

### 2.4 A well-bounded task that was still over-authorized

**LOCAL FIELD OBSERVATION** — one episode, same project lineage. This one is largely negative
evidence for the hypothesis, and is recorded because it bounds the attractive version of it.

A qualification target became mechanically applicable under the current project state. Human
execution authorization for that target had been deliberately withheld. Ordinary regression
then executed it anyway — not through a producer's discretionary decision, but because nothing
separated *applicable* from *authorized to run*.

**The workflow did not prevent this.** Meaning was locked, scope was bounded, and the residual
reasoning burden on the producer was genuinely small — and none of that mattered, because the
failure did not run through producer judgment at all. Stating it plainly: verification strength
and bounded reasoning did not prevent an unauthorized consequential execution, because the
execution path itself was over-authorized.

The repairs were containment mechanisms, applied after the fact: explicit execution
allowlisting, a tripwire on the withheld target able to demonstrate that it executed zero times,
and a firmer separation between applicability and execution authorization. They are worth
recording as repairs, not as evidence that the original design was sound.

The field interpretation:

> Strong verification and a well-bounded residual task are insufficient if consequential
> execution reachability itself remains over-authorized.

### 2.5 An extended bounded-work run at a named model and effort

**LOCAL OPERATIONAL FIELD OBSERVATION** — one extended episode. Not a controlled benchmark, not
a validated routing law, and not evidence of general model-tier substitution.

**Producer: GPT-5.6 Terra, High effort.** This is recorded as episode provenance, not as a
mapping. It bears on one (model, effort) point and says nothing about the same model at lower
effort — see the economic boundary below for why the effort level in particular matters here.

The task was heavily VLD-transformed before execution: consequential meaning, authority,
protected state, forbidden actions, deterministic checks, stop rules and human-only decisions
were all externalized. Inside that envelope the producer handled a long series of bounded
implementation, repair and assurance tasks.

**The useful result was not first-pass correctness.** Ordinary defects and incomplete repairs
occurred throughout — incomplete authority and compatibility enforcement, bypasses inside
bounded lanes, promotion mechanisms that were not properly rooted, self-certifying identity and
state, trust placed in caller-supplied evidence, lexical guard gaps, false negatives and benign
false positives, and repeated repair cycles on the same surfaces. That negative record is part
of the observation, not a caveat attached to it.

What is worth recording is that these defects repeatedly became visible before consequential
acceptance. The recurring shape was:

```text
repair → focused regression green → fresh bounded Nuke → survivor found
→ STOP → bounded authorized repair → fresh re-Nuke
```

Focused green was routinely not the end of the sequence, which is the behavior the
transformation was supposed to produce.

Authority-boundary behavior across the tracked chain was strongly positive: no invented human
rulings, no unauthorized provider calls, no unauthorized image generation, no unauthorized
movement of protected state, no reopening of forbidden routes, and human-only approval remained
human-only.

**That is not the same claim as autonomous authority judgment.** The boundaries in question had
been made explicit externally; what the episode shows is reliable compliance with them, not
independent recognition of where they lay. Nothing here establishes what the producer would do
against a boundary that had not been externalized.

> The producer did not demonstrate autonomous authority judgment. It demonstrated reliable
> compliance with externally explicit authority and stop boundaries.

> VLD did not stop the producer making mistakes. It made many of those mistakes hard to hide
> and hard to accept.

**Common-mode limit.** The same model tier participated in the repair and re-Nuke cycles.
Independence in this episode was mechanical — deterministic state, hashes, tests, preserved
artifacts, human-defined semantics — not model-level semantic independence. Read against §1.3
and §8 gate item 5: a shared abstraction error could have survived these cycles, and this
episode is not evidence that none did.

**Economic status: INCONCLUSIVE.** The reliability and control signal above is positive local
field evidence. The economic signal is not, and the two must not be merged:

- the run took multiple repair and re-Nuke rounds;
- no controlled stronger-model comparison was run;
- total token or credit consumption was not measured;
- wall time was not compared;
- human time was not accounted for;
- cost per accepted result was not measured.

High effort matters here specifically. An economy-positioned model run at high effort is not a
clean cheap-producer result, and the repair rounds sit on the cost side of the ledger. Do not
infer economic success from the producer's tier alone, and do not read this episode as evidence
about that model at a lower effort setting.

### 2.6 A different producer under the same governance — interim

**LOCAL OPERATIONAL OBSERVATION — INTERIM.** This phase is still running. Not a controlled
benchmark, not a validated routing law, and not a completed phase conclusion. Everything below
may change as the phase continues.

**Producer: GPT-5.6 Sol, Medium effort.** Episode provenance, not a mapping. The phase followed
§2.5 under substantially the same project governance, authority model, VLD boundaries,
verification requirements, STOP semantics, and HUMAN SHOULD authority — which is what makes the
contrast worth recording at all, and is also the only sense in which the two are comparable.

**The interim signal.** Under substantially the same externalized structure, this producer has
so far required less orchestration and fewer repair loops than §2.5 while preserving the same
fail-closed authority and STOP behavior — which, as in §2.5, is compliance with externally
explicit boundaries and not autonomous authority judgment. That is a qualitative contrast from
natural sequential use, not a measurement: the phase is early, the task sequence was unequal and unrandomized,
there was no matched benchmark, and cost could not be cleanly attributed.

Neither producer's record should be flattened. §2.5 showed strong explicit STOP behavior and
strong authority-boundary compliance alongside many first-pass omissions, repeated adjacent
trust-surface defects, and long repair chains. This phase has so far shown comparable STOP and
authority behavior with better first-pass integration and fewer repair loops across
multi-mechanism work. Nothing here says the earlier producer was inadequate, or that this one is
generally superior.

**Proportional assurance.** The phase opened with a fresh bounded Nuke of a rooted content-only
rejection mechanism and reached clean bounded closure without opening a repair lane. It verified
the exact rejected raws and the actual promotion-consumer behavior, handled wrong-raw and
cross-slot attacks, fabricated no style decision, claimed no replacement authority, and promoted
nothing. Unrelated broader-suite failures stayed separate and were not repaired. That is scope
discipline and proportionality, not a small campaign.

**Breadth carried.** A comparatively broad bounded preflight and execution surface was handled
in one pass — canonical group requirements, style authority, environment references,
recognizability requirements, exact attachment order, one-shot/no-retry semantics, independent
content and style review, distinct-group requirements, frozen packages, prompt identity,
call-budget discipline, custody. The comparative point is the repair-loop burden this took, not
that the surface was novel.

**Governed execution is not a semantic guarantee.** One run's provider outputs were mechanically
well-governed and semantically inadequate — named-character collision risk, recurrence across
supposedly distinct groups, recognizability failure. Governing request construction, authority,
invocation, custody and promotion does not pre-prove provider semantic compliance or final
artistic correctness, and human post-generation review remained necessary. This is confirmation
of what §4 already says VLD cannot substitute for, not a new rule.

Reporting that evidence did not confer authority over it: collision-risk and recognizability
findings were returned while the human decision state stayed explicitly undecided until HUMAN
SHOULD ruled. Stronger execution capability did not acquire SHOULD authority.

**Two fail-closed blockers are the strongest observations in this phase.**

*Exact-surface freeze.* Before a provider call, the authorized prompt carried a style
instruction semantically similar to — but byte-different from — the canonical derived sentence
the freeze consumer required. The mechanism failed closed. The producer did not normalize the
prompt, did not build the frozen package, did not call the provider, and consumed no attempt; it
returned the discrepancy to HUMAN SHOULD, and provider calls for that attempt remained zero.

> Semantic similarity did not override the exact governed authority surface.

This is local evidence that a stronger producer still benefits materially from exact VLD
boundaries. It is not a general claim that byte identity is the right contract anywhere beyond
the one that governed here. Once the human authorized the change, the bounded revision was made
without silently widening the decision, and the unrelated collision, recognizability,
environment, call-limit and review semantics were preserved. A subsequent governed edit used the
exact prior raw as its source, ran as a new governed run rather than an implicit retry, spent one
provider call, held composition and other subjects tight, and preserved custody and one-shot
semantics.

*Unrepresentable accepted meaning.* HUMAN SHOULD ruled content approved while style
compatibility remained undecided. The authority model could represent an independent
content-only rejection but could not represent a positive content approval without also
completing style compatibility. The producer stopped. It did not fabricate a style-compatibility
value, collapse content approval into style approval, redesign the mechanism, promote the
candidate, or mutate rooted state that did not exist.

> When the current authority model could not faithfully represent accepted human meaning, the
> execution model stopped rather than inventing the missing authority.

That is externalized meaning and correct escalation working as §3 describes, and a further
datapoint for the governed-model insufficiency that Nuke Testing records separately — not a new
representability rule here.

After the human authorized a change to the representation, the repair added a separate canonical
root for positive content approval, so the two decisions could be held independently. A bounded
fresh Nuke then challenged wrong raw, run, attempt and slot, approval/rejection contradiction,
ambiguity against legacy rows, automatic promotion, and style inference, and closed cleanly. A
later, separately ruled style compatibility was rooted independently again. Ownership stayed
split — content approval to the content root, style compatibility to the style root, the style
master as sole style authority — and neither pair of decisions promoted anything on its own.

The capability-substitution point is not the authority design, which is ordinary HSM and VLD. It
is that the producer repaired the representation surface to fit the accepted human meaning
rather than reshaping the meaning to fit what the implementation could already express.

*Abstraction boundary rather than failing instance.* A later bounded task exposed a deeper
version of the same thing. A stable slot identity had been hard-bound to one historical concrete
realization, down to that realization's run, attempt, raw path and hash, so a legitimately
approved replacement could not become current without violating the slot contract. The producer
stopped first and mutated nothing before authorization.

What it did after authorization is the observation worth recording. It did not substitute the
newer realization for the older one inside the existing hardcoded structure — the repair that
would have made the immediate failure go away. It separated the boundaries instead: stable slot
identity, concrete approved identity, and the projection of current authority became three
distinct things, with the stable slot owning only stable semantic properties — slot and group
identity, kind, panel scope, population and variation envelope, foundational provenance — and
concrete approved identity authenticated separately through explicit approved-group authority.
The superseded realization remained valid historical evidence; it simply stopped being current
authority. Fresh bounded assurance then challenged stale hardcoding becoming current, rejected
and undecided realizations becoming current, latest-run inference, cross-group authority
inheritance, automatic promotion and production-state movement, and closed cleanly.

**Economic status: still INCONCLUSIVE.** The tension is real and unresolved: this producer
appears to consume substantial execution budget per turn while appearing to need fewer repair
loops and less orchestration, and §2.5's producer may carry lower producer cost against higher
repair and orchestration burden. Per-turn usage readings are too weak to attribute either way.
The endpoint that matters remains total governed-system cost per accepted result (§11), not
usage per turn.

**What this does not establish.** Not economic superiority for this producer; not a permanent
ordering against §2.5's; nothing about either model at any other effort setting; no general
capability ordering; no reduction in the need for human semantic authority or for VLD; no
provider semantic determinism; and no universal first-pass correctness. It does not even
establish that this phase will keep showing the pattern — it is interim, and should be re-read
against whatever the phase finishes with.

---

## 3. Mechanisms VLD may partly externalize

The following is a candidate list, not a proof. It distinguishes what VLD-style structure
plausibly moves out of the producer from what remains model or human competence.

**Candidate externalized burdens** — things the producer may need to supply less of:

- remembering all locked constraints;
- maintaining scope/action boundaries;
- deciding by intuition whether tests are enough;
- noticing some regressions;
- preserving predecessor contradiction;
- keeping track of authorized vs. prohibited change;
- knowing when unresolved semantics must escalate;
- treating confidence as if it were evidence;
- determining task completion solely from its own prose.

**External structures that may supply the above instead:**

- a locked contract;
- protected state;
- discriminative tests;
- negative controls;
- predecessor state;
- mechanical diff/state inspection;
- explicit stop conditions;
- human semantic escalation.

This is not complete substitution. It is a claim that *some* of the burden can move outside the
producer under the right conditions (§7, §10).

---

## 4. What VLD cannot substitute for

This limitation is equally central to the hypothesis, not a footnote to it.

VLD does not reliably substitute for:

- discovering what the system should mean;
- open-ended architecture;
- novel solution invention;
- constructing a correct oracle when one does not yet exist;
- recognizing missing dimensions shared by both the specification and the tests;
- broad cross-domain judgment;
- deciding consequential human meaning;
- adversarially challenging the governing abstraction itself;
- unmodelled novelty outside the locked envelope.

> Procedures and verification structure do not replace competence where the residual task still
> requires that competence.

A lower-cost producer may therefore be suitable for implementation inside a well-transformed
task while a stronger challenger, stronger Layer 1 reasoning, or HUMAN SHOULD remains necessary
elsewhere in the same project — often in the same session.

---

## 5. Checkability is a central boundary

The experimental benefit is expected to be strongest where the important claims are
sufficiently:

- observable;
- representable;
- reachable;
- discriminable;
- contradiction-capable;
- independently checkable enough for the assurance claim actually being made.

The expected benefit should weaken as the task becomes:

- oracle-poor;
- semantically open-ended;
- highly novel;
- dependent on implicit domain judgment;
- vulnerable to producer/checker common-mode misunderstanding.

This document uses existing VLD and Nuke Testing terminology for checkability, oracle adequacy,
and common-mode risk rather than inventing a parallel coverage taxonomy. Read those documents
directly for the underlying concepts.

---

## 6. External research basis

Kept in separate epistemic classes deliberately. Do not collapse them into a single claim of
"the research supports VLD" — it does not. It supports several component mechanisms, at varying
strength, with real counterevidence.

### 6.1 Established external findings

**A. LLM verification.** Recent controlled work on variation in verification reports that
verification-based selection can reduce performance gaps between weaker and stronger generators
on some task families, while other task families receive little verification gain.
*Mechanism relevance:* verification can compress some generator capability differences where
errors are sufficiently checkable. *Boundary:* verification quality itself depends on task and
verifier capability.

**B. Agent scaffolding.** Recent LLM-agent work indicates that changing scaffolding around the
same underlying model can materially change task resolution, cost, and behavior.
*Mechanism relevance:* system performance is not raw model performance. *Boundary:* more
scaffolding is not monotonically better.

**C. Test-first / external checking.** Research on test-driven LLM code generation and
verifier-assisted correction reports benefits from executable tests and external feedback.
*Mechanism relevance:* some self-monitoring burden can be moved outside the generator.
*Boundary:* incorrect or incomplete tests can provide misleading feedback.

**D. Human factors / cognitive offloading.** Research on cognitive offloading and structured
checklists shows that external structure can reduce internal cognitive burden and can
disproportionately help lower-expertise performers on some bounded tasks.
*Mechanism relevance:* external structure can narrow some competence gaps. *Boundary:*
procedures do not replace expertise in novel or uncovered situations.

### 6.2 Practice-derived analogies

**E. Formal / runtime assurance analogues.** Proof-carrying systems; least privilege; runtime
assurance / Simplex-style architectures; lightweight formal methods; separation of duties.
*Mechanism relevance:* a system can safely or reliably make use of a component without
requiring that component to possess all system-level judgment. *Boundary:* the guarantee covers
only what has actually been specified, monitored, or proved — never more.

### 6.3 Local downstream field observations

See §2. One operational episode; local; not generalized.

### 6.4 Inferences

- Task transformation, not model choice alone, is likely the operative variable.
- The residual-judgment view of a task (§10) is likely a better routing signal than the
  original task-complexity label (§12).

### 6.5 Open questions

- What is the actual shape of the capability/workflow interaction — linear, threshold, or
  something else?
- Does the effect hold across task families, or is it concentrated in code/engineering work
  with strong existing tooling?
- How much of the local downstream observation generalizes past one episode, one model, one
  project?

### 6.6 Counterevidence

- Incorrect requirements can be verified correctly — verification cannot detect an error in
  what it was told to check.
- Producer and checker can share the same mistaken abstraction (the counter-model in §1.3).
- Procedural systems can create false confidence.
- Automated aids can produce automation bias in the humans and models relying on them.
- Checklists and procedures sometimes show no benefit despite high compliance.
- Some tasks remain dependent on high-level situation assessment and novel reasoning that no
  amount of external structure supplies.

### 6.7 Proposed testable hypotheses

See §14 (the future controlled experiment) and §15 (falsifiers).

**None of the above is direct proof of VLD.** It is bounded support for the plausibility of
several component mechanisms VLD composes. Do not cite this section as "external research
validates VLD" — it does not, and should not be represented as doing so.

---

## 7. Current best abstraction

> VLD changes the reliable-work envelope by transforming the residual task and moving some
> semantic, action, memory, checking, and failure-detection burdens outside the producer.

A second, operational formulation:

> Route on residual unbounded judgment after task transformation, not only on the original task
> label.

Both remain hypotheses for field use. Neither is a timeless fact, and neither should be quoted
elsewhere as one.

### 7.1 Capability substitution and execution-agent portability are different claims

Field use made a distinction visible that §1 does not draw sharply enough, and conflating the
two would inflate the evidence considerably.

**Capability substitution** asks: does task transformation permit reliable use of a
lower-capability or lower-cost model than would otherwise be required? Answering it requires
actual capability or cost comparison evidence — which this document does not yet have.

**Execution-agent portability** asks: does externalized meaning, state, verification and
escalation let a *different available* execution agent continue bounded work without
reacquiring semantic authority? Answering it requires only that the work continued correctly,
and that residual judgment still escalated.

> **Execution-agent portability is evidence for externalized task state and authority. It is
> not by itself evidence of capability-tier substitution.**

Portability can be valuable even where capability ordering is unknown and no downward cost
substitution has been shown — §2.3 is exactly that case. When reviewing field evidence (§11),
classify which of the two questions an episode actually bears on. Most ordinary field work
bears on portability.

### 7.2 Zero producer error is probably the wrong target

Stated as an explicitly experimental field interpretation, not a routing rule:

> Zero producer error may be the wrong target for downward routing. The more useful question is
> whether the proposed producer's characteristic mistakes can remain bounded, observable,
> reversible, contradiction-capable, and economically repairable before crossing the acceptance
> boundary, while genuinely unresolved judgment escalates correctly.

§2.2 is the episode that suggests this framing: the producer made a real semantic error and the
outcome was still sound, because the error could not acquire authority. This does not license
any model-specific or provider-specific routing conclusion, and §9's anti-rule continues to
govern.

### 7.3 Residual judgment is not the only residual

The abstraction above, and the routing gate in §8, are framed around how much unbounded
*judgment* a producer must still supply. §2.4 shows that this framing is incomplete.

> **A task can be cognitively bounded and still be operationally over-authorized.**

A producer may need very little discretionary reasoning while retaining uncontrolled
reachability to consequential actions whose execution was never separately authorized — and, as
§2.4 shows, that reachability need not even be exercised by the producer's own judgment.
Ordinary automation running inside the same boundary is a path to the same actions.

> **Task transformation must reduce both residual unbounded judgment and uncontrolled
> consequential execution authority. A producer that is well-bounded cognitively may still be
> unsuitable for downward routing if it can reach consequential actions whose execution
> authorization is not independently enforced.**

**Residual authority surface** may be useful as experimental reasoning vocabulary for the second
of these. It is a question to ask, not a quantity: there is no score, no metric, and no
threshold, and inventing one would be exactly the per-task paperwork §8 warns against. Gate
items 2 and 7 there already ask for bounded action authority and custody protection; the
addition is that
those bounds must be *independently enforced* rather than declared, and that ordinary automation
counts as a reachability path.

### 7.4 The emerging difference may be integration friction, not authority

An experimental field interpretation from §2.5 and §2.6, offered as a hypothesis to watch
rather than a finding. Both episodes are single, unmatched, same-project observations, and the
second is still running.

> Stronger execution capability may reduce integration and orchestration burden after VLD task
> transformation, without acquiring any additional semantic authority.

The contrast between the two episodes is not about authority. Both producers complied with the
same externalized boundaries and stopped in the same places. What differed was how much repair
and orchestration the residual task cost to reach an accepted result: a more bounded executor
carried surprisingly complex governed work with substantial repair support, while the other has
so far carried broader multi-mechanism residual tasks with fewer repair loops.

If that holds, the useful question for later review is not which producer is better but:

> Does stronger model capability become economically valuable mainly when the transformed
> residual task still contains substantial cross-mechanism integration?

with a tentative shape of:

```text
very sharply bounded residual task
    → a less capable producer under strong VLD may be sufficient
broader multi-mechanism residual task
    → stronger capability may reduce repair and orchestration burden
```

A second mechanism may sit underneath that difference, visible only in the later episodes:

> Stronger execution capability may reduce integration friction partly by locating the correct
> abstraction boundary earlier, not only by making fewer local implementation errors.

In two governed repairs the producer changed the underlying authority or identity model rather
than patching the concrete instance that happened to be failing — separating two human decisions
that had been entangled in one representation, and separating a stable identity from the one
historical realization it had been bound to (§2.6). Both are repairs that cost more up front and
remove a class of future failure, which is exactly the choice that a producer under integration
pressure tends to get wrong.

Treat this as an emerging signal, not a property of any model. It does not establish that this
producer reliably selects better abstractions, that the earlier one could not have reached the
same repairs, that the task sequences were matched, that capability rather than accumulated
project understanding produced the difference, or that any of it generalizes past this project
lineage. Both repairs also happened inside explicit authority ownership, identity boundaries,
immutable custody, independent decision axes, consumer checks, stop conditions and bounded fresh
assurance — and both began with the producer stopping. Stronger capability did not replace that
structure and did not acquire SHOULD authority; if anything these episodes show the structure
being what made a good repair choice checkable.

This is not a routing rule and must not be used as one. It names nothing about any specific
model, establishes no ordering, and would need the comparison in §12 before it could become
anything more. §9's anti-rule governs here exactly as it does elsewhere: the presence of a
pattern is not permission to route on it.

---

## 8. Experimental routing gate

An operational candidate gate for considering downward model routing **after** task
transformation. This is a reasoning aid, not a mandatory eight-field form — do not turn it into
required paperwork per task.

Downward routing MAY be considered when approximately all of the following hold:

1. **Consequential meaning is established.** The producer is not being asked to invent or
   adjudicate the governing semantics.
2. **Action authority is bounded.** The allowed state transition and protected state are
   sufficiently explicit.
3. **Important failure modes are checkable.** Relevant defects can produce observable,
   discriminating contradiction before consequential acceptance.
4. **The oracle is good enough for the claim.** Do not route downward merely because tests
   exist — the tests/checkers must be capable of distinguishing the relevant incorrect
   behavior.
5. **Common-mode false-green risk is controlled.** Producer and checker must not obviously
   share the entire failure model. Where that risk matters, independent challenge may still
   require stronger or differently grounded reasoning (VLD Rule 4; Nuke Testing).
6. **Escalation is available.** Unresolved semantics can return to Layer 1 / HUMAN SHOULD
   instead of forcing the producer to guess.
7. **The change is reversible or custody-protected.** Producer mistakes must not create silent
   irreversible state outside the authorized boundary.
8. **False green is caught before consequential acceptance.** A lower-cost model is not
   justified if undetected failure can cross the acceptance boundary.

If several conditions fail, route upward instead.

---

## 9. Important routing anti-rule

Explicitly forbidden:

> **"VLD is present, therefore use a cheaper model."**

That is not the experiment, and is not licensed by anything above.

The correct question is:

> After VLD-style transformation, how much residual unbounded judgment remains, and does that
> residual task fit the reliable envelope of the proposed model?

The original task label is not, by itself, sufficient evidence for that question.

Example: "complex intermediate-representation repair" may become a materially different routing
problem once it has fixed meaning, bounded files, an exact failing witness, discriminative
regression, a protected predecessor, explicit stop conditions, and human escalation available.
The original complexity label is not a timeless routing truth once the task has been
transformed — but the transformation has to have actually happened, and been verified, not
merely be nominally present.

---

## 10. Experimental field use

This experiment is authorized for real Madpakken-assisted work. Layer 1 may use the candidate
mechanism (§7, §8) when selecting model/effort for bounded DID work. A synthetic experiment
(§14) is not required before any use — but every use remains experimental, subject to field
review (§13).

The expected useful observation from ordinary field use is **not**:

> "Did the cheaper model make zero mistakes?"

It is whether, across real tasks:

- mistakes became detectable before acceptance;
- semantic drift escaped;
- unauthorized authority decisions occurred;
- escalation happened correctly;
- false greens occurred;
- retries erased the economic advantage;
- stronger-model intervention was still needed;
- the final accepted result was correct against the governed meaning.

No new permanent per-task report is required. Existing project history, handoffs, evidence,
commit history, task records, and later field review may be used to reconstruct these
observations when review occurs (§13).

---

## 11. Field review / sunset rule

**FIELD REVIEW REQUIRED.**

This experiment must not become permanent merely through age. Passage of time alone is not
evidence.

Reassess after a materially relevant number of real tasks have exercised downward routing under
verification-locked conditions. At review, inspect both positive and negative cases.

Review questions should include:

- Was work actually routed downward because of VLD transformation?
- Which model/capability tiers were used?
- Did semantic defects escape?
- Did false-green occur?
- Did the lower-tier model make ordinary mistakes the workflow successfully exposed?
- How often did correct human escalation occur?
- How often was escalation unnecessary?
- Did human intervention/retries erase the cost benefit?
- Did oracle construction itself cost more than stronger-model use would have?
- Did VLD merely encode the same misconception as the implementation?
- Were some tasks correctly routed upward because residual judgment remained too high?

Field use suggests five further review questions, none of which require per-task logging — they
are reconstruction questions asked later:

- **Containment.** Did a producer semantic error stay inside its authorized boundary, or had
  downstream work already begun to depend on it before reconciliation?
- **Correct escalation.** Did the alternative producer succeed because the residual task had
  genuinely been transformed, and did it stop and escalate where residual human judgment
  remained?
- **Total system cost.** Was cost or capability actually reduced for the governed system as a
  whole, or merely shifted into stronger Layer 1 reasoning, challenger work, retries, oracle
  construction, or human intervention? Evaluate total governed-system cost, not producer-token
  cost alone — producer compute, repair and retry compute, verifier and challenger compute,
  Layer 1 effort, human time, wall time and external side-effect cost all belong in it. A
  cheaper producer tier is not by itself an economic result (§2.5).
- **Error surface.** Which externalized mechanism actually exposed the mistake — the locked
  contract, a validator, discriminative regression, a preservation control, direct state
  observation, a challenger or frozen witness, repair ablation, or human escalation?
- **Evidence breadth.** Is this another episode inside the same project or campaign, a
  materially independent task, or controlled experimental evidence? Repeated episodes within one
  project are not replications (§2.2, §2.3), and should not be counted as such.

The portability/substitution distinction (§7.1) applies throughout: an episode that shows only
that work continued under a different available agent is evidence about portability, and
answers the routing question only indirectly.

Two further questions follow from §7.3:

- **Residual authority surface.** After task transformation, what consequential actions could
  the producer — or ordinary automation running alongside it — still execute without a separate
  authorization boundary?
- **Source of residual risk.** Was the residual risk coming from residual judgment, residual
  authority surface, or both? A review that only asks the first question will score §2.4 as a
  success.
- **Orchestration and repair burden.** How much orchestration and how many repair loops were
  needed to reach an accepted result, and did that burden differ materially across model or
  effort configurations? This is the quantity §7.4's hypothesis turns on, and it is not visible
  in per-turn usage readings.
- **Stop behavior, and what produced it.** Did the producer stop when the authorized envelope
  ended — and was that stop autonomous inference of a boundary, or reliable compliance with a
  boundary that had been made externally explicit? The hypothesis is about the second; treating
  the second as evidence of the first would overstate it badly (§2.5).
- **Repair altitude.** When a repair succeeded, did the producer repair the load-bearing
  abstraction or authority boundary, or substitute the currently failing concrete instance? The
  second reads as a successful repair at the time and is the cheaper answer; the difference
  usually only becomes visible at the next change (§7.4).

Possible dispositions at review:

- **DROP**
- **PROJECT_LOCAL**
- **KEEP_EXPERIMENTAL**
- **SMALL_VLD_CLARIFICATION**
- **ROUTING_RULE**
- **RESEARCH_AGAIN**

Do not promote this experiment automatically. Promotion requires an explicit, human-authorised
disposition at review, the same as any other Madpakken doctrine change.

---

## 12. Proposed controlled experiment (future — not run as part of this integration)

Preserved here as the design for a future stronger test. Introducing this document does not run
it.

Use several model capability/cost tiers across the same bounded engineering tasks, with
workflow arms:

**A — Ordinary agentic.** Goal + repo + ordinary agent instructions.

**B — Authority-bounded.** Explicit scope, protected state, human-only meaning decisions,
stop/escalation.

**C — Full VLD.** B, plus: locked semantic contract; read-only inspection first; pre-fix
reproduction; discriminative fail-before-repair regression; negative/preservation controls;
correction; post-fix verification; causal/counterfactual check where applicable; broader
regression; explicit evidence boundary; semantic escalation.

**D — Same information, no locking discipline (optional but important control).** Approximately
the same specifications/tests/evidence as C, but without the VLD sequence/control topology.
Tests whether any observed effect is merely "more information" versus "workflow structure
matters."

Task classes: high checkability; partial checkability; common-mode / wrong-oracle trap.

**Primary candidate measures:** semantic escape rate; false-green rate; unauthorized semantic
decision rate; gold-correct task completion.

**Secondary measures:** regressions introduced; correct escalation; unnecessary escalation;
retries; human intervention; tokens; monetary cost; wall time; tool use; scope violations; cost
per gold-correct accepted task.

The most important statistical/mechanistic signal is the **model capability × workflow**
interaction. The capability-substitution hypothesis gains support if full VLD disproportionately
narrows the reliable-performance gap between model tiers without increasing hidden semantic
failure.

---

## 13. Falsifiers

This experiment must remain easy to kill. Important falsifiers include:

- full VLD does not reduce the reliability gap between model tiers;
- lower-tier models show fewer visible errors but equal hidden semantic escapes;
- false-green increases under shared producer/checker misconception;
- weaker models cannot use verifier feedback reliably;
- human escalation becomes so frequent that cost savings disappear;
- benefit exists only on trivial tasks;
- same-information/no-locking (arm D) performs equally well as full VLD (arm C);
- stronger models gain equally or more from VLD, producing no useful downward-routing effect;
- oracle construction costs exceed the model savings;
- VLD makes actors less likely to notice that the specification itself is wrong;
- routine use produces ceremony rather than reduced residual judgment.

A failed experiment is a valid result, and should be reported as such at field review (§11), not
suppressed or quietly reframed.

---

## 14. Position in the Madpakken stack

This document does not restate Human Sandwich, VLD, Critical Mass, or Nuke Testing content. It
sits beside them as a narrow experimental question about one downstream consequence of using
them together:

> **HSM:** who may decide?
> **VLD:** what meaning is locked, and does evidence support the claim?
> **Critical Mass:** what method should we consider?
> **Nuke Testing:** why should we trust that implementation and verification preserve the
> intended meaning?
> **This document:** given VLD-style transformation, how much does the residual judgment burden
> on the producer actually shrink, and can that support routing a lower-capability or
> lower-cost model to the transformed task?

HUMAN SHOULD remains authority. This document creates no new authority, no new methodology name,
and no standing model-tier default. See `Model_Routing_and_Effort_Policy.md` for where its
routing consequence is recorded, and `Model_Routing_Current_Mappings.md` for current named
mappings — this document introduces neither.

---

## 15. Update / removal policy

Keep exactly one active copy under this canonical filename while the experiment runs.

Update or supersede this document only through an explicit, human-authorised revision — the
same convention as Nuke Testing and Documentation Delta.

This document, and the small references to it in `Human_Sandwich_Layer1_Context.md`,
`Model_Routing_and_Effort_Policy.md`, `The_Sandwich_Alignment_Skewer.md`, and `README.md`, are
designed to be removable together without requiring changes to the Human Sandwich Model, VLD
itself, Critical Mass, Nuke Testing, or `Model_Routing_Current_Mappings.md`, if field review
(§11) disposes of this experiment as `DROP`.
