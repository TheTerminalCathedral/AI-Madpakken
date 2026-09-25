# The Human Sandwich Model

## A practical pattern for separating AI reasoning, human authority and AI execution

```text
COULD  ──────▶  SHOULD  ──────▶  DID
  ▲                                │
  └────────────────────────────────┘
```

**Practice-based report — August 2026**
`COULD → SHOULD → DID`

---

I did not set out to invent an AI framework.

I was trying to get complicated work done without doing every mechanical step myself — and without letting an AI quietly turn its own suggestions into project reality.

The arrangement that emerged was almost embarrassingly simple:

An AI helped me explore what **could** be done.

I decided what **should** be done.

Another AI worked against actual project state and recorded what **did** happen.

I started calling it the Human Sandwich Model because there was an AI on each side of me and the name was stupid enough to remember.

The useful part was never really the sandwich.

It was the decision boundary in the middle.

But when I went back and examined how several real workflows had actually operated, something else became obvious:

> **The Human Sandwich is an authority structure. The work itself is a recursive loop.**

That distinction turned out to be much more interesting than the original three boxes.

And it also clarified who this pattern is actually for.

Not everyone using AI needs this.

It starts becoming useful when AI work lasts long enough, changes enough persistent state or spans enough contexts that **authority and context themselves become architectural problems**.

**In other words:**

> **This is for people whose AI use has started behaving like a system rather than a chat.**

---

# 1. The stupidly simple idea

The shortest version of the model is still useful:

**FIG. 01 / AUTHORITY STRUCTURE**

```text
   LAYER 1               HUMAN               LAYER 2
   COULD      ──────▶    SHOULD    ──────▶   DID
                                   ║
                               AUTHORITY

   LAYER 1 / COULD   :  explore, challenge, compare, recommend
   HUMAN   / SHOULD  :  decide, accept / reject, modify, authorise
   LAYER 2 / DID     :  execute, validate, record, stop / escalate
```

The first AI can speculate, challenge me, compare alternatives and temporarily entertain bad ideas.

None of that becomes operational merely because it was said.

I can reject it.

I can change it.

I can combine parts of several suggestions.

Only after I make the decision does something cross into execution.

That matters because *human-in-the-loop* can describe some surprisingly weak arrangements.

A system might interpret the problem, frame the solution, refine its own proposal, act on it and only then ask a human whether the result looks okay.

The human was technically in the loop.

They just arrived after most of the interesting decisions.

The question I care about is therefore not:

**Was a human involved?**

It is:

**Who controlled the point where a proposal became authorised action?**

That is the boundary the sandwich is trying to make visible.

## Clipboard middleware

There is also a fake version:

**AI #1 writes a prompt → human copies it → AI #2 runs it**

If all I did was move text from one window to another, I did not become meaningful human authority.

I became clipboard middleware.

The human layer matters when something actually happens there:

- an assumption is rejected;
- the goal is changed;
- alternatives are combined;
- scope is narrowed;
- a source is accepted or rejected;
- execution is authorised;
- execution is stopped;
- or a technically plausible answer is judged to be the wrong answer.

Human authority does not require human labour.

It requires human decisions.

---

# 2. Then I looked at what was actually happening

The three-box model felt right in practice, but I wanted to know what the conversations around it actually looked like.

Who normally started the work?

Who steered it?

How many times did the human and the upstream AI go back and forth before anything was authorised?

Was Layer 2 really just an executor?

What happened when execution failed?

Did the workflow actually move:

**AI → HUMAN → AI**

or was that diagram hiding most of the work?

I asked several AI threads that had participated in real workflows resembling this pattern to reconstruct their own role and interaction history.

They were asked to describe what they could actually observe, distinguish observation from interpretation and avoid inventing precise counts where the history did not support them.

The underlying cases were anonymised at the domain level. The point was the interaction structure, not the private work itself.

This was not a controlled study.

It was a practice-based examination of a small number of workflows I had actually used.

The participating AI threads also did not have equal visibility into those workflows.

That limitation produced one of the most useful findings.

## Every agent sees a different sandwich

A downstream execution agent may observe:

**Human → detailed specification → Layer 2**

From its perspective, the human simply arrived with a highly developed instruction.

Several execution-side reconstructions could not reliably describe a separate upstream reasoning process because their available record began at or near the specification stage.

But an upstream conversation could reveal how that same type of specification was created:

**Human → L1 → Human → L1 → Human → authorised specification**

The specification was not the start of the reasoning process.

It was the end product of one.

The upstream process commonly involved exploration, rejection, disagreement, refinement and eventually compression into something another context could execute.

SO:

> **A clean handoff does not imply a simple decision process.**

It may only mean that the mess happened somewhere else.

That also means workflow reconstruction is perspective-dependent.

A downstream system cannot reliably tell us how many upstream reasoning cycles occurred if it never saw them.

That sounds obvious once written down.

It is surprisingly easy to forget when looking at agent logs.

---

# 3. What the simple diagram gets wrong

The sandwich still describes the authority split well.

As a timeline, it is much too tidy.

## Both sides reason

The easiest misreading is:

**Layer 1 thinks. Layer 2 does.**

That is not what the workflows showed.

Execution agents also performed substantial reasoning.

They inspected state, found contradictions, selected technical implementations, tested assumptions, verified outputs and sometimes refused to continue when current state no longer supported the authorised instruction.

The more useful distinction is therefore:

**BEFORE THE AUTHORITY BOUNDARY**

The reasoning can ask:

- What are we actually trying to achieve?
- Which interpretation is right?
- What trade-off do we want?
- Should the rule itself change?
- Is this even the right problem?

**AFTER THE AUTHORITY BOUNDARY**

The reasoning can ask:

- What is currently true?
- How should the authorised goal be implemented?
- Which technical approach is valid?
- Are the required inputs present?
- Is the requested action still inside scope?
- Does validation permit me to continue?

Reasoning can happen on both sides.

What does not automatically cross the boundary is **decision authority**.

> **Reasoning can exist on both sides of the human boundary. Decision authority does not.**

## Who actually starts and steers the loop?

The workflows did not reveal one fixed conversational leader.

The trigger could come from several places:

- the human starts with a new goal;
- Layer 2 returns a failure or discrepancy;
- live state changes;
- validation exposes a bad assumption;
- or an AI notices something that requires escalation.

Once exploration begins, control is often shared.

The AI may lead decomposition, comparison and technical investigation.

The human may overturn the framing entirely.

In one particularly clear case, the reasoning AI initially produced a coherent explanation for why an existing execution rule made sense.

The human rejected the assumption behind that explanation.

Several further exchanges then produced a new operational distinction and eventually a new downstream instruction.

The final rule did **not** exist in the first AI response.

It emerged from disagreement.

So "the human leads" is too simple.

"The AI leads" is also wrong.

A better description is:

> **co-steering with asymmetric authority.**

The AI can strongly influence where the conversation goes.

The human decides which direction becomes authorised.

---

# 4. The handoff is a compression boundary

The handoff turned out to be one of the most consistent parts of the workflows.

Layer 2 usually did **not** receive the full upstream conversation.

It received something more like:

**decision + constraints + authorised evidence + acceptance criteria + stop conditions**

Execution-side workflows commonly received exact objectives, allowed inputs, protected state, tests, restrictions and required outputs rather than raw exploratory transcripts.

The upstream side described the same transformation from the opposite direction: conversation was reduced to an execution-ready contract.

That makes the handoff a form of deliberate lossy compression.

**FIG. 02 — THE HANDOFF IS A COMPRESSION BOUNDARY**

```text
   hypothesis              ┐                        ┌ OBJECTIVE
   alternative             │                        │ CONSTRAINTS
   rejected idea           │        HUMAN           │ AUTHORISED EVIDENCE
   constraint              ├──▶  AUTHORISE /   ──▶  ┤ LOCAL DECISION SCOPE
   source                  │      COMPRESS          │ ACCEPTANCE CRITERIA
   temporary contradiction │                        │ STOP CONDITIONS
   joke                    │                        │
   decision                ┘                        └
```

And lossy is not necessarily bad.

Layer 2 usually does not need:

- every rejected idea;
- every abandoned hypothesis;
- every joke;
- every temporary contradiction;
- every argument that led nowhere.

In fact, passing all of that downstream may make execution worse by forcing Layer 2 to reconstruct which parts were decisions and which parts were merely thinking out loud.

But compression can also become destructive.

If a constraint is transferred without enough context to recognise when it applies, Layer 2 may faithfully implement the words while violating the intent.

So a good handoff should preserve at least:

- the authorised objective;
- the constraints that materially shape it;
- authoritative sources or state;
- what Layer 2 is allowed to decide locally;
- what must come back to the human;
- acceptance criteria;
- and stopping conditions.

The goal is not to preserve the reasoning transcript.

It is to preserve the **decision** well enough that downstream reasoning does not need to invent it again.

---

# 5. What happens after authority

Once a decision crosses the boundary, Layer 2 does not need to become passive.

Quite the opposite.

Useful downstream behaviour in the examined workflows included:

- state inspection;
- contradiction detection;
- technical design choices;
- implementation;
- validation;
- regression checking;
- provenance recording;
- and escalation when authority was missing.

That gives Layer 2 real initiative.

BUT:

> **Initiative is not authority.**

An execution agent can discover that a source is missing.

It can say that the current state contradicts the instruction.

It can propose a safer implementation.

It can stop.

What it should not do is silently redefine the goal so that execution can continue.

## Authority can be staged

The workflows also showed that "approved" is not always one binary state.

A human might authorise:

**inspect**

then later:

**modify locally**

then:

**validate**

and only after another review:

**publish or deploy**

That gives us a very practical distinction:

> **You may build it does not necessarily mean you may publish it.**

**FIG. 03 — AUTHORITY CAN BE STAGED**

```text
                  INSPECT              examine and understand
                     │                 current state
   AUTHORISED        ▼
   SCOPE      MODIFY LOCALLY           make changes within
                     │                 authorised scope
                     ▼
                  VALIDATE             verify and confirm
                     │                 changes
   ══════════════════╪══════════════════════════════════
              HUMAN REVIEW
        AUTHORISATION REQUIRED
                     ▼
            PUBLISH OR DEPLOY          release beyond authorised scope
                                       REQUIRES ADDITIONAL HUMAN APPROVAL
```

The same idea applies elsewhere.

An agent might be allowed to generate candidates but not select one.

It might repair a known defect but not redesign the objective.

It might inspect live state but not change it.

This is where the human bottleneck question becomes important.

If every tiny choice has to come back for approval, the human either becomes painfully slow or eventually starts clicking "yes" without thinking.

That is not meaningful authority either.

The solution is not simply **more approvals**.

It is better **authority granularity**.

Give the execution layer room to make decisions already inside the authorised problem.

Escalate when the problem itself changes.

---

# 6. Execution breaks the linear model

The biggest thing missing from:

**L1 → Human → L2**

is that Layer 2 produces information.

Execution interacts with reality.

Reality may answer back.

The result can reveal:

- unexpected state;
- a missing source;
- an implementation constraint;
- a validation failure;
- a probabilistic failure;
- a wrong assumption;
- or evidence that the original decision should be reconsidered.

**THE RECURRING PATTERN WAS CLOSER TO:**

**decision → implementation → validation/new state → human interpretation → revised decision → implementation**

Execution creates information.

Information changes reasoning.

Reasoning changes the next execution.

This is why the sandwich is a good authority diagram and a bad sequence diagram.

**The sequence is recursive.**

**FIG. 04 / OPERATIONAL MODEL — The work itself is a recursive loop**

```text
          ┌───────────────────── TRIGGER / STATE ─────────────────────┐
          │                                │                          │
          ▼                                ▼                          ▼
      LAYER 1                            HUMAN              LAYER 2
      COULD               ──────▶        SHOULD    ──────▶    DID ──────────────────┐
                                                ║                                   │
   exploration              interpretation      ║  implementation                   │
   reconsideration          decision            ║  validation                       │
   goal-forming reasoning   authorisation       ║  state interaction                │
                            changed objective   ║  bounded repair                   │
                            authority boundary  ║  execution                        │
                                                ║        │                          │
                            APPROVE             ║        ▼                          │
                            authorised decision ║   LIVE STATE                      │
                            crosses boundary    ║        │                          │
                                                ║        ▼                          │
                                                ║     RESULT                        │
                                                     │           │                  │
                                                     ▼           ▼                  │
                                                  REPAIR      RETHINK               │
                                            discrepancy within  changes premise,    │
                                            authorised repair   goal, authority     │
                                            policy              or interpretation   │
          ▲                                          │           │                  │
          └─────────── VALIDATE / LAYER 2 ───────────┘           └──────────────────┘
```

The horizontal line still shows the authority structure:

**COULD → SHOULD → DID**

The loop shows the actual interaction.

Layer 2 is not necessarily an endpoint.

Its output may become the next Layer-1 input.

## When should failure return upstream?

Not every defect deserves another human conversation.

If the failure is already classified inside an authorised repair policy, Layer 2 can continue.

**Known bounded failure → repair → validate**

But if the failure implies that the premise may be wrong, the system has reached a different kind of boundary.

Examples include:

- unresolved source authority;
- broken upstream input;
- unexpected state;
- missing decisions;
- repeated failure suggesting the chosen approach is wrong;
- or anything requiring the goal to be reinterpreted.

Layer 2 may be capable of recognising that condition.

Recognition does not grant permission to solve it by changing the goal.

That comes back through the human.

---

# 7. The layers are roles, not identities

The original diagram naturally looks like three actors:

**AI #1 → HUMAN → AI #2**

That is a useful introduction.

It is not a requirement.

The layers are better understood as **governed roles**.

They can be instantiated by:

- different AI models;
- different agents;
- separate conversations with the same general AI system;
- contexts with different tools or project state;
- a human executor downstream;
- or, in some cases, different operating modes of the same AI around an explicit human authority gate.

The stable thing is the authority topology.

The implementation can vary.

**FIG. 05 — SAME TOPOLOGY, DIFFERENT IMPLEMENTATIONS**

```text
   AI ROLE A       ──────▶  ║ HUMAN ║  ──────▶   AI ROLE B
   CONTEXT A       ──────▶  ║ HUMAN ║  ──────▶   CONTEXT B
   AI REASONING    ──────▶  ║ HUMAN ║  ──────▶   HUMAN ACTION
   AI / MODE A     ──────▶  ║ HUMAN ║  ──────▶   AI / MODE B

   Context separation can separate jobs.
   It does not necessarily separate biases.
```

The boundary matters more than the logo printed on either side of it.

## Contexts can instantiate roles

This became especially obvious while preparing this report.

I used separate AI conversations for different jobs.

One context was used for core reasoning and editorial work.

Another was asked to behave as a close technical peer reviewer.

Another was given responsibility for visual and publication design.

Outputs moved back through me before being sent elsewhere.

The conversations used the same general class of AI system.

What made them different was not model identity.

It was:

- context;
- role;
- instructions;
- available evidence;
- mandate;
- and what each conversation was allowed to decide.

That can still create meaningful separation.

But only if the human does something meaningful at the boundary.

If one thread produces a prompt and I blindly paste it into another, nothing interesting has happened.

That is still clipboard middleware.

If I reject parts, combine ideas, change the objective, decide what is authoritative and pass a bounded specification into a context with a different job, then the separation is operationally real.

> **Contexts can instantiate layers. Multiple chats alone do not create architecture.**

## Operational separation is not independent judgement

There is also an important limitation.

Separate contexts can separate jobs.

They do not necessarily separate biases.

Two conversations using the same model family may still share:

- similar priors;
- failure tendencies;
- knowledge limits;
- stylistic habits;
- and systematic blind spots.

So context separation should not be confused with epistemic independence.

Opening another instance of the same model does not automatically create an independent verification system.

If genuinely independent challenge matters, other forms of separation may also matter:

- different sources;
- different models;
- independent measurements;
- specialist human expertise;
- or genuinely independent review.

That is a different problem from the authority architecture.

A useful shorthand is:

> **Role separation does not guarantee context separation, and context separation does not guarantee independent judgement.**

---

# 8. Who actually needs this?

The profession is less important than the behaviour.

The model becomes relevant when the work has stopped behaving like a disposable conversation.

Typical symptoms include:

- one enormous chat is carrying too much project history;
- old possibilities and current decisions are becoming mixed;
- exploratory discussion leaks into execution;
- downstream systems have to guess which ideas were actually approved;
- one context has access to live state another does not;
- several specialist AI roles are involved;
- execution creates evidence that needs interpretation elsewhere;
- or "what does this context know and what may it change?" has become a real engineering question.

That describes several common users.

## Engineers separating reasoning, implementation and QA

One context may discuss architecture.

Another may work directly against a repository or toolchain.

Another may critique the result.

The problem is not how to use three AIs.

It is:

**Which context is authoritative for what, and what is allowed to cross between them?**

## Founders separating exploration from operations

Strategic conversations contain hypotheses, alternatives and deliberately provocative ideas.

Operational systems need decisions.

Brainstorming sentences should not quietly become instructions.

## Creative and technical production workflows

Development may need freedom.

Production needs explicit choices.

Critique should be allowed to challenge the result without automatically modifying it.

The same authority pattern still applies.

## Long-running stateful projects

This may be the clearest case.

The project accumulates:

- history;
- persistent files or state;
- irreversible or costly decisions;
- multiple tools;
- multiple AI contexts;
- and enough complexity that one mega-thread becomes actively unhelpful.

At that point, context has become infrastructure.

That is where this pattern becomes annoyingly practical.

---

# 9. What the model does — and does not — mean

The model is not a claim that every useful AI workflow needs two different AI systems.

It does not even require AI on both sides.

The meaningful questions are:

- what is still a proposal;
- what has become an authorised decision;
- who may change state;
- what autonomy exists inside that scope;
- what context has access to which evidence;
- and what conditions force the work back across the authority boundary.

Nor are all implementations equivalent.

A single AI may technically operate on both sides of a human approval event.

But if it retains the entire persuasive reasoning history and then executes its own proposal after receiving "okay", that has different risk properties from a genuinely isolated downstream context.

The model identifies the authority boundary.

It does not magically provide independence, clean context or good judgement.

And it is allowed to be overkill.

If someone is:

- asking for dinner ideas;
- summarising an article;
- writing a disposable message;
- brainstorming names;
- performing a one-shot calculation;
- or generating something where a bad result costs almost nothing,

they probably do not need a Human Sandwich.

My rule of thumb remains:

> **If a wrong autonomous action costs more than asking me once, the boundary is probably worth having.**

The point is not to turn every interaction with AI into miniature constitutional law.

It is to become explicit when interpretation is about to become consequential action.

---

# Revised working definition

I would now define the model this way:

> **The Human Sandwich Model is a human-governed AI workflow pattern in which exploratory or goal-forming reasoning is separated from consequential execution by an explicit human authority boundary. The layers are governed roles rather than fixed agent identities: they may be implemented through different models, contexts, tools or human/AI combinations. AI systems may reason and act autonomously on either side of the boundary, but the authority to define or materially change the objective remains human. Execution can produce new evidence that returns through the human and reopens upstream reasoning, making the practical workflow recursive rather than purely linear.**

The shorthand can stay:

**COULD → SHOULD → DID**

It is easy to remember.

And it is usefully incomplete.

---

# Final observation

The name still makes me laugh a little.

That is probably part of why I remember it.

But after looking more closely at the workflows, the useful idea is no longer simply:

**There is an AI on each side of the human.**

It is that autonomy, reasoning, context and authority are different things.

The upstream role can explore aggressively because proposals are cheap.

The downstream role can execute aggressively because its scope is explicit.

Different contexts can specialise without pretending to be independent minds.

Both sides can show initiative.

Both sides can reason.

Neither needs to own the whole workflow.

The human does not remain responsible by manually doing everything.

The human remains responsible by controlling where the important boundaries move.

That is the part I would keep:

**possibility becomes intention,**
**intention becomes authority,**
**execution produces evidence,**
**and evidence is allowed to change the next decision.**

The layers are roles.

The sandwich is the authority structure.

The work is the loop.
