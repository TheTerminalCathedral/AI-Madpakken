# The Sandwich Alignment Skewer

## Verification-Locked Development

**VIBE THE IMPLEMENTATION.**
**LOCK THE MEANING.**

*By Dan Almer Jensen and his sandwich*

```text
   AUTHORISED MEANING              ┐
       IMPLEMENTATION              │  ALIGNMENT
   EVIDENCE / VERIFICATION         │   SKEWER
       ACCEPTED STATE              ┘      ▼

   LAYERS MAY MOVE. THEY MAY NOT SILENTLY STOP REFERRING TO THE SAME THING.
```

**Practice-based report — September 2026**
`VLD / ALIGNMENT / EVIDENCE`

---

I did not set out to invent another AI development framework.

I was trying to get software built.

AI coding agents had become good enough that specifying every function, class and implementation detail myself increasingly felt like defeating the point.

I wanted them to explore.

I wanted them to refactor.

I wanted them to choose algorithms, create helpers, write tests, inspect the repository and solve local implementation problems without asking me about every mechanical decision.

Basically:

> **I wanted the useful part of vibecoding.**

Unfortunately, correctness remained necessary.

And after enough complicated work, I started noticing a particular kind of failure.

---

## THE FAILURE THAT WOULD NOT GO AWAY

> **The code could change.**
>
> **The tests could pass.**
>
> **The counts could reconcile.**
>
> **The report could say success.**
>
> **And a frozen earlier result could still disagree.**

That was the part I could not ignore.

The obvious response would have been to control the implementation more tightly.

Instead, I gradually started doing almost the opposite.

I became stricter about **meaning**, **authority**, **evidence** and **what the result was actually allowed to claim**.

The implementation could still move.

The surrounding definition of correctness could not silently move with it.

I started calling the practice:

> **Verification-Locked Development.**

The Human Sandwich apparently required structural reinforcement.

**So now it has a skewer.**

---

# 1. Green can still be wrong

*FALSE GREEN*

I ran into a case where a new execution completed cleanly.

All cases ran.

The external engine returned success.

Expected outputs existed.

Values were finite.

Counts reconciled.

The test suite was green.

But one derived measurement was wrong for a subset of cases.

The implementation had interpreted an event in a way that looked perfectly reasonable locally.

A frozen predecessor result disagreed.

The new implementation reported an event where the predecessor had recorded none.

> **Nothing had crashed.**
> **The system had simply answered the wrong question very successfully.**

**FIG. 01 — GREEN CAN STILL BE WRONG** — *local success can still conflict with preserved meaning*

```text
   LOCAL SUCCESS / CONTRADICTORY REFERENCE

      CODE CHANGED
      TESTS PASSED              ┌──────────────────────┐
      COUNTS RECONCILED         │  FROZEN PREDECESSOR  │
      REPORT SAID SUCCESS ──────│      DISAGREES       │
                                └──────────────────────┘

                     GREEN != CORRECT
```

The first repair was also wrong.

It produced a second plausible interpretation that still failed to preserve the intended meaning.

Only comparison with the earlier reference exposed that the implementation had drifted away from what the field was supposed to represent.

That changed how I thought about baselines.

> **A baseline is not just a rollback point.**
> **It is a causal fingerprint.**

It can tell you:

> **What actually changed?**

And sometimes:

> **What changed even though every test I wrote thinks nothing is wrong?**

That is the first VLD failure mode:

> **semantic drift.**

The implementation changes.

The interpretation moves with it.

The tests follow.

Everything goes green.

And the system is now correct according to a meaning nobody explicitly authorised.

---

# 2. Worse: the meaning can stay right while the evidence is wrong

*A HARDER FAILURE MODE*

Semantic drift was the problem I noticed first.

Then I found something worse.

The semantics can remain completely unchanged.

The contract can still say exactly the right thing.

The implementation can still satisfy every visible requirement.

And the result can still fail to deserve the meaning it claims.

> **That is vacuous satisfaction — formally compliant, practically meaningless.**

Imagine a system that needs to record evidence that an external action actually occurred.

The system knows what was supposed to happen. It knows the intended inputs. It knows what the caller says happened.

**FIG. 02 — SEMANTIC DRIFT VS VACUOUS SATISFACTION** — *the meaning can stay still while the evidence collapses*

```text
   TWO DIFFERENT WAYS TO LOOK RIGHT

   SEMANTIC DRIFT                    │   VACUOUS SATISFACTION
                                     │
   MEANING / CONTRACT                │   MEANING / CONTRACT
          │  MOVES                   │          │
          ▼                          │          ▼
   CONVENIENT NEW MEANING            │   TESTS STAY GREEN
          │                          │          │
          ▼                          │          ▼
   TESTS FOLLOW                      │   EVIDENCE DOES NOT
                                     │   DESERVE THE CLAIM
```

It can hash files, validate structure, build a beautiful provenance record and test dozens of negative cases.

All of those tests can pass.

But if the supposed evidence of "what actually happened" ultimately comes from caller-supplied information, then the system may only be proving this:

> **the caller's statement is internally consistent.**

That is not the same claim.

The field still has the same name.

The contract still has the same wording.

The tests still enforce the same schema.

Nothing has drifted.

The evidence just does not carry the meaning being claimed.

This is where "test harder" stops being an answer.

> **If the sanctioned evidence cannot support the claim, the system must not report the claim as verified.**

> **No amount of internal consistency can manufacture information that is not present in the evidence surface.**

---

# 3. Therefore: implementation freedom is not semantic authority

*IMPLEMENTATION FREEDOM*

There is an easy reaction to unreliable AI coding: specify more.

That can work.

It also throws away a substantial part of what makes coding agents useful.

In practice, implementation agents were often perfectly capable of making local technical decisions: data structures, refactoring, test strategy, local algorithms, helper tools and repairs.

> **Less freedom to redefine the problem.**
> **More freedom to solve the defined problem.**

That is the part of vibecoding I wanted to keep.

The human does not need to prescribe the implementation in detail.

The implementation can move quickly.

What it cannot do is quietly move the definition of correctness with it.

**FIG. 03 — FOUR RULES AROUND IMPLEMENTATION** — *freedom inside a guarded correctness boundary*

```text
   VLD / FOUR RULES AROUND IMPLEMENTATION

   1 / LOCK MEANING                          2 / SUPPORT THE CLAIM
   before output proves itself               evidence must be sufficient
                        ╲                   ╱
                     ┌─────────────────────────┐
                     │     IMPLEMENTATION      │
                     │ technical freedom       │
                     │ inside boundary         │
                     └─────────────────────────┘
                        ╱                   ╲
   3 / PRESERVE DISAGREEMENT                 4 / NON-CIRCULAR NO
   keep contradiction-capable reference      something else can reject

        IMPLEMENTATION MOVES. MEANING DOES NOT MOVE SILENTLY.
```

So VLD starts from one separation:

> **Implementation strategy may vary within an authorised boundary.**
> **Accepted meaning may change only through explicit authority.**

And one clarification matters enormously:

> **VLD protects accepted meaning from unauthorized drift.**
> **It does not give the earliest formulation permanent epistemic privilege.**

The first idea can be wrong.

The specification can be wrong.

The contract can be wrong.

Learning is allowed.

What is not allowed is for implementation pressure to turn that learning into a silent rewrite of success.

> **Do not freeze learning.**
> **Freeze unauthorized reinterpretation.**

---

# 4. Four rules

*FOUR RULES*

The method does not need a new vocabulary for every useful idea.

It needs four rules around the implementation.

## RULE 1 — Lock the meaning before the implementation gets to prove itself

Exploration can happen first.

Prototyping can happen first.

The implementation can discover that the original idea is incomplete or wrong.

But before implementation output is allowed to count as **acceptance evidence**, the consequential meaning and authority boundary need to be explicit.

Otherwise the process can quietly become:

1. build something;
2. see what it conveniently produces;
3. reinterpret success around that output;
4. declare victory.

Sometimes four lines in a work order are enough.

What matters is that we know what the consequential result is supposed to mean, what would count as acceptance, what kind of evidence should support it, and who or what is allowed to change that meaning.

> **This cannot change merely because the implementation would prefer a different answer.**

## RULE 2 — Evidence must be able to support the claim

Before building a verifier, ask:

> **Can the available evidence actually support the thing we want to call verified?**

Sometimes the answer is yes through direct observation.

Sometimes through an accepted model, an external measurement or a trustworthy historical reference.

Sometimes the evidence is only an assertion from the same party whose claim we are trying to verify.

And sometimes the answer is simply:

> **no.**

That is not a test failure.

It is an evidence failure.

The correct output may be **UNKNOWN**, **NOT VERIFIED**, **NOT DEMONSTRATED** or **BLOCKED**.

Those are valid engineering results.

> **If the sanctioned evidence cannot support the claim, the system must not report the claim as verified.**

## RULE 3 — Preserve what needs to remain capable of disagreeing

A baseline is useful because it can disagree.

A predecessor is useful because it can disagree.

Historical evidence is useful because it can disagree.

That only works if we do not rewrite the disagreeable parts into a nicer story later.

I ran into a case where there was effectively a test whose job was to ensure that an old artifact **continued to contain its known wrong values**.

The test would fail if somebody later cleaned the evidence up.

**FIG. 04 — PRESERVED DISAGREEMENT** — *corrections add to the chain rather than cosmetically repairing it*

```text
   PRESERVE WHAT MUST REMAIN CAPABLE OF DISAGREEING

   ATTEMPT 1        ATTEMPT 2        CORRECTION       ATTEMPT 3
   FAILED           FAILED           NEW DECISION     ACCEPTED
      ●────────────────●────────────────●────────────────●
   preserved        preserved        additive         new reference

   CORRECTIONS SUPERSEDE. THEY DO NOT SILENTLY REWRITE THE EVIDENCE CHAIN.
```

That sounds ridiculous until the old artifact is part of the evidence chain explaining why a later decision was made.

Then rewriting it is not cleanup.

It is changing history.

So corrections should be additive.

Failed attempts should remain failed attempts.

Superseded evidence can be superseded without being cosmetically repaired.

A consequential result should remain traceable enough that we can still answer what supports the claim, where that evidence came from, what kind of evidence it is, and what limitations remain.

> **Traceability does not make weak evidence strong.**
> **It makes weak evidence visible as weak.**

> **Preserve the things that must remain capable of disagreeing with the next implementation.**

## RULE 4 — The implementation must not exclusively control every path by which it is declared correct

This is the rule I would protect hardest.

A large green test suite can be an extremely detailed description of the implementer's misunderstanding.

The same human or AI that misunderstands a requirement can encode the same misunderstanding into the implementation, tests, fixtures, documentation and completion report.

> **Five agreeing artifacts are not five independent confirmations if they all inherited the same mistake.**

**FIG. 05 — CIRCULAR VS NON-CIRCULAR VERIFICATION** — *the critical property is the capability to contradict*

```text
   CIRCULAR AGREEMENT / NON-CIRCULAR CONTRADICTION

   CIRCULAR                          │   NON-CIRCULAR
                                     │
        IMPLEMENTATION               │        IMPLEMENTATION
        ╱      │      ╲              │        ╱            ╲
   TESTS   FIXTURES   REPORT         │   TESTS        FROZEN / EXTERNAL
        ╲      │      ╱              │                      │
      DECLARED CORRECT               │                     NO
```

So before acceptance, at least one path must be capable of saying:

> **NO.**

That path might be a frozen predecessor, an independently produced reference, an external measurement, a native behavior check, an adversarial reviewer, another model, a differently constructed implementation or a deliberately designed probe.

The important property is **non-circularity**.

But:

> **non-circular does not mean independent.**

A second model can still use the same wrong input.

A different tool can still share the same parser.

A separate reviewer can still inherit the same framing.

So when the consequence is high enough, prefer a contradiction path with **materially different failure modes**.

Not because every feature needs two implementations and a tribunal.

Because "ask the same system again" is a weak way to challenge a claim that matters.

### Verification has to stop somewhere

*RULE 4 / TRUST BOUNDARIES*

There is one boundary hidden inside this rule.

Follow any verification chain far enough and eventually you reach something else you are trusting:

the external tool, its compiler, its runtime, the operating system, the processor.

If VLD required every one of those layers to be independently re-proven before the layer above could count as evidence, verification would never terminate.

> **VLD does not eliminate trust.**
> **It makes trust explicit and bounded.**

An external tool may be treated as a declared trust anchor when verifying the tool itself is outside the justified scope of the work.

VLD then verifies the part of the chain it actually controls: the intended input, configuration, invocation, observable errors and warnings, output handling and interpretation.

> **Verify your use of the tool.**
> **Do not necessarily re-prove the tool.**

That does not mean the tool is magically correct.

**A trust anchor is a declared assumption boundary, not a proof.**

If the correctness of the tool itself becomes consequential enough, move the boundary and verify more.

The important thing is that hidden trust does not masquerade as verified evidence.

---

# 5. Sometimes the correct outcome is nothing shipped

*FAIL CLOSED*

Coding agents are extremely good at finding a route to success.

Usually that is the point.

It also creates a dangerous gradient.

When the obstacle is local, great.

When the obstacle is actually telling us that the approved claim cannot be demonstrated, "keep solving" becomes the wrong behavior.

I ran into a case where the required evidence could not be mechanically produced through the authorised execution route.

The easy move would have been to weaken what "evidence" meant.

The harder move was to preserve the requirement and admit that the current system could not satisfy it.

> **The implementation was not accepted.**
> **The missing capability stayed missing.**
> **Nothing shipped.**

From a delivery perspective, that looks like failure.

From an engineering perspective, it was the most honest result available.

> **Fail closed is occasionally a remarkably successful failure.**

---

# 6. The contract is allowed to be wrong

*CONTROLLED UNLOCK*

"Lock the meaning" can sound like:

> **freeze the specification earlier and harder.**

That is not VLD.

Contracts are written by humans.

Humans retain their traditional ability to be wrong.

Verification can reveal that two accepted rules conflict, an assumption was too narrow, a required evidence type cannot be produced, a historical interpretation was mistaken, or the specification does not distinguish two materially different cases.

When that happens, VLD should not preserve the bad contract forever.

It should preserve the distinction between:

> **implementation failure**
>
> VERSUS
>
> **decision change**

The execution layer needs to be able to say:

> **I cannot satisfy this without changing what it means.**

That is not permission to change it.

It is a reason to escalate.

Then authority can deliberately unlock the semantic boundary, make a new decision and establish a new reference.

> **The lock is there to stop unaccounted-for change.**

Not legitimate change.

Not learning.

Not correction.

> **Do not freeze learning.**
> **Freeze unauthorized reinterpretation.**

---

# 7. The method, compactly

*OPERATIONAL MODEL*

VLD does not need a fourteen-step lifecycle.

**FIG. 06 — THE VLD METHOD** — *authorise, check, implement + verify, then contradict or escalate*

```text
   THE VLD METHOD / COMPACTLY

   1 / AUTHORISE  ──▶  2 / CHECK  ──▶  3 / IMPLEMENT  ──▶  4 / CONTRADICT

     1 / AUTHORISE    —  meaning + authority boundary
     2 / CHECK        —  can evidence support claim?
     3 / IMPLEMENT    —  + VERIFY
     4 / CONTRADICT   —  or escalate
                                │
          ┌─────────────────────┼─────────────────────┐
          ▼                     ▼                     ▼
   IMPLEMENTATION WRONG   EVIDENCE INSUFFICIENT   MEANING WRONG
        REPAIR                NOT VERIFIED       AUTHORITY UNLOCK

   IF THE CLAIM SURVIVES: PRESERVE EVIDENCE -> ACCEPT / INTEGRATE
```

That is the skewer.

The implementation can move.

The relevant layers should not quietly stop referring to the same thing.

---

# 8. Use the heavy machinery where meaning becomes consequential

*APPLICABILITY*

The biggest danger with VLD is that it becomes unbearable.

So this needs to be explicit:

> **Most code changes do not need heavy VLD.**

A useful first question is:

> **Will this output become something later work or the outside world is expected to trust?**

One especially strong subtype is:

> **Will this output later be treated as a fact without being re-derived?**

Full VLD becomes interesting where an output changes or expresses authoritative meaning, authorises or attests a consequential or difficult-to-reverse external effect, or becomes a future reference fact that later work is expected to trust without re-derivation.

Persistence alone is not enough.

A commit is persistent. A log can be persistent. A screenshot can be persistent.

That does not make all of them worth governing heavily.

> **Use the heavy machinery where meaning becomes consequential.**
> **Vibe the rest.**

**Nobody needs constitutional law for a button margin.**

---

# 9. Where the Human Sandwich fits

*TWO DIFFERENT PROBLEMS*

The Human Sandwich Model and VLD solve different problems.

The Human Sandwich describes an authority architecture:

> **COULD → SHOULD → DID**

It asks:

> **Who gets to decide what becomes real?**

Verification-Locked Development is narrower.

It operates around consequential implementation and execution.

It asks:

> **How do we verify that what became real still means what was authorised — and that the evidence actually supports that claim?**

**FIG. 07 — AUTHORITY VS VERIFICATION** — *separate frameworks with a natural fit*

```text
   AUTHORITY ARCHITECTURE / VERIFICATION DISCIPLINE

   HUMAN SANDWICH MODEL              │   VLD
                                     │
   COULD -> SHOULD -> DID            │   CONSEQUENTIAL DID
                                     │   implementation / evidence / verification
   Who gets to decide                │
   what becomes real?                │   Did execution still mean
                                     │   what was authorised?

              SEPARATE FRAMEWORKS. NATURAL FIT.
```

So VLD can live inside the DID side of the Human Sandwich.

But it is not the Human Sandwich Model.

The sandwich decides where authority sits.

The skewer helps keep implementation, evidence, verification and accepted meaning referring to the same thing while the work moves.

**That is enough sandwich engineering for one paper.**

---

# 10. None of this is especially exotic

*THE SYNTHESIS*

Preregistration-like commitment is not new.

Traceability is not new.

Fail-closed behavior is not new.

Independent challenge is not new.

Preserved baselines are not new.

Orthogonal evidence is not new.

What changed for me was the balance.

> **Implementation suddenly became cheap.**
> **Correctness did not.**

AI can now produce enormous amounts of plausible implementation very quickly.

That makes implementation freedom easier to grant.

It also makes semantic drift, vacuous satisfaction and self-confirming verification easier to produce at scale.

VLD is my attempt to combine old high-reliability instincts around a new engineering condition:

> **implementation can move extremely fast without automatically gaining authority over what success means.**

That is the contribution.

Not a claim that every individual mechanism was invented here.

---

# 11. A working definition

*WORKING DEFINITION*

> **Verification-Locked Development** is a development practice that keeps implementation flexible within explicit boundaries while preventing implementation pressure from silently changing accepted meaning or what counts as sufficient evidence. Consequential claims must be supportable by the available evidence and survive at least one non-circular path capable of contradicting the implementation before acceptance. Changes to accepted meaning require explicit authority rather than implementation-side reinterpretation.

The serious definition is useful.

The working version is still better:

> **Vibe the implementation.**
> **Lock the meaning.**

And the rule I would protect hardest is still:

> **The implementation must not exclusively control every path by which it is declared correct.**

---

# 12. Experimental note — capability substitution (companion)

*EXPERIMENTAL — NOT PART OF VLD ITSELF*

VLD does not increase producer capability. By locking meaning, bounding authority, preserving
contradiction, and supplying discriminative external checks, it may reduce the residual
judgment the producer must supply.

That substitution holds only to the extent that the governing meaning and verification oracle
are adequate for the claim. Shared wrong meaning and shared wrong verification can still produce
a confidently verified failure.

This is an experimental field hypothesis, supported by local operational observation plus
relevant external mechanism evidence — not yet a validated generic routing law. It is not
restated here; see the supplied `VLD_Capability_Substitution_Experimental_v0.1.md`.

---

# Final observation

## The part I would keep

I started doing this because AI could write code much faster than I wanted to micromanage it.

The obvious solution seemed to be tighter control over the agent.

What I ended up doing was almost the opposite.

I became stricter about meaning so I could become looser about implementation.

> **The agent could choose the path.**
> **It could not quietly move the destination.**

It could not turn missing evidence into evidence.

It could not rewrite inconvenient history.

It could not declare its own interpretation correct merely because its own tests agreed with it.

And when reality contradicted the specification, the contradiction could remain visible instead of being repaired into submission.

That is the part I would keep.

Not making AI code less aggressively.

Making aggressive AI coding **arguable with**.

> **That is the part I would keep.**
>
> **Not making AI code less aggressively.**
>
> **Making aggressive AI coding arguable with.**
>
> **Because vibecoding is extremely convenient.**
>
> **Unfortunately, reality continues to have opinions.**
