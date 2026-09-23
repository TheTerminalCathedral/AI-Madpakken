# Layer 1 cold-start package

This directory holds the cold-start bootstrap package for a user's preferred upstream LLM
acting as **Layer 1 / COULD** in a Human Sandwich (`COULD → SHOULD → DID`) workflow.

Layer 1 either resolves this package from the canonical distribution below, or has it uploaded
or pasted into its context, before discussing work in a Human Sandwich project. A thin starter
that only tells Layer 1 where the distribution is suffices: the startup behaviour is owned here,
by item 1 of the reading order, not by the starter. The upstream LLM helps prepare safe
downstream prompts; it does not execute against a project itself. The human remains the
authority boundary that decides what is authorised. The downstream **DID** role — the
execution layer that works against real project state, validates results, and records
evidence — may be performed by Codex, Claude, another model, a local toolchain, or a human
operator, depending on the task and project.
**DID is a role, not a vendor or model name.**

## Canonical distribution

Both consumers **resolve and read** the package. Layer 1 grounds once at the start of every
conversation (`Human_Sandwich_Layer1_Context.md` §4). An uploaded, pasted or local copy is a
transport of foundation content, not proof of currentness: it stands in for the canonical
foundation only where it is established to match the resolved revision, and is otherwise never
represented as current. Downstream, where project grounding or an invoked doctrine requires a
governing document, DID resolves the current Keeper-maintained distribution once per session
and reads the applicable document directly, rather than working from a summary, a handoff
paraphrase, or an older project-local copy. The resolved revision is the conversation's or
session's foundation snapshot, re-checked only when the human asks
(`Human_Sandwich_Layer1_Context.md` §39).

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

This file remains the owner of package composition and reading order. There is no separate
manifest.

## Reading order

1. **`Human_Sandwich_Layer1_Context.md`** — general cold-start operating context.
   How a fresh Layer 1 thread grounds the foundation and starts, new-project vs
   existing-project onboarding, the existing-project reconstruction/context-pack protocol,
   foundation bootstrap for a fresh downstream session, working preferences,
   downstream prompt presentation, escalation and autonomy, custody habits, and how to read
   downstream reports. This is general to any project using the Human Sandwich Model, not
   specific to any one project. Read this first; it is the operating manual.

2. **`The_Human_Sandwich_Model.md`** — authority doctrine.
   The `COULD → SHOULD → DID` model. Answers: *who gets to decide what becomes real?*

3. **`The_Sandwich_Alignment_Skewer.md`** — verification doctrine
   (Verification-Locked Development, VLD).
   Discipline around consequential implementation and execution. Answers: *did what became
   real still mean what was authorised, and does the evidence actually support that claim?*
   VLD may operate inside a consequential `DID`. It is not a fourth Human Sandwich layer.

4. **`Critical_Mass_v0.1.md`** — mechanism-first cross-domain research protocol for
   discovering, evaluating and transferring field-proven methods. It is a distinct
   methodology document, not part of Human Sandwich authority doctrine or VLD verification
   doctrine — it addresses a different question: how to find and validate a method in the
   first place, not who decides or whether evidence supports a claim.

5. **`Nuke_Testing_Experimental_v0.1.md`** — experimental contract-driven adversarial
   assurance. Starts from governed meaning/claims and attacks implementation, verification,
   and assurance-model weaknesses to challenge whether confidence in a result is actually
   justified. Proportional — not mandatory for every task, and not authority. Marked
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
companion. Items 5 (Nuke Testing), 6 (Documentation Delta), and 8 (VLD Capability Substitution)
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
- **`Human_Sandwich_Layer1_Context.md` (item 1) provides stable, cross-project operating
  practice**, not project state. It intentionally does not carry a downstream project's
  current phase, branch/HEAD, subsystem status, or model-routing tables.
- **`Nuke_Testing_Experimental_v0.1.md` (item 5) is a supplied experimental assurance
  method, not authority.** It gives a technique for adversarially challenging whether
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
rule changes — see its own "Update policy" section. Do not add project-specific or volatile
project content to it.

The doctrine documents (`The_Human_Sandwich_Model.md`, `The_Sandwich_Alignment_Skewer.md`)
and `Critical_Mass_v0.1.md` are published/accepted methodology held in governed custody. Do
not rewrite them casually. Replace what one of them says only when the publication itself is
substantively superseded, and keep exactly one current copy of each under its canonical
filename.

Migrating a publication's canonical *representation* — the format it is carried in — is not
substantive supersession and does not require one. It is permitted where substantive meaning
is preserved, the predecessor representation stays recoverable in governed history, and
exactly one active canonical representation is left behind. Do not leave parallel
representations of the same publication side by side, and do not accumulate versioned
duplicates such as `..._v4`, `Critical_Mass_v0.2.md`, or `...(4)`.

`Human_Sandwich_Layer1_Context.md` itself uses a stable canonical filename without a version
suffix, so future revisions replace it in place rather than forcing every project or reference
to change filenames. The file's own internal `Version:` metadata tracks its revision.

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
exactly one active Nuke Testing document under its canonical filename; predecessor versions
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
