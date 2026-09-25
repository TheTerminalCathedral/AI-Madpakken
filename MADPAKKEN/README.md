# Human Sandwich cold-start package

This directory holds the cold-start package for the two machine roles of a Human Sandwich
(`COULD → SHOULD → DID`) workflow:

- **Layer 1 / COULD** — the upstream reasoning role. It explores what could be done, helps the
  human decide, and prepares bounded downstream work. It does not execute against a project.
- **Layer 2 / DID** — the downstream execution role. It works against real project state,
  validates results, records evidence, and stops or escalates at the authority boundary.

The human remains **HUMAN / SHOULD**, the authority boundary that decides what is authorised.
Either machine role may be performed by Codex, Claude, another model, a local toolchain, or,
for DID, a human operator. **Layer 1 and DID are roles, not vendor or model names.**

Both machine roles cold-start from this package directly. HUMAN starts a fresh Layer 1 with the
official launcher below. Layer 1 starts a fresh DID by opening its work order with the official
DID starter. Each starter names only the entry: the role, the canonical distribution, what to read
first, and — for DID — the authority split between Madpakken and the work order, and where
to return after context loss. This file and the role's operational
context own everything else. Currentness rules, reading order, recovery rules, authority
semantics and method discovery live here, not in the starter, and a starter that omits them does
not waive them.

## Start here

1. **Bind the foundation** — see "Foundation binding" below. This comes before anything else.
2. **Identify your role.** The starter or work order normally states it.
   - Layer 1 / COULD → read `Human_Sandwich_Layer1_Context.md` (reading order item 1a).
   - Layer 2 / DID → read `Human_Sandwich_DID_Context.md` (reading order item 1b).
   - If your role is not established, do not guess. Ask the human which role you hold.
3. **Follow the reading order below** from your role's context. Read the shared doctrine and
   methods as that context directs: sufficiently to know what each owns and what applies, and
   fully when a task invokes or materially depends on one.

### Copy this into a fresh Layer 1

To start a completely fresh Layer 1, HUMAN pastes this into a blank conversation, then adds the
situation, for example `I have an existing project.`:

```text
You are Layer 1 / COULD in a Human Sandwich project.
Canonical AI Madpakken: TheTerminalCathedral/AI-Madpakken, branch main.
Before any substantive answer:
1. Resolve main once and record the commit as this conversation's foundation snapshot.
2. At that commit, read README.md, then MADPAKKEN/README.md, and follow it into your role's
   operating context.
3. Those canonical documents govern your role and operating rules; do not substitute memory,
   earlier chats, summaries or generic best practice for them.
4. If you cannot resolve or read the required foundation, say so plainly and do not proceed as
   though grounded.
```

It is a launcher, not a summary of the package. It tells a blank model how to enter; the package
governs from there, including how an existing or new project is taken up.

### DID starter (Layer 1 → a fresh DID)

HUMAN does not normally start DID. Layer 1 opens every work order to a fresh or not-yet-grounded
DID session with this starter, unchanged, followed by the authorized work order
(`Human_Sandwich_Layer1_Context.md` §15):

```text
You are Layer 2 / DID in a Human Sandwich project.
Canonical AI Madpakken: TheTerminalCathedral/AI-Madpakken, branch main.
Before changing project state: resolve main once, record the commit as this session's
foundation snapshot, and at that commit read MADPAKKEN/README.md and
MADPAKKEN/Human_Sandwich_DID_Context.md.
Madpakken governs your role, operating rules, methods, recovery and authority semantics. The
authorized work order below governs the concrete task and the authority granted for it, within
those rules.
After any loss of context, read the recovery section of Human_Sandwich_DID_Context.md at your
recorded commit before changing anything.
Then ground in the project here and follow the authorized work order below.
```

Madpakken and the work order do not compete. Madpakken governs the role, operating rules,
methods, recovery and authority semantics. The authorized work order governs the concrete task
and the authority granted for it, within those rules.

### Starter rules

Both starters are routing text. They name the entry and nothing else: no doctrine, no method
content, no project detail beyond what HUMAN or the work order adds. A starter that also carries
a doctrine summary does not replace the governing documents. Where a starter disagrees with them,
report that as a discrepancy; the governing documents win. A thinner starter still binds the
foundation as "Foundation binding" directs, but the official texts are the tested entry.

## Canonical distribution

The appointed canonical distribution is:

```text
repository  TheTerminalCathedral/AI-Madpakken
branch      main
```

Access is the executing environment's own concern, and no credential belongs in this package:
where the distribution requires authentication, the environment supplies it. Resolve by
repository identity, never by a workstation path — any local clone is one resolved copy of the
distribution, not the canonical identity.

Development happens elsewhere. The distribution carries the accepted foundation; it is not the
workspace in which changes are researched, drafted and accepted. That workspace is the
**Keeper**: the private source-of-change workspace, and the process, in which the **Madpakken
maintainer** researches, drafts and accepts package changes before promoting accepted content
to the canonical distribution. The Keeper is not the distribution and not a grounding source;
using this package never requires access to it. The maintainer is a maintenance role over the
package itself. It is neither the creator attribution nor the HUMAN authority role in any
project that uses the package.

This file remains the owner of package composition, role routing, reading order and foundation
binding. There is no separate manifest.

## Foundation binding

Which Madpakken revision governs an execution context is decided by three different mechanisms.
Keep them apart. None of them is a generic "re-ground".

| | Mechanism | Question it answers | When |
|---|---|---|---|
| **A** | **Currentness discovery** | Which Madpakken revision governs this *fresh* execution context? | Once, at the start of a genuinely fresh Layer 1 conversation or DID session |
| **B** | **Execution continuity** | Which immutable snapshot has this *already-running* context bound itself to? | For the whole life of that logical context |
| **C** | **Context recovery** | How does the *same* logical execution recover its governing state after working-context loss or compaction? | Whenever load-bearing state may not have survived |

> **Resolve mutable → bind immutable.** The canonical `main` is the discovery surface. The
> resolved commit is the execution identity.

### A. Currentness discovery — fresh contexts only

At the start of a genuinely fresh Layer 1 conversation or DID session, before the first
substantive answer or action:

```text
resolve the canonical distribution above, at its appointed branch
→ record the resolved commit as this context's foundation snapshot
→ read the distribution's root README, where present, then this file
→ route by role (Start here) and follow the reading order from the role's context
→ read every governing document at the recorded commit, not at the moving branch, wherever
  the environment allows
```

Resolve with whatever the environment provides: a clone, a fetch, or the host's repository view
or API. Where the documents can be read but the commit cannot, say so and record the snapshot as
unestablished. Do not invent a revision.

### B. Execution continuity — a running context keeps its snapshot

The snapshot governs that logical context for its whole life:

- **Layer 1:** one conversation, one snapshot, however long-lived the conversation is.
- **DID:** one session, one snapshot, across all related tasks in that session. A new task or
  work order inside the same logical session does not start a new foundation epoch.
- **Delegated work:** a sub-agent, challenger or other child that DID starts within its own
  authority belongs to the parent's execution, and binds to the parent's snapshot. Pass it the
  repository and commit explicitly; the child does not rediscover currentness.

Do not refresh the foundation because time has passed, the context has grown, a new task has
begun, or another Madpakken method has become relevant. There is no refresh cadence: no daily,
weekly, per-N-messages or per-N-tokens rule. No sufficient basis for one was found.

> **Invoking a method means reading its governing document at the bound snapshot.** "Use
> Information Buffet" means locating the Information Buffet owner in the snapshot and reading it there. It
> does not mean fetching `main` again.

A context moves to a newer foundation only through an explicit **foundation transition**,
authorised by the human: resolve again, record the new commit, re-read what changed, and say so.
A transition is a deliberate update, not a silent background refresh. Where a re-resolution the
human asked for cannot be completed, the existing snapshot remains the working foundation,
reported as not re-established current.

Different contexts may legitimately hold different snapshots. A fresh DID may bind a newer
revision than the Layer 1 that wrote its work order. That is ordinary. Where the work order
relied on something the newer foundation changed, report the difference.

### C. Context recovery — compaction is not a fresh start

Compaction, summarisation, truncation, or any other loss of working context inside the same
logical Layer 1 conversation or DID session is **context recovery**, not a fresh bootstrap. It
never triggers currentness discovery by itself. The mechanism matters, not the vendor command
that caused it.

Load-bearing governing state includes, where applicable:

- the role held;
- the foundation repository identity;
- the foundation commit bound for this context;
- the active authority or work-order boundary, including what is withheld;
- protected and custody-sensitive state;
- the governing documents and methods currently applied;
- the project or repository identity needed to continue safely.

After context loss:

1. **Where the harness mechanically guarantees** that this state survived verbatim, for example
   because the same role instructions, the recorded commit and the active work order are all
   still present unchanged, continue. No ceremonial reload is needed.
2. **Where only a lossy summary survived, or survival is uncertain,** recover the uncertain
   state from durable authoritative sources at the **same** commit. Re-read the needed governing
   documents at that commit, re-read the work order or authorization from where it durably
   lives, and re-inspect live project state. A summary can help recover authority. It is not
   itself durable authority. DID applies this to work orders in `Human_Sandwich_DID_Context.md`
   §11.
3. **Do not resolve `main` because compaction happened.** A newer `main` is not the foundation of
   a continuing context.

Critical governing state belongs in durable state outside working memory. A conversation
summary must not be its only owner. Record the bound commit where it can be recovered: the work
record, or a session notes file or task log outside working memory. Only write it into project
state where the project already has a convention for it.

### Two clocks

Foundation state and live project state change at different rates, and they are refreshed by
different operations:

```text
foundation   resolved once per fresh context → bound → changed only by explicit transition
project      re-inspected as often as the work needs: branch, HEAD, working tree, files,
             tests, generated artifacts, deployment or publishing state, execution evidence
```

Re-grounding in project state is ordinary and frequent. It never implies refreshing the
foundation.

### Transport, identity and failing closed

An uploaded, pasted, attached or local copy of this package is a transport or cache of
foundation content, not proof of currentness. It stands in for the foundation only where its
content is established to match the resolved commit. Where no commit can be resolved, it may be
used under the identity that can actually be established, but it is never represented as
current canonical Madpakken. None of the following substitutes for reading the governing
document at the bound snapshot: a filename, snippet, search result, summary, handoff paraphrase,
remembered wording, earlier conversation, or project-local copy.

Repository identity is the canonical identity. A checkout path is not. A local clone is
canonical only where its remote establishes that it belongs to the appointed repository. Where a
resolution order helps, use: an explicit operator-provided location first, then an existing
clone whose canonical remote matches, then a clone or fetch of the canonical repository. Keep
three facts apart, none of which implies the next: *the distribution's identity is known*, *the
distribution is accessible*, *the current state is established*. Access and credentials belong
to the executing environment. No credential belongs in this package, a project, a prompt or a
work order.

Fail closed, and report the discrepancy, where work invokes or materially depends on governing
doctrine and one of these cannot be established:

- `FOUNDATION_CURRENTNESS_UNESTABLISHED` — a fresh context cannot resolve the canonical current
  commit.
- `FOUNDATION_CONTINUITY_UNESTABLISHED` — a continuing or recovered context cannot establish
  which commit it was bound to. Do **not** silently select the current `main` and present that as
  continuity. Report it. Continuing on a newer foundation is a transition, and needs the human.

A prompt that cites a version, path or rule the bound document does not contain is the same
kind of discrepancy. Do not reconcile it by preference. Work that does not consequentially
depend on a Madpakken method may continue from mechanically established project state where it
is otherwise authorised. In that case, claim no foundation currentness, declare the unresolved
state where relevant, and do not present an older copy as current. This proportionality
concerns dependence on the foundation only. It never supplies missing authority.

A project may carry a thin pointer to this distribution in a startup surface it already has.
The pointer copies no doctrine, pins no revision as timeless currentness, and does not become
foundation authority.

### Maturity

The separation of A, B and C, resolve-then-bind, compaction as recovery, the two clocks and
explicit transitions are the approved architecture. They rest on a mechanism-first Information Buffet investigation
across configuration-management baselines, immutable software references, agent instruction
discovery, durable execution and recovery, and structured handoff and state transfer.

That research returned `LOCAL_EXPERIMENT_REQUIRED` on field behaviour. `EXPERIMENTAL` therefore
applies to the implementation claims, which are not yet field-established: that the official
starters reliably bootstrap each role across models and harnesses, that recovery from lossy compaction preserves load-bearing
state in practice, that sub-agents inherit the parent snapshot, and that access works in
non-workstation environments. The pre-publication validation of these paths was a
maintainer-run dry run with simulated compaction. It was not observed native field use.

## Reading order

1. **The operational context for your role.** Read it first and in full. It is that role's
   operating manual, and it tells you which of items 2–8 to read and when.

   1a. **`Human_Sandwich_Layer1_Context.md`** — Layer 1 / COULD. How a fresh Layer 1
       conversation starts, new-project vs existing-project onboarding, the existing-project
       reconstruction/context-pack protocol, working preferences, downstream prompt
       presentation and when to open a work order with the DID starter, escalation and autonomy, custody
       habits, and how to read downstream reports.

   1b. **`Human_Sandwich_DID_Context.md`** — Layer 2 / DID. How a fresh DID session binds the
       foundation and grounds in the project, how it interprets a work order and its authority,
       how it finds the governing methods in its bound snapshot, evidence and custody
       expectations, protected state, stopping and failing closed, session continuation and
       recovery after context loss, and what a report returns.

   Both are general to any project using the Human Sandwich Model, not specific to any one
   project. Neither restates the shared doctrine and methods below; each routes to them.

2. **`The_Human_Sandwich_Model.md`** — authority doctrine.
   The `COULD → SHOULD → DID` model. Answers: *who gets to decide what becomes real?*

3. **`The_Sandwich_Alignment_Skewer.md`** — verification doctrine
   (Verification-Locked Development, VLD).
   Discipline around consequential implementation and execution. Answers: *did what became
   real still mean what was authorised, and does the evidence actually support that claim?*
   VLD may operate inside a consequential `DID`. It is not a fourth Human Sandwich layer.

4. **`Critical_Mass_v0.1.md`** — **Information Buffet** (formerly Critical Mass):
   mechanism-first cross-domain research protocol for
   discovering, evaluating and transferring field-proven methods. It is a distinct
   methodology document, not part of Human Sandwich authority doctrine or VLD verification
   doctrine — it addresses a different question: how to find and validate a method in the
   first place, not who decides or whether evidence supports a claim.

5. **`Nuke_Testing_Experimental_v0.1.md`** — **Chef's Test** (formerly Nuke Testing):
   experimental contract-driven assurance and falsification testing. Starts from governed
   meaning/claims and challenges implementation, verification, and assurance-model weaknesses to challenge whether confidence in a result is actually
   justified. It applies to the authorized project's own implementation, models, evidence
   and test estate. Proportional — not mandatory for every task, and not authority. Marked
   `EXPERIMENTAL`; see "Maintaining this package" below for what that status does and does
   not mean.

6. **`Documentation_Delta_Experimental_Layer1_Rule_v0.1.md`** — experimental Layer 1 field
   rule for durable project knowledge. Checks what durable fact changed, what already owns it,
   and whether any durable record should change at all, and supports human-invoked
   documentation reconnaissance of an existing project. Human authority over documentation
   placement, ownership, retirement and removal is preserved. Marked `EXPERIMENTAL`; see
   "Maintaining this package" below for what that status does and does not mean.

7. **`Model_Routing_and_Effort_Policy.md`** — stable, cross-project model-routing and
   reasoning-effort policy: how to select model capability and effort for an authorized
   downstream task. Its dated, volatile companion, **`Model_Routing_Current_Mappings.md`**,
   records the maintainer's reference choice of named models and effort levels that currently
   implement that policy — not a default for every human using the package — is marked
   `EXPERIMENTAL`, and must be re-checked against live product/account state before use — see
   "Maintaining this package" below.

8. **`VLD_Capability_Substitution_Experimental_v0.1.md`** — experimental field hypothesis that
   verification-locked task transformation can reduce residual model judgment and permit
   lower-cost routing on sufficiently bounded/checkable work. A companion to items 3 and 7, not
   a new methodology in its own right. Marked `EXPERIMENTAL`; see "Maintaining this package"
   below for what that status does and does not mean.

Items 1–7 are general to Human Sandwich Model projects and contain no project-specific or
volatile project state, with the deliberate, dated exception of item 7's current-mappings
companion. Items 5 (Chef's Test), 6 (Documentation Delta), and 8 (VLD Capability Substitution)
are likewise general and fully supplied, but their explicit `EXPERIMENTAL` maturity labels are
not project-specific or volatile details to be stripped out — they are part of those documents'
meaning.

## What is authoritative, and what is not

- **The live repository and its governed state are authoritative for current project
  status.** Phase, evidence, baselines, acceptance records and roadmap position come from
  the repository (`ROADMAP.md`, `AGENTS.md`, `PROJECT.md`, protected baseline records), not
  from this package.
- **The doctrine and methodology documents (items 2–4) provide doctrine and reasoning, not
  volatile roadmap state.** They explain how authority, verification, and method discovery
  are meant to work. They do not tell you where the project currently stands.
- **The role contexts (items 1a, 1b) provide stable, cross-project operating practice**, not
  project state. They intentionally carry no project's current phase, branch/HEAD, subsystem
  status, or model-routing tables. Neither is authority over meaning, scope or acceptance —
  HUMAN SHOULD remains authority — and a work order does not become authoritative by quoting
  either one.
- **This file's "Foundation binding" section owns how every role discovers, binds, continues
  on and recovers its foundation snapshot.** The role contexts apply it to their role and do
  not restate it.
- **`Nuke_Testing_Experimental_v0.1.md` (item 5) is a supplied experimental assurance
  method, not authority.** It is Chef's Test. It gives a technique for challenging whether
  confidence in a result is justified; it does not decide meaning, cannot invent missing
  semantics, and remains `EXPERIMENTAL` — apply it proportionally, not as mandatory ceremony.
- **`Documentation_Delta_Experimental_Layer1_Rule_v0.1.md` (item 6) is a supplied experimental
  field rule, not authority.** It governs when a durable-state question gets asked, not who
  answers it: the human decides documentation placement, ownership, retirement and removal, and
  may decide that no durable documentation should exist. Its reconnaissance mode runs only when
  the human asks for it, is not an always-on scanner, produces `COULD` options rather than
  authorised work, may conclude that no material gap exists, and creates no persistent
  ownership map.
- **`Model_Routing_and_Effort_Policy.md` (item 7) is stable, cross-project policy**, not
  project state or account state. Its companion, `Model_Routing_Current_Mappings.md`, is
  explicitly operational and volatile — it may change independently of the policy itself and
  carries no authority over engineering decisions.
- **The routing policy (item 7) and its mappings companion are supported by a separate
  research/evidence record, maintained outside this package.** It documents provenance —
  inherited methods, local synthesis, residual uncertainty — for the routing revision. It is
  not part of this package, is not required to use this package, and is not itself operational
  authority or doctrine.
- **`VLD_Capability_Substitution_Experimental_v0.1.md` (item 8) is a supplied experimental field
  hypothesis, not authority and not a validated routing law.** It does not claim VLD makes
  weaker models smarter, does not define current model/vendor mappings, and carries no authority
  over meaning, scope, or acceptance — HUMAN SHOULD remains authority. It remains
  `EXPERIMENTAL`, subject to the field-review/sunset conditions stated in the document itself.

## Maintaining this package

Update `Human_Sandwich_Layer1_Context.md` only when a stable, cross-project Layer 1 working
rule changes, and `Human_Sandwich_DID_Context.md` only when a stable, cross-project DID working
rule changes — see each file's own "Update policy" section. Do not add project-specific or
volatile project content to either. A rule that both roles need belongs in its shared owner —
this file for foundation binding, the doctrine or method documents for everything else — not
in two role contexts.

The doctrine documents (`The_Human_Sandwich_Model.md`, `The_Sandwich_Alignment_Skewer.md`)
and `Critical_Mass_v0.1.md` are published/accepted methodology held in governed custody.
"Published/accepted" is their status within this package and its custody. It is not a claim that
they are externally established named methodologies; each document states its own evidence
maturity (Information Buffet, for example, describes itself as a practice-derived protocol). Do
not rewrite them casually. Replace what one of them says only when the publication itself is
substantively superseded, and keep exactly one current copy of each under its canonical
filename.

Migrating a publication's canonical *representation* — the format it is carried in — is not
substantive supersession and does not require one. It is permitted where substantive meaning
is preserved, the predecessor representation stays recoverable in governed history, and
exactly one active canonical representation is left behind. Do not leave parallel
representations of the same publication side by side, and do not accumulate versioned
duplicates such as `..._v4`, `Critical_Mass_v0.2.md`, or `...(4)`.

`Human_Sandwich_Layer1_Context.md` and `Human_Sandwich_DID_Context.md` use stable canonical
filenames without a version suffix, so future revisions replace them in place rather than
forcing every project or reference to change filenames. Each file's own internal `Version:`
metadata tracks its revision.

Some package filenames carry a version suffix, such as `_v0.1`. That suffix is part of the
file's stable path, kept so that references do not break, and is not renamed when the document
is revised. It is not the document's version: the internal `Version:` field is the authoritative
version signal wherever a document has one. Package status (membership, custody) is separate
from a document's evidence maturity; an `EXPERIMENTAL` label changes only on the evidence that
document requires.

From 2026-09-25 onward, a change to a document that has a `Version:` field bumps that field. This
applies to any change to normative behaviour, an execution contract, applicability, authority,
status, load-bearing operational references, or other plausibly behaviour-changing instructions.
The bump is one minor step (0.9 → 0.10 → 0.11; 1.1 → 1.2), once per affected document per public
promotion. Purely typographic or whitespace corrections with no plausible behavioural effect need
not bump. Earlier publications are not renumbered. A document without a `Version:` field, this
file among them, is not given one for symmetry.

`Model_Routing_and_Effort_Policy.md` follows the same convention: a stable canonical filename
without a version suffix, internal `Version:`/`Status:` metadata, and no current model names,
pricing, or account state. Update it only when a stable routing mechanism itself changes.

Current model/effort mappings belong in `Model_Routing_Current_Mappings.md` only, dated and
marked `EXPERIMENTAL`. Update it when the mapping changes; this does not require touching the
stable policy file.

Pricing and product/account availability are never cached in either routing document — they
are re-derived from live sources whenever a decision actually depends on them.

`Nuke_Testing_Experimental_v0.1.md` is an active package member but is explicitly
`EXPERIMENTAL` — unlike the doctrine documents above, it is not published/accepted stable
methodology, and being part of this package does not by itself promote its maturity. Keep
exactly one active Chef's Test document under its canonical filename; predecessor versions
remain available through Git history. Do not describe it as established doctrine, an
industry standard, or a validated/certified methodology. Update or supersede it only through
an explicit, human-authorised revision.

`Documentation_Delta_Experimental_Layer1_Rule_v0.1.md` is an active package member on the same
terms: explicitly `EXPERIMENTAL`, under active field trial, and not promoted by package
membership. Keep exactly one active copy under its canonical filename. Do not describe it as
established doctrine, a documentation methodology, an artifact taxonomy, or a repository
scanner, and do not let it acquire the documentation-placement authority that belongs to the
human. Its own falsification and halt conditions govern the trial; update or supersede it only
through an explicit, human-authorised revision.

`VLD_Capability_Substitution_Experimental_v0.1.md` is an active package member on the same
terms: explicitly `EXPERIMENTAL`, under active field trial, and not promoted by package
membership. Keep exactly one active copy under its canonical filename. Do not describe it as
established doctrine, an industry standard, or a validated model-tier routing law, and do not
let it be read as license to route downward merely because a VLD workflow is present — its own
routing gate, anti-rule, falsifiers, and field-review/sunset conditions govern the trial; update
or supersede it only through an explicit, human-authorised revision.
