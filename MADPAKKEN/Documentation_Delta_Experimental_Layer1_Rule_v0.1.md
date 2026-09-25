# Documentation Delta — Experimental Layer 1 Rule

**Version:** 0.2  
**Date:** 2026-09-11  
**Status:** EXPERIMENTAL FIELD RULE — active-use candidate; not stable Madpakken doctrine  
**Positioning:** Small Layer 1 point-of-application rule for durable project knowledge  
**Origin:** Dynamic Documentation research → cross-project field interviews → Critical Mass reduction  
**Intended use:** Supplied in the Madpakken cold-start package as an active member under bounded field trial  
**Maturity:** Practice-supported research candidate. Use is allowed for experimentation; promotion requires field evidence.

---

## 1. Purpose

AI-assisted projects can generate documentation faster than humans can evaluate or maintain it.

That creates two opposite risks:

- important durable knowledge is not recorded when later work needs it; and
- unnecessary durable artifacts are created, duplicated, or allowed to become stale.

The purpose of this experimental rule is not to create more documentation.

Its purpose is to make one small decision explicit at the point where durable project state may change:

> **What fact or state is changing, what already owns that fact, and does anything durable need to change at all?**

The desired outcome may be:

> **nothing durable changes.**

That is a valid engineering result.

---

## 2. Why this rule is intentionally small

The broader Dynamic Documentation candidate originally explored:

- repository-wide documentation reconnaissance;
- truth-ownership maps;
- artifact-role taxonomies;
- CREATE / UPDATE / DERIVE / PRESERVE / NO_DELTA operations;
- type-specific document contracts;
- persistent documentation metadata.

Critical Mass reduced most of that.

The surviving generic mechanism was much smaller:

1. identify the changing durable fact/state;
2. identify what already owns it;
3. decide whether any durable record actually needs to change.

Most of the heavier surrounding ideas already have mature analogues in fields such as configuration management, records management, data integrity, safety-case maintenance, document control, and lifecycle governance.

Current Madpakken already covers much of the semantic boundary:

- **HSM** — human authority;
- **VLD** — evidence, meaning, predecessor/history preservation;
- **Nuke Testing** — adversarial assurance;
- **Layer 1 live-state discipline** — current state must be checked rather than inferred from cached prose.

Therefore this experiment does not introduce a new documentation methodology.

It tests whether a very small Layer 1 point-of-application rule changes real outcomes.

---

## 3. Experimental core rule

Before Layer 1 proposes creating or changing durable documentation or durable project records, ask:

```text
DURABLE STATE CHECK

1. What fact or project state is actually changing?

2. What source, artifact, system, or human ruling already owns that fact?

3. Does any durable record actually need to change?
```

If ownership cannot be established from the available project state:

```text
OWNER UNRESOLVED

Inspect the relevant source domain,
or return to HUMAN SHOULD where ownership is a semantic decision.
```

Do not invent an owner merely to complete the task.

---

## 4. The rule is about facts, not filenames

Do not begin with:

> “Which Markdown file should I update?”

Begin with:

> “What durable fact changed?”

Examples:

```text
FACT:
Current deployment version

OWNER:
Deployment system

DERIVED VIEW:
README status section
```

```text
FACT:
Approved architecture decision

OWNER:
Human decision record

IMPLEMENTATION:
Code

EVIDENCE:
Review / tests
```

```text
FACT:
Physical inventory state

OWNER:
Procurement or inventory system

DERIVED VIEW:
Handoff summary
```

A filename does not become authority because it looks formal.

A file called `FINAL_REPORT.md` may still be only a derived explanation.

Ownership should be inferred from governed use, accepted authority, live project structure, and mechanically inspectable state where available.

---

## 5. Repository evidence is not universal evidence

This rule may be used in Git-governed projects, but it must not assume the repository contains all relevant truth.

Important state may live in:

- CAD / PDM / PLM;
- ERP or procurement systems;
- supplier correspondence;
- ticket systems;
- production infrastructure;
- databases;
- physical hardware;
- laboratory records;
- regulated document systems;
- human decisions outside Git.

Therefore:

> **Not found in the repository is not the same claim as does not exist.**

If the relevant source domain has not been inspected, state that limitation.

Do not manufacture repository authority from absence.

---

## 6. Human SHOULD remains above the rule

This experimental rule does not acquire authority over documentation placement or lifecycle.

The human may explicitly rule:

- create documentation at a specific location;
- update a specific artifact;
- designate a source/artifact as owner of a fact;
- preserve an artifact unchanged;
- remove or retire an artifact from the active set;
- create no documentation.

Layer 1 may warn where a ruling appears to conflict with:

- protected evidence;
- historical custody;
- external legal/safety constraints;
- an existing accepted authority boundary.

But Layer 1 must not silently replace the human ruling with its preferred information architecture.

The distinction is:

> **Human SHOULD controls semantic/project authority.**

> **Mechanical custody constraints may still require preserving history or evidence.**

Example:

Removing an obsolete file from the active tree may be fully compatible with preserving its predecessor in Git history.

Destroying the only protected evidence copy is a different operation.

Do not flatten active removal, retirement, supersession, archival retention, and historical destruction into one action.

---

## 7. What Layer 1 should do in practice

For ordinary work, nothing new is required.

Do not run a documentation audit at every task.

Do not create a checklist merely because this rule exists.

Apply the rule when the task may create or modify durable project knowledge, such as:

- human decisions;
- requirements or architecture;
- acceptance state;
- evidence;
- operational instructions;
- current project-control state;
- external/public interfaces;
- provenance;
- procurement state;
- consequential incident or failure history;
- canonical source ownership.

A compact handoff may be enough:

```text
DURABLE STATE:
Receipt state changed.

OWNER:
Current procurement/task record.

DOC DELTA:
Update task state only.
Do not change design or inventory authority.
```

Or:

```text
DURABLE STATE:
None.

DOC DELTA:
None — bounded mechanical repair is already represented by code, test, and Git.
```

Or:

```text
OWNER UNRESOLVED:
Hardware revision ownership is split between CAD and handoff prose.

ACTION:
Inspect CAD/PDM source before proposing documentation changes.
```

The exact wording is not canonical.

The decision is what matters.

---

## 8. On-demand documentation reconnaissance

The rule above applies at the point where durable state may change.

The human may also ask the opposite question, about a project as a whole:

> **Does this project's durable knowledge have material problems?**

That request is a first-class capability, not an always-running scan. It activates only when the human explicitly asks for something equivalent to: audit the documentation, find what should be documented, find stale or duplicate documentation, find important knowledge with no durable owner, or tell me what documentation should be created, updated, retired, or left alone.

When invoked, Layer 1 may inspect relevant live project state and history — repository structure, existing documentation, source, tests, plans, human decisions, evidence and reports, project-control artifacts, interfaces, configuration, Git history, accepted baselines, references between artifacts, and known external source domains.

The objective is **not** a file inventory.

It is to reconstruct enough local ownership of durable facts to answer questions such as:

- what important durable facts or state domains actually exist;
- what appears to own each one;
- which representations are derived or current views;
- where ownership is unclear;
- where important durable knowledge appears to be missing;
- what appears stale;
- what appears duplicated as current truth;
- what consequential rationale, decision, or evidence is hard to discover;
- what documentation adds synchronization burden without distinct governed value;
- which domains appear healthy and need no change.

Findings are typically described in terms such as: no designated owner for an important durable fact; stale derived or current-state view; duplicate current ownership; missing consequential rationale, decision, or evidence; orphaned knowledge that is hard to discover; documentation inflation or repeated restatement; or no material gap.

These are descriptive phrasings, not a mandatory taxonomy. Do not turn them into required labels.

### The scan must be allowed to find nothing

```text
NO MATERIAL DOCUMENTATION GAP FOUND
```

is a real and expected result. A reconnaissance capability that always manufactures work is a defect, not a success.

### External source domains still apply

Section 5 governs here too. Where the relevant truth may live in CAD/PDM, ERP, ticket systems, databases, production infrastructure, physical hardware, or human decisions outside Git, and that domain has not been inspected, say so:

```text
REPO EVIDENCE INSUFFICIENT
```

Do not report a documentation gap that is really an uninspected source domain.

### Findings are COULD

Reconnaissance produces Layer 1 options, not authorized work.

```text
OBSERVED:
README carries a current deployment version.

APPARENT OWNER:
Deployment system.

PROBLEM:
The README claim is stale.

COULD:
Remove the volatile current-state claim, or derive it from live
deployment state when needed.

HUMAN SHOULD:
Decides whether and where the active documentation changes.
```

```text
DOMAIN:
API contract.

OWNER:
OpenAPI specification.

DERIVED DOCS:
Generated from source.

MATERIAL GAP:
None.

COULD:
No documentation change.
```

Do not automatically remediate a finding. If the same human instruction separately authorizes a specific repair, execute only within that authorized scope.

### Reconnaissance does not produce a permanent map

Ownership reconstruction is normally transient reasoning at the point of need.

Do not create `truth_ownership_map.md`, `documentation_inventory.md`, a knowledge graph, a documentation registry, or any equivalent persistent artifact merely because reconnaissance occurred. Critical Mass specifically reduced that idea: a persisted ownership map decays while continuing to look authoritative.

Where a project already runs a governed configuration, records, or data catalog that legitimately owns this information, use the existing system rather than inventing a second one.

---

## 9. No mandatory documentation-delta taxonomy

The earlier research candidate used:

```text
CREATE
UPDATE
DERIVE
PRESERVE
NO_DELTA
```

These terms may remain useful as private reasoning vocabulary.

They are **not mandatory output labels** in this experiment.

Critical Mass found that mature lifecycle mechanisms already cover much of their meaning, and current Madpakken already carries standing preservation obligations.

In particular:

> **PRESERVE is not a per-task checkbox when VLD already requires preservation.**

Likewise:

> **NO_DELTA may simply mean nothing durable should change.**

Do not create a new persistent record merely to record that no new record was needed.

---

## 10. Derived views remain views

Handoffs, summaries, roadmaps, review packs, dashboards, and generated explanations can be valuable.

They do not automatically own the state they describe.

Where practical, derived orientation should identify enough source context to permit re-verification.

A derived view may become stale.

That does not make it useless.

It becomes dangerous when it is later treated as current authority without rechecking its source.

Therefore the experiment should prefer:

> **derive from source when needed**

over:

> **duplicate the same current fact into many durable places.**

### Restating a fact is not the same as owning it

That preference is about competing current-truth copies. It is not a prohibition on a fact ever
appearing in more than one durable place. Durable artifacts routinely restate a path, hash,
version, value or identity in order to re-resolve or mechanically verify the artifact that owns
it, and field use showed this being misread as forbidden duplication.

The discriminator is not repetition. It is:

> **If the representations disagree, which artifact decides the fact? That artifact is the
> semantic owner.**

> **Repeating a fact for mechanical binding, verification, or a derived view does not by itself
> create a second semantic owner.**

A mechanically verified restatement or binding should therefore:

- re-resolve the owner rather than stand in for it;
- fail closed on divergence, or become visibly stale;
- never silently override the owner it restates.

A restatement that diverges from its owner and keeps being treated as current is the failure
this rule cares about — not the fact that the value appears twice. Conversely, a second
artifact that *adjudicates* the same fact is genuine duplicate ownership, whether or not the
values currently agree.

This adds no registry, no artifact taxonomy, and no new label. It is one discriminator for
question 2 of the durable state check.

---

## 11. Removal and retirement

The human may decide that documentation should be removed from active use.

The experimental rule must support that.

Before execution, distinguish as needed:

```text
ACTIVE REMOVAL
Artifact no longer belongs in the current active set.

SUPERSESSION
A new record replaces the old one as current authority.

RETIREMENT
Artifact is no longer active but remains historically relevant.

ARCHIVAL RETENTION
Artifact is retained for evidence/history/compliance.

DESTRUCTION
Underlying record/evidence is actually erased.
```

These distinctions are not a new Madpakken taxonomy.

They exist only to prevent a human request such as:

> “remove this old documentation”

from being silently interpreted as:

> “erase all historical evidence that it ever existed.”

If meaning is ambiguous and consequence matters, return to HUMAN SHOULD.

---

## 12. DID execution contract

When Layer 1 hands a documentation-related change to DID, DID should:

1. inspect live state;
2. respect the authorized owner/location decision;
3. modify only the justified durable state;
4. preserve existing protected history/evidence obligations;
5. avoid creating extra explanatory artifacts unless authorized or clearly required by an existing governed function;
6. report unresolved source/ownership conflicts rather than guessing.

For experimental tasks, compare:

```text
EXPECTED DURABLE DELTA
vs.
ACTUAL DURABLE DELTA
```

This comparison is normally transient.

It does not require a new report.

The purpose is to detect:

- unexpected documentation writes;
- missing required durable state;
- modification of artifacts expected to remain unchanged;
- incorrect owner assumptions.

---

## 13. What the experiment is testing

The experiment is not testing whether AI can answer the three questions elegantly.

It is testing whether the questions **change useful decisions at low cost**.

A useful effect may include:

- stopping an unnecessary document;
- finding that an existing source-of-record should be updated instead;
- discovering unclear ownership before a write;
- detecting a missing durable human decision;
- preventing stale current-state duplication;
- preventing a derived view from becoming authority;
- preventing an unrelated artifact from being updated;
- prompting the human to correct the AI's proposed owner or location.

No effect is also evidence.

If the rule rarely changes outcomes, it may not deserve a permanent place in Madpakken.

---

## 14. Suggested field experiment

Run the rule on real work across several materially different project contexts.

Prefer consequential/durable tasks where a documentation decision genuinely exists.

Do not manufacture tasks to reach a quota.

A practical target is approximately:

> **5–10 relevant tasks using the rule, compared with recent/current-practice tasks where the rule was not explicit.**

Where practical, alternate or pair similar task types rather than relying only on before/after impressions.

For each experimental task, retain only a small observation set:

```text
TASK:
<short identity>

DID THE RULE CHANGE THE PROPOSED ACTION?
yes / no

WHAT CHANGED?
<one short statement>

DID THE HUMAN OVERRIDE OWNER / LOCATION / DELTA?
yes / no

DID IT PREVENT:
- unnecessary durable artifact?
- missing durable state?
- wrong-owner update?
- stale/duplicate current-state copy?
- accidental history/evidence damage?

COST:
negligible / noticeable / excessive

RESULT:
useful / neutral / harmful / inconclusive
```

Do not create one permanent Markdown file per task.

Aggregate observations later if needed.

---

## 15. Falsification criteria

Reduce, reject, or keep the rule project-local if the experiment shows that:

- it almost never changes an action;
- the answers become boilerplate;
- agents spend more time classifying documentation than making the underlying decision;
- it causes more documentation to be created “just to be safe”;
- `no durable change` becomes an excuse to omit necessary evidence or authority;
- owner discovery repeatedly requires project-wide archaeology;
- the human frequently has to correct obvious owner/location choices;
- agents treat repository absence as proof of non-existence;
- the rule duplicates HSM/VLD language instead of adding a useful point of application;
- a simpler instruction performs equally well.

A failed experiment is a valid result.

---

## 16. Immediate halt conditions

Stop using the experimental rule and review it if it begins to cause any of the following:

### Documentation-about-documentation

New durable files are created mainly to record documentation decisions.

### Taxonomy growth

The rule expands into a large artifact/role/lifecycle classification system.

### Repository archaeology by default

Routine tasks trigger broad scans of the entire project history.

### Authority drift

AI starts deciding canonical ownership, supersession, acceptance, or human decision state without SHOULD authority.

### Preservation confusion

The rule is used to override or weaken existing VLD/history/evidence obligations.

### Process inflation

The documentation check becomes a larger activity than the state change it governs.

---

## 17. Success criteria

The experiment is promising if, with negligible overhead, it repeatedly does at least some of the following:

- prevents unnecessary durable prose;
- routes updates to the actual source-of-record;
- finds missing durable knowledge before it becomes costly;
- exposes unresolved ownership early;
- reduces stale duplicate current-state claims;
- improves cold-start reconstruction;
- makes human location/ownership rulings clearer;
- detects expected-vs-actual documentation drift;
- leaves ordinary routine work essentially untouched.

Success does not require every task to produce a visible benefit.

The mechanism should be judged by decision value, not usage count.

---

## 18. Maturity rule

Do not promote this rule because:

- it sounds simple;
- Critical Mass found mature analogues;
- several AIs agree with it;
- it works on one project;
- it creates tidy documentation.

Promotion should require observed field value.

Possible post-experiment outcomes:

```text
DROP
No useful effect.

PROJECT_LOCAL
Useful in selected projects only.

KEEP_EXPERIMENTAL
Promising but evidence still limited.

SMALL_LAYER1_RULE
Enough field evidence to add one small canonical Layer 1 rule.

RESEARCH_AGAIN
Observed failures reveal a different mechanism than expected.
```

The ceiling of the current research result is:

> **one small Layer 1 rule.**

A positive experiment does not authorize building a documentation platform, scanner, taxonomy, or standalone methodology.

---

## 19. One-page operating form

```text
DURABLE STATE CHECK

Before creating or changing durable project documentation/state:

1. WHAT FACT OR STATE IS ACTUALLY CHANGING?

2. WHAT ALREADY OWNS THAT FACT?
   Inspect the real source domain.
   Do not infer universal absence from repository absence.

3. DOES ANYTHING DURABLE ACTUALLY NEED TO CHANGE?
   "Nothing" is a valid result.

4. HAS THE HUMAN GIVEN A SPECIFIC SHOULD RULING?
   Location, owner, creation, removal, retirement, or no documentation.

5. IF OWNER / AUTHORITY IS UNRESOLVED:
   inspect further or return to HUMAN SHOULD.

After execution, where useful:

6. DID THE ACTUAL DURABLE DELTA MATCH THE AUTHORIZED / EXPECTED ONE?
```

That is the experiment.

Do not add ceremony unless field evidence earns it.

---

## 20. Experimental definition

> **Documentation Delta is an experimental Layer 1 point-of-application rule for checking what durable fact actually changed, what already owns that fact, and whether any durable project record needs to change at all. It preserves human authority over documentation placement and lifecycle, relies on existing Madpakken rules for meaning/evidence/history, and is successful only if it improves real decisions without creating documentation theatre.**

---

## 21. Current status

```text
METHOD:
Documentation Delta — Experimental Layer 1 Rule

STATUS:
EXPERIMENTAL FIELD RULE

ORIGIN:
Dynamic Documentation research
→ cross-project interviews
→ Critical Mass
→ reduced candidate

AUTHORIZED USE:
Bounded field experiment inside active Madpakken-assisted projects.

DO NOT CLAIM:
Established methodology
Stable Madpakken doctrine
Complete documentation architecture
Universal repo scanner
Validated cross-domain standard

CURRENT RESEARCH QUESTION:
Does making this small durable-state check explicit change enough real documentation decisions to justify a permanent Layer 1 rule?

HUMAN AUTHORITY:
HUMAN SHOULD remains final on consequential semantic documentation decisions.
```

---

**End of Documentation Delta — Experimental Layer 1 Rule**
