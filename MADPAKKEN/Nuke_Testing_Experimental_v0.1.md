# Nuke Testing — Contract-Driven Adversarial Assurance

**Version:** 0.7  
**Date:** 2026-09-22  
**Status:** EXPERIMENTAL — practice-derived working method; not an established named methodology  
**Positioning:** Experimental method in the Human Sandwich / AI Madpakken family  
**Primary audience:** Humans and LLMs working on consequential software, engineering, research, automation and AI-assisted systems  
**Maturity:** Usable for bounded experiments and governed project work; not yet ready to be presented as externally validated doctrine

---

## 1. Purpose

**Nuke Testing** is an experimental assurance method for work that is too consequential to trust merely because ordinary implementation checks are green.

Its purpose is not to maximize test count.

Its purpose is to challenge whether confidence in a result is actually justified.

The core question is:

> **Can the system become confidently wrong while all of its ordinary checks still look reasonable?**

Examples include:

- a human decision being attached to state the human did not approve;
- a valid human decision being silently lost after a semantic no-op;
- persistent identity changing even though the governed meaning did not;
- stale state surviving a material evidence change;
- provenance appearing complete because a contributor was omitted;
- a replay system reproducing an illegal history perfectly;
- a verifier agreeing with production because both share the same mistaken assumption;
- a coverage model reaching 100% while an important property was never represented;
- several AI agents independently sounding confident while sharing the same prior conclusion.

Nuke Testing treats these as **assurance failures**, not merely ordinary test failures.

Its working principle is:

> **Lock the meaning. Derive falsifiable claims. Attack the implementation and the assurance model through heterogeneous mechanisms. Repair causes, not examples. Verify the verification. Preserve failures. Re-anchor after repair. Stop when further attacks no longer add materially independent evidence against the remaining risk.**

Nuke Testing does not promise proof of correctness.

It aims for:

> **bounded, inspectable, adversarially challenged assurance.**

---

## 2. Experimental Status

Nuke Testing is currently **EXPERIMENTAL**.

It is practice-derived from consequential AI-assisted engineering work and has evolved through repeated real failures, repairs, verifier failures, independent challenge and assurance-closure attempts.

It must not currently be described as:

- an industry standard;
- a scientifically validated named methodology;
- a formal verification method;
- a safety certification framework;
- a substitute for domain-specific qualification;
- proof that a system is correct.

A correct current description is:

> **Nuke Testing is a practice-derived experimental assurance method that composes established verification, validation, adversarial testing, falsification, mutation, stateful testing, independent review and assurance ideas into an LLM-compatible workflow for challenging high-consequence semantic claims.**

Its individual techniques have substantial precedent.

Its particular composition, terminology, sequencing, governance structure, LLM execution model and stopping doctrine are local synthesis.

The method should remain versioned and explicitly experimental until broader use and external research justify stronger claims.

---

## 3. Position in the Madpakken Stack

Nuke Testing is intended to sit beside, not replace, the other methods.

### Human Sandwich Model — Authority

Human Sandwich asks:

> **Who may decide meaning?**

A useful shorthand is:

> **COULD → SHOULD → DID**  
> **AI → HUMAN → AI**

The human retains authority over consequential meaning.

### Verification-Locked Development — Meaning

VLD asks:

> **What meaning is locked, and did implementation preserve what was authorized?**

A useful shorthand is:

> **Vibe the implementation. Lock the meaning.**

Implementation freedom does not grant semantic authority.

### Critical Mass — Method Discovery

Critical Mass asks:

> **What mechanism are we actually dealing with, where else has it appeared, and which field-tested responses can transfer?**

It is used to discover and challenge candidate methods before inventing locally.

### Nuke Testing — Assurance

Nuke Testing asks:

> **What evidence justifies trusting that the locked meaning survives implementation, interaction, persistence, repair, failure and verification?**

Together:

> **HSM:** Who may decide?  
> **VLD:** What meaning is locked?  
> **Critical Mass:** What method should we consider?  
> **Nuke Testing:** Why should we trust that the implementation and verification actually preserve the intended meaning?

A compact sequence is:

> **Authority → Meaning → Method → Assurance**

Nuke Testing must never acquire authority to invent missing meaning.

If testing discovers that the governing semantics are genuinely underspecified:

> **HUMAN_RULING_REQUIRED**

—not “make the test pass.”

---

## 4. When to Use Nuke Testing

Nuke Testing is not required for every task.

It is most appropriate when one or more of these are true:

- silent semantic failure could be consequential;
- human authority is represented in persistent state;
- identity, provenance or lineage must survive reconstruction;
- historical correctness matters, not merely final output;
- failure can remain internally coherent;
- multiple mechanisms interact across time;
- validators may share implementation assumptions;
- a normal green test suite is insufficient assurance;
- a repair changes a mechanism on which prior assurance depends;
- an external or independent review is expected to carry real evidentiary weight;
- the cost of false confidence is materially higher than the cost of deeper challenge.

Examples may include:

- persistent engineering representations;
- authorization systems;
- evidence pipelines;
- safety-related control logic;
- data lineage;
- migration tooling;
- regulated or auditable workflows;
- critical infrastructure software;
- financial state transitions;
- high-consequence automation;
- AI-assisted systems that preserve human decisions or claims.

---

## 5. When Not to Use It

Do not invoke a full Nuke campaign merely because testing is possible.

Ordinary validation may be sufficient for:

- trivial presentation changes;
- bounded low-consequence utilities;
- reversible local experiments;
- deterministic transformations with strong existing oracles;
- changes whose failure is obvious and cheap to correct;
- work where additional assurance has no plausible decision value.

Nuke Testing must be proportional.

A methodology that requires maximum ceremony for every change becomes a process defect.

The correct result may be:

> **NUKE_NOT_JUSTIFIED_FOR_THIS_SCOPE**

A Nuke campaign should exist because of a meaningful assurance question, not because the method is available.

---

## 6. Core Shift: Claims Before Tests

Nuke Testing begins from **governed claims**.

Not from:

- code coverage;
- existing test files;
- current implementation behavior;
- the producer's explanation;
- a previous LLM's summary.

Examples:

> A tool cannot establish human-only authority.

> A semantic no-op preserves persistent engineering identity.

> A valid human decision remains effective while its governing evidence is semantically unchanged.

> A material change in governing evidence invalidates dependent state when the contract requires it.

> Uncertainty remains explicit until legitimate evidence or human authority resolves it.

For every critical claim, record at least:

```text
CLAIM:
<what must be true>

AUTHORITY:
<what establishes the intended meaning>

CONSEQUENCE:
<why failure matters>

FALSIFIER:
<what observation would refute the claim>

EXPECTED EVIDENCE:
<what evidence should support it>

INDEPENDENCE REQUIREMENT:
<how common-mode verification will be limited>

KNOWN ASSUMPTIONS:
<what the claim depends on>

RESIDUAL RISK:
<what remains outside the assurance boundary>
```

The central question is:

> **What observation would make us stop believing this claim?**

If no falsifier can be stated, the claim is probably not ready for a Nuke campaign.

---

## 7. Tests Are Evidence, Not Authority

A test suite can demonstrate behavior.

It does not automatically define intended meaning.

Therefore:

> **Green tests are evidence, not authority.**

When a test expectation conflicts with accepted authority, possible outcomes include:

- product defect;
- test defect;
- oracle defect;
- fixture defect;
- authority ambiguity;
- environment problem;
- accepted limitation.

Do not silently choose whichever interpretation produces green output.

Nuke Testing requires **adjudication against authority before repair**.

---

## 8. The Five-Level Coverage Distinction

A central experimental Nuke distinction is:

> **Representable ≠ Reachable ≠ Exercised ≠ Observed ≠ Verdict-influential**

These are different assurance questions.

### Representable

Can the test model express the relevant state or failure at all?

A generator cannot test a state its model cannot represent.

### Reachable

Can legal operations actually reach the state?

A representable object may be unreachable through valid product behavior.

### Exercised

Did the campaign actually execute a path that reaches the relevant state?

Potential coverage is not executed coverage.

### Observed

Did the instrumentation expose the relevant consequence?

A failure can occur without the oracle observing the important semantic fact.

### Verdict-influential

Could the observed fact actually change PASS/FAIL/INCONCLUSIVE?

A checker may collect information that never affects its verdict.

This distinction prevents false assurance such as:

> "The field exists in the checker, therefore the checker verifies it."

or:

> "The generator supports that operation, therefore that lifecycle state was tested."

For every high-risk assurance claim, challenge all five levels where relevant.

### Gaps attach to claims, not to attacks

A gap at any of the five levels is not an unexecuted test. It limits a specific assurance claim: the one whose relevant failure mode could not be represented, reached, exercised, observed or made verdict-influential.

> **A representability gap attaches to the assurance claim it limits, not to the attack that could not be run.**

Three consequences follow.

Unrelated passing evidence does not compensate. A claim whose relevant failure mode the harness cannot represent is not supported by tests of other properties, by attack counts, or by coverage totals.

The count of affected attacks is not the count of distinct gap mechanisms. One unrepresentable state can block many predeclared attacks, so an attack-instance count overstates how many independent problems exist.

Predeclared attacks the evidence surface cannot represent are not assurance. A large frozen attack model is a plan; only executed attacks are evidence.

A live gap on a consequential claim therefore requires one of:

- expanding the evidence or harness surface until the failure mode is representable;
- narrowing the claim to what the surface can support;
- or recording that claim as INCONCLUSIVE or explicitly limited, naming the gap;
- or removing the need for the claim, by making the hazardous condition impossible in the
  execution context rather than establishing its absence in the subject.

Leaving it in a report as a coverage statistic is none of these. The fourth option changes what
is being claimed rather than how well it is evidenced, and is governed below.

### Partial exercise is not whole-oracle PASS

A single oracle may carry several claims or clauses, and an authorized phase may only be able to
exercise some of them. Partial exercise is a normal, legitimate situation. Promoting it into an
aggregate PASS is not.

> **Where an oracle is only partly exercisable in the current authorized state, record evidence
> at the claim or clause level it actually covers, and preserve the unexercised remainder as
> explicitly still owed. The aggregate oracle remains unresolved — INCONCLUSIVE or explicitly
> limited (§8) — until the remaining clauses become applicable and are exercised.**

What is preserved for an unexercised clause is normally small: what it still requires, what
condition would make it exercisable, and that it remains owed. Clauses that are genuinely
inapplicable in the current state are still not PASS; they are unexercised, and the reason is
part of the record.

This does not require every oracle to be decomposed into clauses. It applies where a real
oracle already has separable claims and only some are currently reachable.

### A conservative default needs a route out of itself

An owed remainder that nothing can ever discharge is a permanent claim wearing a temporary
label. Where unknown or unevidenced work is conservatively routed into an expensive or
restricted disposition, that population only grows, and the pressure it creates lands on the
gate rather than on the evidence.

> **Where work is routinely held by a fail-closed default, there should be an evidence-producing
> route by which a held subject can earn the cheaper treatment. The absence of such a route does
> not make the estate safer — it makes weakening the gate the only available relief.**

The route produces evidence for the claim actually at stake. Relaxing admission because the held
population became inconvenient is the failure this is meant to prevent, not an instance of it.

### Consequential non-execution should be observed, not inferred

Sometimes the load-bearing claim is negative: *this mechanism must not have run*. That claim
still has to reach the Observed level, and absent downstream artifacts are a weak way to get
there — missing reports, outputs or traces are also consistent with an execution that failed,
was redirected, cleaned up after itself, or wrote somewhere unexamined.

> **Where non-execution is itself a consequential assurance claim, prefer direct observation or
> instrumentation at the execution boundary over inferring non-execution from absent downstream
> evidence. Absence of evidence of execution is not evidence of non-execution.**

Instrumentation that can demonstrate *executed 0 times* turns a negative inference into an
observed fact. This is the Observed level applied to a negative claim; it changes none of the
five levels' meanings.

Keep it proportional. This is not a requirement to instrument every action — it applies where
"this consequential mechanism must not have executed" is itself load-bearing to the assurance
claim, typically because execution authority was deliberately withheld.

### A condition can be made true by the context instead of proved about the subject

Some blocking conditions are not properties of the subject at all. They are properties of the
context the subject runs in — and where that is so, the subject-level question can be
unanswerable and unnecessary at the same time. Field use reached this the hard way: a detector
that could only ever be PARTIAL was being asked to establish that a subject did *not* exercise a
hazardous mechanism, a planted-state experiment established that the method could not support
that claim at all, and the resolution was neither a weaker detector nor a more elaborate one.

> **Before building a stronger absence detector, ask whether the hazardous condition can be made
> impossible in the execution context. Establishing a condition by construction and establishing
> a property of the subject are different claims, and the first does not license stating the
> second.**

Three truths must then stay separate, because collapsing any two of them produces a result that
reads stronger than its evidence:

- **what the subject can do** — its capability, which the context does not change;
- **what condition holds in the execution context** — stated in the terms of the hazard, not in
  the subject's terms;
- **by which mechanism that condition became true** — different mechanisms establish different
  condition sets, so one flag cannot stand for two of them.

> **Do not restate a neutralised hazard as an absent or inapplicable capability. Record the
> capability as it is, the condition as context-established, and the mechanism that established
> it.**

A capability the context neutralises has not become inapplicable. Rewriting it as such destroys
the record that the capability is still present and that only the context is holding the hazard
down — which is exactly what a later change to the context needs to find.

Two bounds apply, and both are load-bearing.

*Scope.* A condition quantified over a population is not established by covering part of that
population.

> **Where a condition is population-scoped, it is established only when every concurrently
> relevant participant is covered by the mechanism claimed to make it true. An absence of
> observed violation is not that mechanism.**

This says nothing about which mechanism, and does not imply one uniform execution environment.
Several mechanisms may cover one population, provided each carries an explicit guarantee and
nothing concurrently relevant falls outside all of them.

*Reach.* A mechanism discharges the conditions that follow from it and no others. A mechanism
that removes concurrency discharges concurrency conditions; it does not discharge hazards that
were never about concurrency. Subjects held for an independent reason must keep being held for
that reason, and must say so.

> **A correct disposition reached through a false reason is still a defect wherever reason codes
> feed later authority, automation or reuse.**

This is not a licence to construct a claim into existence. Construction changes what is being
claimed, and the new claim carries the same obligations as any other: it must be stated, its
mechanism must be attacked with working controls (§17), its observation fidelity must be measured
rather than assumed (§12), and it expires with the context it rests on (§23).

---

## 9. Three Layers Must Be Challenged

Nuke Testing distinguishes at least three layers.

### Layer A — Implementation correctness

Question:

> **Does the implementation satisfy a known semantic property?**

Examples:

- a no-op preserves identity;
- stale promotion is rejected;
- a tool cannot perform a human-only transition.

### Layer B — Verification-system adequacy

Question:

> **Would the assurance machinery detect a violation of that property?**

Examples:

- would the history checker reject an authority-destructive no-op?
- would the completeness oracle detect omitted uncertainty?
- would a deliberate critical mutant be killed?

This is **verification of verification**.

### Layer C — Assurance-model completeness

Question:

> **Did we identify the important property in the first place?**

A campaign can achieve:

> **100% coverage of the declared assurance model**

while still omitting a property nobody encoded.

Therefore:

> **Coverage closure is closure relative to a model. It is not proof that the model is complete.**

At least selected high-consequence campaigns should include a mechanism that attempts to derive important expectations independently of the internal assurance model.

### Governed-model insufficiency is a distinct failure

A consequential assurance failure is not always "the implementation is wrong" or "the harness
could not reach it". It can be that the governed product or authority model has no state in
which the distinction verification needs to enforce can be expressed at all.

> **Assurance can also fail because the governed authority or product model lacks a
> representable semantic state needed to express the intended claim. This is distinct from a
> harness being unable to represent, reach or exercise an otherwise expressible product state.**

The two are diagnosed differently. A harness limitation (§8, Representable) is repaired by
extending the evidence surface; the product's own meaning is unchanged. A governed-model
insufficiency is not repairable by better testing at all — the missing distinction has to be
added to the governed model, and deciding what that distinction means is a HUMAN SHOULD
question, not a challenger's to invent (§21).

A field example: an authority model could bind artifact identity, population bounds and
permitted variation, but had no way to express which observable properties were authoritative
and which were incidental. No harness improvement could close that; the claim the verification
was supposed to enforce had no representable form in the governed model.

Do not read this as a rename of the §8 coverage levels. Representable, Reachable, Exercised,
Observed and Verdict-influential keep their existing meanings, all of which concern the
assurance surface rather than the governed model.

### Non-authoritative does not mean unconstrained

A related governed-model error runs the other way. Establishing that an artifact is
*non-authoritative* for some property is often correct — and is then misread as establishing
that the property is unconstrained.

> **Non-authoritative means an artifact does not confer authority over that property. It does
> not mean the property is free. A separate authority owner may still impose requirements on
> it.**

Three questions that are easy to collapse and should be kept apart:

- **authority** — which artifact decides what this property must be;
- **compatibility** — what this property must still satisfy with respect to that authority;
- **authority transfer** — whether satisfying a requirement makes the satisfying artifact an
  owner of it.

> **Compatibility with an authority does not transfer ownership of that authority.**

A field example: a reference could correctly be non-authoritative for visual style, which was
then treated as making rendering style arbitrary. It was not — style remained subject to
compatibility requirements owned elsewhere.

This is not a general rule that every non-authoritative property is constrained; most are not.
It is a challenger question to ask where a non-authoritative finding is about to be used to
justify unconstrained behavior.

---

## 10. Semantic Coverage, Not Test Count

Nuke Testing does not treat raw test count as assurance depth.

Useful semantic dimensions may include:

- authority;
- lifecycle;
- identity;
- source transition;
- evidence state;
- ambiguity;
- lineage;
- provenance;
- custody;
- acceptance;
- promotion;
- persistence;
- concurrency;
- topology;
- uncertainty;
- human-decision preservation;
- invalidation cause;
- no-op / stutter class;
- failure/recovery state.

A campaign may define:

- mandatory bins;
- important pairwise crosses;
- selected higher-order crosses;
- excluded regions;
- reasons for exclusion.

The purpose is not to enumerate the universe.

The purpose is to make the assurance model inspectable.

A closure report should distinguish:

```text
coverage_of_declared_assurance_model = PASS/FAIL/INCONCLUSIVE

assurance_model_completeness_challenged = PASS/FAIL/INCONCLUSIVE
```

These are not the same claim.

---

## 11. Preservation and Invalidation Must Be Symmetric

Many verification systems aggressively test:

> **When evidence changes, does dependent state become stale?**

That is only half the property.

For consequential human or persistent state, derive both:

### Invalidation property

> **Material governing change must invalidate dependent meaning when the contract requires it.**

### Preservation property

> **Semantically unchanged governing evidence must not invalidate still-valid human or persistent meaning.**

A system that invalidates too little can preserve stale falsehood.

A system that invalidates too much can erase legitimate authority.

Both are semantic failures.

This symmetry should be considered for:

- human decisions;
- identity continuity;
- accepted state;
- attached evidence;
- lineage;
- promotion;
- provenance;
- persistent classifications.

### Load-bearing evidence must not become silently erasable

A third relation sits beside the two above. Evidence required to justify an authority
transition can be present and valid when the transition is accepted, and then be removed later
while the authority it justified stays accepted.

> **Where current authority still depends on lineage or evidence required to justify it, that
> dependency must not be silently erasable while the derived authority remains accepted.**

The challenger question is:

> **Can authority survive the removal of evidence that is still required to justify it?**

This is not a rule that provenance must grow monotonically forever. Evidence can legitimately be
retired, archived or superseded. The narrow property is that removing *still load-bearing*
evidence must either fail closed or invalidate the authority that rests on it — not leave an
accepted state whose justification no longer exists.

---

## 12. Semantic Stutter / Metamorphic Preservation

Some operations are mechanically active while semantically inert with respect to selected governed facts.

Examples may include:

- byte-identical re-ingestion;
- serialization followed by faithful deserialization;
- irrelevant source edits outside a dependency boundary;
- deterministic recomputation from unchanged authority inputs;
- representation-only changes where accepted authority defines meaning as unchanged.

For each such relation:

```text
BEFORE:
<protected semantic projection>

TRANSFORMATION:
<mechanically active but semantically inert operation>

AFTER:
<protected semantic projection>

REQUIRED:
AFTER == BEFORE
for every fact declared invariant under this transformation
```

Do not require every byte or metadata field to remain identical.

Define the protected projection semantically.

This is especially valuable when the internal implementation is complex but the expected relation between executions is simple.

### Durable identity must survive system evolution, not only single executions

The relations above compare two executions of one system. The same preservation question applies
across a change to the system itself, and field use found it easier to get wrong there.

When a durable or recoverable operation gains an optional capability, the path that does not use
that capability is a semantically inert transformation in exactly the sense above — and its
canonical identity is one of the facts that should survive it.

> **When a durable or recoverable operation gains an optional capability, challenge whether the
> legacy default path still produces the same durable identity. New capability fields must not
> perturb that identity while the capability is unused, unless the identity change is itself
> intended and governed.**

The failure this prevents is not a syntax incompatibility. A journalled request made before the
upgrade, retried afterwards with the same semantic content, can hash differently once new keys
are emitted on the default path — producing a spurious conflict against its own earlier
identity, with both sides behaving exactly as written.

The same question reaches the canonicalization rules themselves:

> **Canonicalization is a load-bearing semantic invariant wherever durable identity depends on
> it. Where the input is semantically unordered, equivalent orderings should not produce
> different durable identities unless ordering is part of the governed meaning.**

This is not a rule that every collection must be sorted, and it does not apply where identity is
not derived from the serialization. It applies where a structure the governed meaning treats as
a set is being hashed as a sequence.

Both are one question asked at evolution time: *which facts is this change supposed to leave
alone, and is durable identity one of them?*

### Moving work into a different execution context is one of these transformations

Moving verification work into an isolated context, a different host profile, or any other
altered execution environment is a mechanically active operation asserted to be semantically
inert with respect to what the work observes. That assertion is exactly the relation above, and
the protected projection is what the subject sees.

> **Where verification work is moved into a different execution context, observation preservation
> is a measured property, not an inherited one. A result obtained in the new context is the same
> result only for the facts declared invariant under the move, and only where that invariance was
> actually checked.**

Field use found roughly one node in ten diverging under a candidate context that had been
expected to be transparent. Nothing but running the estate inside it would have shown that, and a
context that changes what the product does is not a cheaper way to obtain the same evidence — it
is a different observation wearing the old label.

---

## 13. Attack Proxies, Not Only Branches

Serious failures often arise when an implementation uses a convenient proxy for a deeper semantic fact.

Examples:

- identifier equality used as proof of same derivation;
- actor metadata used as proof of human authority;
- replay equality used as proof of semantic validity;
- absence of contradiction used as proof of confirmation;
- filename used as custody identity;
- object similarity used as persistent continuity;
- production completeness state reused as independent completeness evidence.

For every high-risk invariant ask:

> **What implementation signal is standing in for the real semantic fact?**

Then attempt to construct a condition where:

> **proxy ≠ semantic fact**

This is **Proxy-Divergence Testing**.

A mechanism repair is incomplete if only one visible occurrence of the proxy is corrected while the same mistaken concept survives elsewhere.

---

## 14. Attack Families

A mature Nuke campaign may consider these attack families.

Not every campaign requires all of them.

### 14.1 Authority attacks

Can a lower-authority actor produce a human-only semantic effect?

### 14.2 Identity attacks

Can identity be transferred, reused, resurrected, merged or erased without authority?

### 14.3 Preservation attacks

Can valid human or persistent state disappear under semantically unchanged evidence?

### 14.4 Invalidation attacks

Can stale meaning survive genuine governing change?

### 14.5 Proxy-divergence attacks

Can implementation proxies diverge from the facts they are assumed to represent?

### 14.6 Coverage-model attacks

Which important semantic properties are missing from the declared coverage model?

### 14.7 Verifier attacks

Can an oracle, checker or validator label a real violation as legal?

### 14.8 Common-mode attacks

What single mistaken assumption could make implementation and validators agree?

### 14.9 Metamorphic / stutter attacks

Do meaning-preserving transformations preserve the protected semantic projection?

### 14.10 Stateful / history attacks

Can legal individual operations compose into an illegal history?

### 14.11 Exploit-chain attacks

Can individually permitted transitions combine into a forbidden semantic end state?

### 14.12 Failure / chaos attacks

Can interruption, recovery or partial failure leave the system confidently wrong?

### 14.13 Mutation attacks

Would the assurance estate detect a deliberately introduced high-consequence defect?

### 14.14 Custody / evidence attacks

Can evidence become more authoritative merely through movement, replay, copying or persistence?

### 14.15 Independent challenger attacks

Can an independently derived semantic model produce a serious counterexample that the internal assurance model missed?

### 14.16 Authority-laundering attacks

Can technically valid evidence confer apparent authority on state that governing human authority never currently approved?

### Authority laundering as an optional lens

The question above recurs often enough in field use to be worth naming, though it is a lens
across several of the families above rather than a replacement for any of them.

> **Authority laundering occurs when internally coherent lineage, hashes, registries,
> approvals, derived state or other local evidence make a state appear authorized or current
> even though the governing human meaning, scope, lineage or currentness does not actually
> support that authority.**

What makes it hard to catch is that nothing is malformed. Observed instances included a
cryptographically valid but superseded approval; an approval for one artifact effectively
authorizing another; lineage required for an authority being removed after the fact; and a
reduced derived ledger refreshing its own hash and thereby certifying its own reduced
completeness.

The label is optional and is not a required finding class. If a campaign already asks the
question through §14.1, §14.2 or §14.14, the mechanism is covered and the term adds nothing.

---

## 15. Nuclear Mutation Testing

Nuke Testing may use deliberately chosen **nuclear mutants**.

These are not random syntax mutations.

They are small deliberate changes that violate a high-consequence semantic claim.

Examples:

- bypass a human-authority gate;
- accept stale state;
- omit one provenance contributor;
- reuse a retired identity;
- suppress required uncertainty;
- break exact-state acceptance binding;
- replay a locally valid grant against different bytes, material, operation, subject, recovery
  context, or widened scope.

A killed mutant demonstrates:

> **The current assurance estate is sensitive to this deliberate failure class.**

It does not establish:

> **Every important failure class was represented by the mutant set.**

Mutation testing measures verifier sensitivity to the mutant model.

It does not prove specification completeness.

For mature campaigns, a selected **semantic/specification mutant** may also be useful.

Example mutated rule:

> "A human decision may be discarded after unchanged evidence."

Question:

> **Would the assurance model itself reject this altered meaning?**

One caveat on reading kill rates: a mechanism that rejects everything kills every mutant.

> **Mutation death supports assurance only if the intended valid state remains representable,
> reachable and accepted under the same mechanism (§11, §17).**

### Where trust rests on a root, mutate the chain rather than a field

As a system moves from individually checked hashes and fields toward canonical provenance roots,
producer-origin registries, deterministic derivation, lineage roots or root-owned allocation
state, the useful mutant changes shape. "Can I corrupt one hash?" stops being the strong
question, because every field-level check may correctly reject a malformed input.

> **Where assurance depends on a provenance or authority root, challenge internally coherent
> alternative chains — locally valid hashes, well-formed derivations, a self-consistent history
> — not only malformed individual fields.**

The failure this looks for is acceptance of unauthorized state through evidence that is valid at
every local check, which is the same mechanism as §14.16 approached from the mutant side. It is
a choice of mutant, not a separate method.

---

## 16. Semantic History Checking

A history checker can be valuable for systems where final-state checks are insufficient.

It may reason about:

- authority;
- identity;
- lifecycle;
- provenance;
- ambiguity;
- promotion;
- acceptance;
- persistence;
- invalidation;
- preservation;
- historical legality.

But its claim must remain bounded.

A green history checker result should mean:

> **No encoded history invariant was violated.**

It must not automatically mean:

> **The history is semantically correct in every relevant sense.**

A history checker is only as complete as the properties it encodes.

It should not simply call the production mechanism it is supposed to judge.

---

## 17. Verification of Verification

Nuke Testing treats verification machinery as part of the assurance problem.

This can include:

- semantic history checkers;
- completeness oracles;
- identity or lineage oracles;
- mutation harnesses;
- replay checkers;
- test generators;
- coverage instrumentation;
- custody validators;
- closure metrics.

A serious verifier should receive, where appropriate:

- legal positive controls;
- illegal negative controls;
- boundary cases;
- targeted mutants;
- independent cross-checks;
- proof that the observed property can influence the verdict.

A permanent rule is:

> **If an independent challenge establishes a real violation and an internal verifier labels it legal, the verifier gap is itself an assurance finding.**

Fixing production without understanding a blind verifier can leave the assurance architecture vulnerable to recurrence.

A related rule governs what verification machinery should do when it catches a violation in
itself or in the boundary it is enforcing.

> **Verification infrastructure that detects a violated boundary should refuse rather than repair
> it, wherever repairing would destroy the evidence that the boundary was false. A silent repair
> removes the one fact worth having.**

A guard that quietly cleans up what it found and continues leaves a clean run behind and no
record that the claimed boundary did not hold. A refusal is visible and attributable: it can name
what was found, where, and what it implies about the claim that depended on the boundary.

---

## 18. Independent Evidence Is Effective, Not Nominal

Two checks are not independent merely because:

- they live in different files;
- different agents wrote them;
- different models ran them;
- one is called an "oracle";
- one is run in a separate chat.

For every serious evidence path, consider:

- authority inputs;
- expected-side derivation;
- production mechanisms read;
- shared fixtures;
- shared transformations;
- shared test model;
- shared prior conclusions;
- model/provider relationship;
- organizational relationship.

Useful diversity dimensions include:

- role diversity;
- mechanism diversity;
- information diversity;
- derivation diversity;
- model/provider diversity;
- organizational diversity.

The concept to optimize is:

> **effective assurance barriers**

—not validator count.

A campaign may have ten validators and only two materially distinct ways of being wrong.

### Transmitted and inherited correlation

Isolating challengers from one another reduces correlation that would otherwise be **transmitted** between them.

It does nothing about correlation **inherited** from a shared model family, authority, set of assumptions, decomposition, toolchain or evidence surface.

Isolation primarily reduces transmitted correlation. Inherited correlation is reduced only by deliberately varying those shared inputs, and may remain even under perfect isolation. An independence claim should therefore describe what the evidence paths share, not only what has been withheld from them.

### Optional: parallel specialist challengers

Effective barriers may be pursued by one challenger or by several working in parallel on different challenge derivations.

The parallel form is practice-derived operational guidance and an execution topology — not a method, and not validated generic best practice. Its value comes from challenge diversity and preserved provenance, never from challenger count.

Consider it only when approximately all of the following hold.

1. **Consequence justifies the extra breadth.** The result could materially affect acceptance, repair or residual-risk judgment. Routine work does not warrant it.
2. **The challenge divides into materially different derivations** — different failure-seeking mechanisms, causal hypotheses, evidence surfaces or lifecycle paths. Topic labels, role names and several variations of one prompt are not materially different derivations.
3. **Provenance and disagreement can be preserved** through synthesis, as the adjudication rules below require.
4. **The information boundary can be described as implemented rather than as intended**, and inherited correlation is stated rather than assumed away.
5. **Marginal assurance value justifies the cost**, under the Stop Doctrine.

A single strong challenger may be the better choice, and often is, where the assurance problem depends on deep stateful sequences, long lifecycle continuity, repeated-history reasoning, or causal minimization that resists partition — or where the surface is small enough that further challengers would mostly duplicate work. Bounded parallel decomposition may be a poor fit where assurance depends on long accumulated histories or on causal continuity that does not partition cleanly: the depth can still be reached, but split across challengers it fragments easily, and no single challenger then holds the whole sequence.

Depth and breadth are ways of allocating challenge effort. Neither is doctrine, and using both is not required.

---

## 19. Fresh Context Is Not Automatically Independent

A fresh LLM session is useful.

It is not automatically blind.

If the challenger first reads:

- prior repair reports;
- previous findings;
- internal oracle designs;
- roadmap conclusions;
- prior challenger reports;
- producer reasoning;

then its "independent" result may simply reproduce the existing assurance model.

For high-consequence final challenge, use an explicit information boundary.

A strong pattern is:

1. provide accepted authority and the exact system under test;
2. withhold internal assurance conclusions;
3. derive critical expectations independently;
4. freeze those expectations;
5. inspect implementation;
6. construct independent attacks/oracles;
7. freeze findings;
8. only then unblind against the internal assurance case.

Where evidence must live outside the canonical project during challenge, bind it by:

- exact system revision;
- file hashes;
- aggregate hashes;
- manifest;
- content-addressed custody.

> **Independent evidence should depend on content identity, not merely directory location.**

---

## 20. Challengers Must Not Repair Their Own Counterexamples

An independent challenger should normally not repair production.

A challenger that finds a serious failure should:

1. preserve the counterexample;
2. classify it against authority;
3. freeze evidence;
4. stop or complete only the authorized challenge;
5. hand repair to a separate role/session.

Why?

Because a challenger with repair authority can drift from falsification into rationalization.

A useful pattern is:

```text
INDEPENDENT CHALLENGE
        ↓
SERIOUS FINDING
        ↓
FREEZE EVIDENCE
        ↓
SEPARATE HUMAN/SEMANTIC ADJUDICATION IF NEEDED
        ↓
SEPARATE REPAIR
        ↓
DISCRIMINATIVE REGRESSION
        ↓
NARROW OR BROAD RE-CHALLENGE AS WARRANTED
```

---

## 21. Findings Must Be Adjudicated Before Repair

Not every adversarial disagreement is a product bug.

Classify material findings as, for example:

```text
CONFIRMED PRODUCT BLOCKER
CONFIRMED PRODUCT MAJOR
MINOR
ASSURANCE GAP
VERIFIER GAP
TEST / ORACLE GAP
PREMISE ERROR
AUTHORITY QUESTION
ENVIRONMENT ERROR
ACCEPTED LIMITATION
NOTE
```

A useful adjudication question is:

> **What accepted authority decides what should have happened?**

If accepted authority is genuinely missing:

> **HUMAN_RULING_REQUIRED**

The test, oracle or challenger must not silently invent the missing semantic rule.

This is a critical Human Sandwich boundary.

### Defect severity and incident causality are separate questions

An investigation motivated by one incident can find a real, material defect that is not the
cause of that incident. Both facts can hold at once, and collapsing them is a live field
failure mode.

> **Finding a material defect does not establish that the defect caused the incident under
> investigation. Severity and causality are separate adjudication questions, and each needs its
> own evidence.**

A material finding may be any of:

- causal to the investigated incident;
- material but latent, with no causal path to this incident;
- a gap in the governed authority or product model (§9) rather than in the implementation;
- expected variance within the accepted contract;
- a disconfirmed hypothesis, which is useful evidence;
- not yet sufficiently evidenced either way.

These are reasoning distinctions, not a mandatory taxonomy to be emitted per finding. Use the
existing finding states (§36) and adjudication classes above.

The practical rule is the same one §22 already applies to repair: establish the causal path,
do not infer it from proximity. A campaign that disproves several plausible causes and then
finds an unrelated real defect has produced two results, not one — and the incident may still
be unexplained.

### Out-of-scope findings: preserve without expanding

A bounded campaign may legitimately discover a material defect outside the incident's causal or
repair scope. Discovering it is not a scope violation, and discarding it because it was not the
target is a real loss.

> **When a bounded assurance campaign finds a material defect outside its authorized causal or
> repair scope, preserve and classify the finding, then return for proportional authorization
> before opening a new consequential repair or assurance lane.**

Enough analysis to preserve the finding — reproduce it, bound it, record what is and is not yet
known — is normally within scope. New consequential implementation, or a widened campaign, is
not. Discovery does not silently authorize recursion into whatever it uncovers.

This is not new paperwork; it is the existing HSM authority boundary applied at the point where
an assurance campaign is most tempted to keep going.

### Challenger-versus-challenger disagreement

The rules above adjudicate a challenger against the producer's assurance case. Where more than one challenger runs, the same requirement holds between challengers.

> **When challengers disagree, the disagreement, its provenance and its supporting evidence must survive synthesis. Challenger count, majority agreement and orchestrator summary do not adjudicate truth.**

Adversarial evidence combines by counterexample, not by vote. One challenger's reproducible counterexample against accepted authority is not weakened by other challengers' silence, and three PASS against one FAIL is not a PASS.

Silence is weakest as evidence exactly where the challengers' correlation is inherited rather than transmitted, because then they may share the reason for missing the same thing.

Where consequence warrants it, a synthesis should leave recoverable:

- which challenger made the claim;
- what evidence supported it;
- which assumptions differed;
- whether the disagreement is semantic, evidentiary, representational or causal.

Resolve the disagreement causally before treating the synthesis as assurance. Averaging distinct causal interpretations into one conclusion discards the finding that was most expensive to obtain.

Routine compatible findings need no disagreement record.

---

## 22. Repair Causes, Not Examples

The central repair rule is:

> **Repair causes, not examples.**

A serious repair should follow a sequence such as:

```text
REPRODUCE
    ↓
MINIMIZE
    ↓
ADJUDICATE AGAINST AUTHORITY
    ↓
CLASSIFY ROOT MECHANISM
    ↓
REPAIR THE MECHANISM
    ↓
DISCRIMINATE OLD VS NEW
    ↓
RE-ANCHOR AFFECTED EVIDENCE
    ↓
ATTACK SIBLING / ADJACENT PATHS
```

### Discriminative regression

Where practical:

- the regression must fail on the superseded implementation;
- pass on the repaired implementation;
- retain positive and negative controls.

A green test written only against repaired code is weaker evidence.

### Repair ablation

Discriminative regression (above) shows that the repaired implementation passes where the
superseded implementation failed. A repair ablation strengthens that causal claim further.

> **Where practical, temporarily ablate or bypass only the claimed load-bearing repair
> mechanism. If the original defect returns and disappears again when that mechanism is
> restored, this strengthens causal evidence that the repair mechanism produced the correction
> rather than an incidental collateral change.**

This is one deliberate mutant, in the sense of §15, applied to the repair itself rather than to
the original implementation — it does not introduce a new mutation doctrine.

A successful repair ablation does not establish semantic authority, full correctness,
assurance-model completeness, absence of sibling defects, or independent verification. It only
strengthens the causal claim that the tested mechanism is load-bearing for the observed failure
class.

Keep the mutation bounded and temporary: revert it, do not commit the ablated state, and do not
use an unsafe mutation against consequential live state.

### Search for sibling mechanisms

After finding a flawed proxy or semantic mechanism ask:

> **Where else did we encode the same mistaken concept?**

One patched branch is not mechanism closure.

---

## 23. Assurance Is Bound to an Exact System State

Assurance evidence applies to the system that was actually challenged.

Record where relevant:

- source revision / commit;
- contract or authority version;
- governed source hashes;
- fixture version;
- verifier version;
- oracle version;
- relevant environment/provenance.

A repair creates a new system state.

Therefore:

> **A repair invalidates affected closure evidence for the superseded state.**

Do not blindly restart everything.

Reopen assurance dimensions materially coupled to the changed mechanism.

But do not inherit closure across a changed mechanism without justification.

Historical evidence remains valuable.

It simply does not automatically prove the repaired state.

### Assurance is also bound to authority state

The state list above already includes contract/authority version. Authority state deserves the
same discipline given to product state above.

> **Assurance evidence is bound to governing authority state as well as product state. A later
> legitimate authority ruling may change the current oracle without making earlier evidence
> historically wrong.**

A challenger may correctly leave a proposition unresolved under the authority state that
existed when it ran. A later human ruling can resolve that proposition and change what the
current oracle requires. That later ruling does not retroactively make the earlier challenger
dishonest, incomplete, or historically incorrect — it was accurate under the authority that
governed it at the time.

> **Preserve earlier evidence under the authority state that governed it. Re-anchor the
> affected current assurance claim against the later authority rather than rewriting historical
> challenger evidence.**

This does not introduce a global authority-versioning system. Use whatever already establishes
the relevant authority state for the claim at hand — a human ruling, a contract revision, a
governing commit — the same way source revision and contract version are already recorded
above.

### Some verified claims are state-relative, not timeless

Because assurance binds to an exact state, a verified assertion can be true *of that state*
without being a permanent prohibition. Claims such as "this component does not yet exist",
"this capability is not implemented and is deferred", or "this file remains byte-unchanged
through this qualification phase" were correct where they were asserted. They are state-bound
claims, not invariants.

> **A verified assertion may be state-bound rather than permanent. Later authorized state can
> legitimately supersede a phase-bound guard or state claim without violating the underlying
> semantic invariant it was protecting.**

Two errors follow from confusing the two, and both have been seen in field use:

- promoting a state-bound claim into a timeless semantic prohibition, so later authorized work
  is treated as a violation;
- treating the superseding change as evidence that the earlier assertion was wrong.

Neither is correct. Preserve what the earlier assertion proved at its governed state (§25), and
re-anchor the current claim against the current state (§24). Where consequence warrants it, say
which invariant a guard protects and which state it was asserted against, so the distinction is
recoverable later. This does not introduce a temporal-claim framework; it is the exact-state
binding above, read forward as well as backward.

### Equal digest bytes are not evidence identity

Evidence records commonly carry digests, and two distinct evidence fields can legitimately
produce identical digest values — they observe the same canonical bytes under the same
canonicalization while supporting different claims or arising from independent derivations.

> **Equal digest values do not by themselves make two evidence claims the same evidence object.
> A digest attests to bytes under a defined canonicalization. Claim meaning, provenance, source
> and derivation remain separate evidence properties.**

The corollary matters more than the statement:

> **Do not modify an accepted digest algorithm, canonicalization, or input merely to force
> visible difference between semantically distinct evidence fields.**

That changes the evidence surface to satisfy a presentation expectation, which is a custody and
evidence attack (§14.14) rather than a repair. If two evidence claims need to be
distinguishable, distinguish them by their claim and provenance, which is where the difference
actually lives.

### Local integrity proves only what it proves

The same boundary generalizes past digests. Field use repeatedly produced states where a local
integrity or identity property was sound and was then read as a much larger claim.

> **Local integrity or deterministic identity establishes only the property it actually proves.
> It does not by itself establish authoritative origin, uniqueness, allocation, or
> consumption.**

Compactly:

> **Identity labels identify; authoritative roots allocate.**

So a valid hash is not canonical authority; a deterministic identifier is not a globally unique
one; a package-local binding is not a root-owned allocation; a reservation is not a consumption;
and an internally consistent package is not an authenticated producer origin. Each of those is
a separate claim needing its own evidence, and the strength of the integrity check says nothing
about them.

The currentness axis is governed by the authority-state binding above and is not restated here.

### Evidence metadata must describe the state it claims

Binding evidence to an exact state has a timing consequence that abstract wording misses.
Explanatory metadata — counts, summaries, derived descriptions — is often computed at a
convenient moment rather than at the moment its subject is final. If a later transformation
changes what the metadata purports to summarize, the metadata is not merely stale: it is a
deterministic, reproducible description of the wrong state, carried inside an evidence object
that otherwise verifies.

> **Evidence metadata must be derived after all claim-relevant effects it purports to
> summarize, or explicitly identify the earlier state it describes.**

Either resolution is acceptable. What is not acceptable is metadata that reads as current while
describing a pre-effect state, because nothing about it looks wrong.

### Reused evidence binds to the population it observed

Where an assurance result is reused rather than re-derived — a qualification, a cached verdict, an
inherited evidence class — the binding above governs it, and one axis of that binding is easy to
omit because subject identity looks stable.

> **Where verification evidence is reused rather than re-derived, its binding includes the
> population of observations it actually covered. Unchanged subject identity is not unchanged
> coverage.**

A subject that gained or renamed observations was not observed as it now is, and the direction of
that omission is fail-open: the unobserved part inherits the cheaper treatment. A count
comparison is not sufficient, because a rename moves no count.

### A reused answer expires when the mechanism that produced it changes

> **The identity of a reusable verification answer includes the semantics of the mechanism that
> produced it, not only the inputs that mechanism read. Otherwise a corrected mechanism can ship
> and never run: the answer derived under the superseded semantics is still addressable, still
> internally consistent, and still verifies.**

This is the currentness axis applied to the deriving mechanism itself, and it is the same
boundary as *local integrity proves only what it proves* above: a seal that recomputes attests
that the bytes are intact, not that the semantics that produced them are current.

### A comparison is attributable only if the claim is held constant

> **A before/after comparison supports a conclusion about the mechanism under study only if both
> sides make the same verification claim. Where the claim changed between them, the difference
> measures the claim change.**

This applies to any measured delta offered as evidence that a change worked — timing, resource
use, defect counts, closure metrics. Comparing a weaker claim against a stronger one and
attributing the whole difference to the mechanism is not a measurement error; it is an
unsupported claim about what the mechanism did.

---

## 24. Re-Anchoring After Repair

After a repair affecting an assurance dimension:

1. reproduce the old violation on the old state;
2. demonstrate the repaired state no longer exhibits it;
3. rerun the affected assurance frontier;
4. challenge adjacent paths;
5. only then claim current evidence for the repaired state.

Compactly:

> **Repair → Discriminate → Re-anchor → Re-challenge**

A narrow repair may justify a narrow re-challenge.

A mechanism with large semantic blast radius may require broader reopening.

Do not automatically rerun the entire campaign.

Do not automatically assume the prior campaign still applies.

### Repair can increase assurance reachability

A repair does not only change product behavior. If the repaired defect previously
short-circuited a semantic, lifecycle, or evidence path, the repair can also make previously
unreachable or unexercised assurance states reachable for the first time.

> **A repair can increase assurance reachability. If the repaired defect previously
> short-circuited a semantic, lifecycle, or evidence path, affected re-anchoring should revisit
> histories or states that were formerly unreachable or unexercised.**

This has a direct consequence for adjudicating a failure found only after repair:

> **A failure observed only after repair is not automatically a regression introduced by that
> repair. The repair may have unmasked a pre-existing downstream failure that the earlier
> defect prevented assurance from reaching.**

When adjudicating such a finding (§21), distinguish:

- **INTRODUCED BY REPAIR** — the repair mechanism itself created the failure;
- **UNMASKED BY REPAIR** — the failure predates the repair but was unreachable while the
  earlier defect stood in the path;
- a genuinely new current-state failure unrelated to either.

This does not mandate a full campaign after every repair. Reopen the affected frontier
proportionally, as the rest of this section already directs.

A repair is not the only change with this effect. A new capability or state transition can make
a pre-existing defect newly reachable, or materially more consequential, even when the new
capability is itself locally correct — a correct authority model that requires a fresh operation
identity, for example, can put weight on a latent path that nothing previously exercised.

> **Material capability or state changes should trigger a bounded review of which pre-existing
> paths, defects and assumptions become newly reachable or more consequential — not only
> repairs.**

The adjudication distinction above applies unchanged: a defect surfaced this way is
pre-existing and newly reachable, not introduced by the change, and classifying it as a
regression misdirects the repair.

The same question has a verification-side half that is easy to miss, because nothing currently
fails. A qualification target can be inapplicable now — its oracle absent, a prerequisite still
false — so ordinary regression has no failing path, and the current inapplicability quietly
holds assurance debt that a later transition will release.

> **An unmet prerequisite is not itself an assurance boundary. Where a capability or state
> transition can make a currently withheld or inapplicable verifier reachable, challenge the
> transition and establish the intended execution or withholding boundary before reachability
> arrives.**

Two questions are worth asking at the point of change rather than after it: *what verifier or
oracle becomes reachable if this capability or state changes*, and *will its execution
authority, oracle definition and still-owed state be valid at that future boundary?* This is the
temporal half of the phased-oracle material in §8 — what is owed there is owed at a known state,
whereas this is about a boundary that does not exist yet — and it does not restate it.

### A repair introduces new trust assumptions of its own

Steps 1–5 above re-challenge the repaired path and its adjacent paths. A repair also usually
*adds* something the system did not previously rely on, and that new thing is load-bearing from
the moment it lands.

> **Post-repair assurance should challenge both the affected original failure family and the
> new load-bearing trust assumptions the repair introduced. Killing every original attack is
> not closure if the repair created assumptions that have not themselves been challenged.**

Field use produced exactly this: a repair killed its entire original hostile failure family,
and a fresh challenge against the repair's own new surfaces found further dangerous survivors —
stale and superseded authority, artifact-versus-approval mismatch, removable predecessor
lineage, and derived requirement state that certified its own completeness.

Surfaces a repair commonly introduces include authority or approval records, currentness
records, lineage anchors, provenance roots, caches and materialized views, registries, derived
state, new verification dependencies, and reservation or allocation mechanisms. Where the repair
added one of these, ask what now trusts it and what happens when that trust is wrong.

Replaying only the original attacks can therefore produce false closure: the old family is
genuinely dead, and the evidence says nothing about the surface that replaced it. This is a
reminder about what the existing re-challenge step should cover, not a new phase and not a
required campaign after every repair — proportionality (§27) still governs.

### Falsifier continuity and challenge independence are different evidence qualities

Re-challenge after repair can serve two different evidence goals, and they are not the same
property.

> **Falsifier continuity and challenge independence are different evidence qualities.**

**Continuity** — re-executing the original frozen falsifier through its original reasoning
lineage — answers the narrow question "did this bounded repair remove the exact previously
frozen counterexample?" It reduces reinterpretation variance and gives a cleaner before/after
discrimination, because the falsifier itself did not change.

**Independence** (§18–§19) — a fresh, effectively independent derivation — answers the
different question "what other failure mechanism might still remain?" It gives a better chance
of discovering a dimension the original challenger did not represent.

> **For bounded post-repair discrimination, re-executing an original frozen falsifier through
> its original reasoning lineage may reduce reinterpretation variance. For discovery of
> additional failure dimensions, a fresh and effectively independent derivation may provide
> stronger evidence. Use either or both only when justified by the assurance question and Stop
> Doctrine.**

Neither is generally stronger than the other — the choice is claim-specific, not a standing
preference. Same-session or same-challenger continuity is not thereby more independent (§18–§19
govern what independence actually requires), and repeating the frozen falsifier is not itself a
substitute for independent challenge where the assurance question calls for one.

Where practical, reuse the existing frozen falsifier artifact rather than depending on a
challenger's conversational memory of it. If the original agent or session is unavailable, a
replacement executor running the same frozen falsifier can still provide useful continuity of
the test object, while representing a different execution lineage — the two are not
automatically equivalent, and equivalence should not be assumed without evidence.

---

## 25. Historical Failure Must Remain Historical

Nuke Testing must preserve uncomfortable history.

If a criterion failed:

> **the historical FAIL remains FAIL.**

A later repair may establish a new current state.

That does not rewrite the earlier result.

Useful state representation:

```text
historical_result: FAIL_PRODUCTIVE
repair: COMPLETE
recheck: COMPLETE
current_closure: PASS_AFTER_RECOVERY
```

This prevents retrospective goalpost movement.

The assurance method should obey the same historical-truth discipline it expects from the product.

---

## 26. Closure-Recovery Protocol

A stop criterion can fail productively.

A general recovery sequence is:

> **FAIL → classify → preregister recovery → repair → discriminate → re-anchor → extend if warranted → reassess current closure**

A recovery rule should be established before seeing the recovery results.

It may become stricter.

It must not become easier merely because the original criterion was inconvenient.

Do not turn:

> **FAIL**

into:

> **PASS**

by rewriting what the original criterion meant.

---

## 27. Stop Doctrine

Nuke Testing is not infinite testing.

The current experimental stopping rule is:

> **Stop when additional attacks are no longer expected to add materially independent evidence against the remaining risk.**

This is deliberately not:

> "Stop when the test count is high."

It is also not:

> "Never stop while another test can be imagined."

Possible closure dimensions include:

- claim/authority closure;
- declared semantic coverage closure;
- model-completeness challenge;
- independent-evidence closure;
- known-mechanism closure;
- verifier closure;
- mutation closure;
- preservation/invalidation closure;
- history/stateful closure;
- failure/cross-mechanism closure;
- independent challenger closure;
- residual-risk review;
- proportionality/economic review.

Not every campaign requires the same depth.

---

## 28. Stop Metrics Must Not Gain Authority

A stopping metric measures a specific thing.

It does not become semantic authority.

For example:

> **economic closure**

may describe whether additional work appears to have diminishing marginal assurance value.

It does not decide whether the implementation is semantically correct.

A metric may remain failed or inconclusive.

Do not manufacture meaningless work merely to make the metric green.

Permanent rule:

> **If a test unit would not count as meaningful evidence when red, it must not count merely because it is green.**

And:

> **Do not invent work whose sole purpose is to move a counter.**

---

## 29. "Done" Has Multiple Meanings

Nuke Testing distinguishes:

### EXHAUSTED

No currently justified new attack dimension remains within the defined scope.

### ASSURED

The predefined assurance threshold has been satisfied for the exact current system state.

### ACCEPTED

A human accepts the residual risk for the intended next consequential use.

These are not interchangeable.

Testing cannot substitute for human acceptance.

Human acceptance cannot substitute for missing evidence.

A campaign may also legitimately remain:

> **INCONCLUSIVE**

That is a valid assurance result.

---

## 30. Minimum Evidence Floor

A testing plateau means little if the system has not received meaningful exposure.

For high-risk claims, define a minimum evidence floor before interpreting quietness.

Possible requirements include:

- critical claims enumerated;
- authority source known;
- relevant semantic states exercised;
- important preservation and invalidation relations tested;
- cross-mechanism interactions challenged;
- at least one independent evidence path for critical claims;
- important verifier sensitivity demonstrated;
- selected high-consequence mutants killed;
- state/history depth appropriate to the mechanism;
- residual uncertainty documented.

The exact floor must be proportional to consequence.

Do not create universal numeric thresholds without evidence.

---

## 31. A Practical Experimental Pipeline

The following is the current **experimental** Nuke workflow.

It is not mandatory ceremony for every project.

### Phase 0 — Bound the assurance problem

State:

- system under test;
- intended next consequential use;
- out-of-scope areas;
- dangerous silent failures;
- trust boundaries;
- consequence classes.

### Phase 1 — Lock meaning

Identify:

- accepted requirements;
- human rulings;
- contracts;
- invariants;
- explicit non-goals.

If semantics are missing:

> **HUMAN_RULING_REQUIRED**

### Phase 2 — Derive falsifiable claims

For high-consequence claims define:

- authority;
- falsifier;
- expected evidence;
- assumptions;
- residual risk.

For persistent/human state derive both:

- invalidation property;
- preservation property.

### Phase 3 — Pre-register the assurance model

Define:

- semantic dimensions;
- important bins/crosses;
- attack families;
- verifier expectations;
- minimum evidence floor;
- stopping criteria;
- expected failure actions.

### Phase 4 — Challenge representability and reachability

Ask:

- can the test model express the risky state?
- can valid operations reach it?
- does the generator actually exercise it?
- does the oracle observe it?
- can the observation alter the verdict?

### Phase 5 — Build heterogeneous evidence

Choose proportionally from:

- deterministic contract tests;
- metamorphic/stutter tests;
- independent oracles;
- model/stateful tests;
- history checking;
- exploit chains;
- fault injection;
- semantic chaos;
- persistence/tamper challenges;
- concurrency;
- mutation;
- governed real-world evidence where authorized.

### Phase 6 — Attack seams and proxies

Prioritize:

- cross-mechanism interactions;
- identity boundaries;
- authority transitions;
- source/reconstruction boundaries;
- implementation proxies.

### Phase 7 — Adjudicate findings

Separate:

- product defect;
- verifier gap;
- oracle/test defect;
- authority gap;
- premise error;
- accepted limitation.

Do not repair before meaning is established.

### Phase 8 — Repair the mechanism

Fix the causal semantic mechanism.

Do not special-case one witness unless authority truly requires that exact case.

### Phase 9 — Discriminate and re-anchor

Show:

- old state fails;
- repaired state passes;
- controls remain meaningful.

Reopen affected assurance only.

### Phase 10 — Verify the verification

Attack:

- checkers;
- oracles;
- coverage models;
- generators;
- mutation harnesses;
- custody checks.

### Phase 11 — Challenge the assurance model

Where consequence warrants it, use a fresh independent derivation path.

For strong independence, control the information boundary.

### Phase 12 — Rechallenge after material repairs

A bounded repair may receive a bounded fresh re-challenge.

A broad mechanism change may require broader reopening.

### Phase 13 — Closure review

Ask:

- what is supported?
- what remains red?
- what remains unknown?
- what historical failures remain?
- what residual risk remains?
- would another materially different attack plausibly change the decision?

### Phase 14 — Human acceptance

The human decides whether the remaining residual risk is acceptable for the intended next use.

Nuke Testing provides evidence.

It does not make the human decision.

---

## 32. LLM Execution Contract

When an LLM is instructed to run or prepare Nuke Testing, it should:

1. identify the exact bounded assurance question;
2. identify accepted semantic authority before deriving tests;
3. distinguish direct evidence from inference;
4. derive falsifiable claims;
5. distinguish representable, reachable, exercised, observed and verdict-influential state;
6. search for proxy/invariant divergence;
7. test preservation as well as invalidation where relevant;
8. prefer heterogeneous evidence over repeated evidence;
9. state common-mode dependencies;
10. challenge the verifier/test model itself;
11. preserve serious historical failures;
12. adjudicate disagreements before repair;
13. repair causal mechanisms rather than witnesses;
14. use discriminative regressions where practical;
15. bind assurance to the exact system state;
16. re-anchor affected evidence after repair;
17. use fresh independent challenge where consequence/common-mode risk warrants it;
18. return authority to the human when meaning is underspecified;
19. preserve INCONCLUSIVE as a valid result;
20. stop according to decision-relevant marginal assurance value.

---

## 33. Forbidden LLM Behavior

An LLM running Nuke Testing must not:

- invent semantic authority to satisfy a failing test;
- treat production behavior as authority merely because it exists;
- treat a green suite as proof of correctness;
- equate test count with assurance;
- call many agents independent without analyzing common-mode inputs;
- reuse production logic as an "independent" expected-value oracle without disclosure;
- silently change test expectations after observing results;
- rewrite historical failures;
- allow a challenger to erase its own counterexample through repair;
- promote a verifier gap into a product defect without causal evidence;
- demote a product defect into "test noise" because the test is inconvenient;
- claim coverage-model completeness from coverage of the declared model;
- claim mutation closure proves specification completeness;
- continue testing solely to satisfy a metric;
- mark human acceptance without explicit human authority.

---

## 34. Common Anti-Patterns

### More-tests-forever

Volume is not assurance.

### Multi-agent theatre

Many agents sharing one model of the problem are not independent evidence.

### Green-dashboard laundering

Historical red states must not be reinterpreted into green.

### Implementation-as-oracle

The mechanism being judged must not be the sole source of expected truth.

### Coverage absolutism

100% of declared bins does not prove the model contains every important property.

### Mutation absolutism

Killed mutants prove sensitivity to those mutants, not completeness of the specification.

### Challenger contamination

A challenger that sees the internal answer first is not strongly independent.

### Repair-in-the-challenger

A falsification role should not silently become a repair role.

### No-op special casing

Repair the semantic relation, not one whitespace/newline/replay witness.

### Metric authority creep

A stopping or coverage metric reports evidence only for the thing it measures.

### Oracle cleanup without impact analysis

If a verifier was wrong, ask which prior conclusions depended on the same error.

### Historical erasure

Do not delete or overwrite evidence simply because later work repaired the defect.

### Consensus laundering

A synthesis that settles challenger disagreement by weight of numbers discards the evidence the disagreement was there to carry.

---

## 35. Assurance Artifact

A Nuke campaign should eventually leave an inspectable assurance record, not merely test logs.

A useful minimal shape is:

```text
NUKE ASSURANCE RECORD

SCOPE:
<what exact system/use is being assured>

SYSTEM STATE:
<commit/hash/version>

AUTHORITY:
<contracts/rulings governing meaning>

CRITICAL CLAIMS:
<what is being trusted>

FALSIFIERS:
<what could refute each claim>

EVIDENCE:
<tests/oracles/histories/mutants/independent challenge>

INDEPENDENCE:
<common-mode and effective assurance barriers>

COVERAGE:
<declared model coverage and known gaps>

VERIFIER EVIDENCE:
<why the checking machinery itself is trusted>

HISTORICAL FAILURES:
<serious findings and repairs preserved>

REPAIR / RE-ANCHOR STATUS:
<what changed and what evidence was rerun>

RESIDUAL LIMITATIONS:
<what remains unknown/out of scope>

STOP ASSESSMENT:
<why further work is or is not justified>

CURRENT STATUS:
EXHAUSTED = true/false
ASSURED = true/false
HUMAN_ACCEPTED = true/false
```

This is a state declaration, not a numerical score.

---

## 36. Recommended Finding States

A Nuke workflow benefits from explicit assurance states.

Candidate states:

```text
NOT_STARTED
RUNNING
PASS
FAIL_PRODUCTIVE
BLOCKER_FOUND
MAJOR_FOUND
HUMAN_RULING_REQUIRED
REPAIR_REQUIRED
RECHECK_REQUIRED
REANCHOR_REQUIRED
EXTENSION_REQUIRED
PASS_AFTER_RECOVERY
INCONCLUSIVE
RESIDUAL_LIMITATION
```

Historical state and current state should be separate.

Example:

```text
historical_result = FAIL_PRODUCTIVE
repair = COMPLETE
narrow_rechallenge = PASS
current_assurance = INCONCLUSIVE
human_acceptance = false
```

This prevents "current looks good" from rewriting the evidence trail.

---

## 37. Minimal Viable Nuke

A full campaign may be expensive.

For smaller but consequential tasks, a minimal experimental Nuke can be:

```text
1. LOCK THE CLAIM
2. STATE THE FALSIFIER
3. IDENTIFY THE DANGEROUS SILENT FAILURE
4. RUN ONE NORMAL CHECK
5. RUN ONE MECHANISM-DIFFERENT CHALLENGE
6. TEST ONE PRESERVATION AND ONE INVALIDATION CONTROL
7. ASK WHETHER THE VERIFIER COULD MISS THE FAILURE
8. IF FAILURE: REPAIR THE CAUSE
9. PROVE OLD FAILS / NEW PASSES
10. STATE RESIDUAL RISK
11. STOP OR ESCALATE PROPORTIONALLY
```

This is preferable to applying the entire methodology mechanically to every task.

---

## 38. Practice-Derived Lessons So Far

The current experimental method is supported by practice observations including:

- broad green test suites can still miss serious semantic failures;
- defects often appear at interactions between individually reasonable mechanisms;
- deeper history/stateful testing can reveal mechanisms missed by shallow testing;
- a replay system can faithfully reproduce an invalid history;
- independent oracles can expose both product defects and oracle defects;
- test/verification systems themselves can have consequential blind spots;
- a campaign can saturate its declared semantic model while the model remains incomplete;
- genuinely independent semantic re-derivation can find failures after extensive internal hardening;
- preservation properties can be as important as invalidation properties;
- semantic no-op transformations are useful metamorphic attack surfaces;
- repairs invalidate assurance evidence tied to the superseded mechanism;
- discriminative pre/post regressions strengthen evidence that a repair addressed the intended defect;
- a verifier may observe a field without allowing that field to influence its verdict;
- a challenger can validly return an authority ambiguity rather than inventing a product defect;
- stopping criteria themselves can become flawed if they begin generating purposeless work.

### Local downstream field evidence (2026-09)

The following four observations come from one local downstream project Nuke episode, not
external validation:

- repairing an early short-circuit defect can make previously unreachable downstream assurance
  paths reachable;
- later human authority can change the current oracle without rewriting historically valid
  evidence produced under earlier authority;
- falsifier continuity and independent challenge serve different post-repair evidence goals;
- targeted repair ablation can strengthen causal evidence that a repair mechanism is
  load-bearing.

### Further local field observations (2026-09)

Five further observations come from continued local governed project work, across several
episodes inside the same projects. They are repeated within-project field observations, not
independent replications and not controlled evidence:

- material defect discovery and incident causality are distinct adjudication questions, and an
  investigation can disprove its plausible causes and still find a real unrelated defect;
- a bounded campaign can reveal a material defect outside its authorized scope, which should be
  preserved and classified without silently widening the repair lane;
- some assurance failures arise because the governed authority or product model cannot express
  the distinction verification needs to enforce, which no harness improvement repairs;
- state-bound claims and partly exercisable oracles need state-relative interpretation rather
  than promotion into timeless invariants or aggregate PASS;
- evidence identity includes claim meaning and provenance, not only digest bytes.

### Authority and repair-surface field observations (2026-09)

Further observations from continued local governed project work, again repeated
within-project rather than independently replicated:

- a repair that kills its entire original failure family can introduce new load-bearing trust
  assumptions that no original attack touches;
- internally coherent local evidence — valid approvals, hashes, registries, derived state — can
  make a state appear currently authorized when governing authority does not support it;
- establishing that an artifact is non-authoritative for a property does not make that property
  unconstrained;
- local integrity and deterministic identity do not establish origin, uniqueness, allocation or
  consumption;
- evidence still required to justify an accepted authority can be removed afterwards unless
  something prevents it;
- where non-execution is the consequential claim, instrumentation at the execution boundary is
  stronger evidence than absent downstream artifacts.

### Identity and admissibility field observations (2026-09)

A further set from a governed development sequence, again local field evidence rather than
independent replication, though several of these were mechanically reproduced before any
implementation existed:

- adding an optional capability can change the durable identity of the path that does not use
  it, producing a spurious conflict between a request and its own earlier journalled form;
- canonicalization becomes a semantic invariant as soon as durable identity is derived from it;
- a locally correct new capability can make a pre-existing defect newly reachable or materially
  more consequential, exactly as a repair can;
- a verifier that is inapplicable now can become applicable after a later transition, so current
  absence of a failing path is not evidence that nothing is owed;
- evidence metadata computed before the effects it summarizes describes the wrong state
  deterministically, while still verifying;
- human authorization of a consequence does not establish an independent technical predicate
  that the consequence was conditioned on.

### Verification-estate scalability field observations (2026-09)

A further set from one governed downstream programme that optimized the execution of a large
verification estate under human acceptance. Local field evidence from a single project and a
single execution environment, not independent replication and not cross-domain validation:

- a hazardous condition can be established by the execution context where the corresponding
  subject-level property is not establishable at all, at which point subject-level absence is no
  longer the claim admission should turn on;
- capability truth, condition truth, and the mechanism that made the condition true are three
  facts, and merging any two of them overstates the result;
- a population-scoped condition is not established by confining part of the population;
- reused qualification typed on subject identity alone went fail-open across a subject whose
  observation set had changed;
- a reused answer derived under superseded mechanism semantics remained addressable, internally
  consistent and verifiable, so a correctness repair could have shipped without ever running;
- a conservative default with no evidence-producing discharge route accumulates until weakening
  the gate is the only relief left;
- a change of execution context altered what a material fraction of the estate observed;
- two timings for the same estate under two different admission claims differed by more than the
  scheduling work being measured;
- a harness defect produced a confident negative conclusion that survived two phases and was
  withdrawn rather than rewritten, and the enforced run then exposed a defect in the tests that
  verify the enforcement.

Two evidence boundaries are explicitly unresolved and are recorded here rather than left to be
inferred from the positive results above:

- **Enumerable populations only.** In this programme one scheduler owned the whole relevant
  population, so *every concurrently relevant participant* was a set it could enumerate and
  cover. Where participants arrive from outside that control, the population-scope rule may name
  a claim nothing can establish, and the failure would be silent.
- **One execution environment.** The mechanism is unproven on a second environment even inside
  the project that established it, which bounds how far the accepted evidence reaches.

These observations motivate the method.

They do not establish external validity.

---

## 39. What Is Inherited, Adapted and Local

### Inherited / established ingredients

Nuke Testing draws on mature or established traditions such as:

- requirements/contract-driven verification;
- independent verification and validation;
- model/stateful testing;
- metamorphic testing;
- mutation testing;
- fault injection;
- chaos/recovery testing;
- red teaming;
- formal invariant reasoning;
- coverage analysis;
- reliability-growth thinking;
- scientific controls and independent replication;
- assurance cases;
- configuration/state binding.

### Adapted

Nuke Testing adapts these to focus on:

- semantic authority;
- persistent human decisions;
- provenance;
- identity;
- uncertainty;
- AI-assisted implementation;
- common-mode reasoning between implementation and verification;
- explicit assurance-state history.

### Local synthesis

The following should currently be treated as local synthesis:

- the name **Nuke Testing**;
- the exact workflow composition;
- the five-level representable/reachable/exercised/observed/verdict-influential distinction as an operational Nuke lens;
- the explicit preservation/invalidation pairing as a standard campaign obligation;
- "nuclear mutants" as a named high-consequence mutation class;
- re-anchor as a first-class post-repair assurance phase;
- the specific blind-challenger sequencing for LLM workflows;
- the current Stop Doctrine;
- the assurance-state vocabulary;
- the combined HSM/VLD/Nuke governance model.

### Experimental

Still experimental:

- how much each phase adds outside the original practice domain;
- which phases should be mandatory at each consequence level;
- how to measure effective assurance barriers;
- how to measure marginal assurance value;
- whether a generic semantic history checker is practical;
- whether blind LLM challenge reliably reduces correlated reasoning error;
- whether parallel specialist challengers add materially independent evidence over one strong challenger at equal cost;
- how well the method transfers to probabilistic/learned systems;
- whether the full method can be compressed substantially without losing defect-finding power.

---

## 40. Method Maturity Rule

Do not promote Nuke Testing from EXPERIMENTAL merely because:

- one project reaches human acceptance;
- many tests pass;
- a fresh challenger returns no new blocker;
- the method feels coherent;
- several LLMs agree that it is useful.

Promotion should require evidence such as:

- repeated use across materially different projects;
- documented cases where Nuke finds failures ordinary validation misses;
- documented cases where Nuke correctly decides deeper assurance is unnecessary;
- evidence about cost and diminishing returns;
- cross-domain Critical Mass research;
- external critique;
- failed transfers and negative cases;
- comparison against simpler alternatives;
- stable terminology and execution behavior;
- evidence that fresh teams/agents can apply it without reproducing hidden project-specific assumptions.

---

## 41. Open Research Questions

Before stable doctrine, investigate at least:

1. Which Nuke phases produce genuinely independent defect-finding value?
2. Which phases mostly duplicate evidence?
3. Which parts transfer beyond persistent engineering/software systems?
4. When is a blind challenger worth the custody/coordination cost?
5. How should effective assurance barriers be measured?
6. How should assurance effort and marginal value be represented without misleading scores?
7. Can preservation/invalidation relations be derived automatically from contracts?
8. Can semantic coverage models be generated without becoming self-referential?
9. How should probabilistic systems be treated when exact invariants are unavailable?
10. How should learned/AI systems be assured when model behavior is stochastic?
11. What consequence thresholds justify mutation, chaos, deep history or independent challenge?
12. How should verifier gaps be prioritized relative to product defects?
13. When is model/provider diversity enough, and when is organizational independence required?
14. What parts of Nuke Testing duplicate existing safety/security assurance methods?
15. Can a much smaller method achieve most of the benefit?
16. What are the strongest observed cases where Nuke Testing adds too much process?
17. What should a future Critical Mass investigation reject or rename?
18. What evidence would justify moving from EXPERIMENTAL to PRACTICE-DERIVED STABLE?

---

## 42. One-Page Model

```text
BOUND THE CONSEQUENCE
        ↓
LOCK THE MEANING
        ↓
DERIVE FALSIFIABLE CLAIMS
        ↓
MAP:
REPRESENTABLE
→ REACHABLE
→ EXERCISED
→ OBSERVED
→ VERDICT-INFLUENTIAL
        ↓
DERIVE PRESERVATION + INVALIDATION PROPERTIES
        ↓
BUILD HETEROGENEOUS EVIDENCE
        ↓
ATTACK PROXIES + CROSS-MECHANISM SEAMS
        ↓
ATTACK THE VERIFIERS
        ↓
ADJUDICATE AGAINST AUTHORITY
        ↓
IF MISSING MEANING:
    HUMAN_RULING_REQUIRED
        ↓
IF DEFECT:
    REPAIR THE MECHANISM
        ↓
DISCRIMINATE OLD VS NEW
        ↓
RE-ANCHOR AFFECTED ASSURANCE
        ↓
INDEPENDENTLY RE-CHALLENGE WHERE WARRANTED
        ↓
ASSESS DECLARED COVERAGE + MODEL COMPLETENESS
        ↓
STATE RESIDUAL RISK
        ↓
STOP WHEN FURTHER ATTACKS LACK
MATERIALLY INDEPENDENT ASSURANCE VALUE
        ↓
HUMAN ACCEPTANCE
```

---

## 43. Permanent Experimental Rules

> **Green tests are evidence, not authority.**

> **If testing discovers missing meaning, return authority to the human.**

> **Representable is not reachable. Reachable is not exercised. Exercised is not observed. Observed is not necessarily verdict-influential.**

> **Coverage closure is closure of a declared model, not proof that the model is complete.**

> **A representability gap limits the claim whose failure mode it hides; unrelated passing evidence does not compensate.**

> **Challenger disagreement is evidence. Challenger count and majority agreement do not adjudicate truth.**

> **Test both what must invalidate consequential state and what must preserve it.**

> **Repair causes, not examples.**

> **A repair changes the system under test; affected assurance must be re-anchored.**

> **Verification mechanisms are part of the assurance problem.**

> **Many agents can still be one correlated epistemic source.**

> **A challenger that sees the internal answer first is not strongly independent.**

> **Historical failures stay historical.**

> **INCONCLUSIVE is a valid result.**

> **Stop metrics report evidence; they do not acquire semantic authority.**

> **Stop when additional attacks no longer add materially independent evidence against the remaining risk.**

---

## 44. Current Madpakken Status

```text
METHOD:
Nuke Testing — Contract-Driven Adversarial Assurance

MADPAKKEN STATUS:
EXPERIMENTAL

ORIGIN:
Practice-derived / local synthesis

USE:
Allowed for bounded governed experiments and consequential project assurance.

DO NOT CLAIM:
Established methodology
Industry standard
Scientific proof
Formal correctness proof
Safety certification

REQUIRED GOVERNANCE:
Human authority remains above test/oracle/agent output.

NEXT MATURITY WORK:
Cross-domain Critical Mass
Continued real-project experiments
Independent critique
Transfer testing
Cost / proportionality evaluation
Method simplification
```

---

## 45. Closing Definition

The current experimental definition is:

> **Nuke Testing is a practice-derived, contract-driven adversarial assurance method that begins from governed meaning, derives falsifiable claims, challenges implementation, verification and the assurance model through heterogeneous evidence, repairs causal mechanisms, preserves historical failures, re-anchors evidence after change, uses genuinely independent challenge where consequence warrants it, and stops when further attacks are no longer expected to add materially independent evidence against the remaining risk.**

Its ambition is not:

> **test everything.**

Its ambition is:

> **make unjustified confidence difficult to survive.**

---

**End of Nuke Testing — Experimental v0.1**
