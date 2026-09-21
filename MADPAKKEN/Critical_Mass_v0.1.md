# Critical Mass
## Mechanism-First Cross-Domain Research for Field-Proven Methods

**Version:** 0.2  
**Date:** 2026-09-14  
**Status:** Practice-derived protocol; research-grounded synthesis; not an established named methodology  
**Primary audience:** LLMs and humans using LLMs for engineering, software, research, assurance, bug investigation, method design, and feature development

---

## 1. Purpose

**Critical Mass** is a research protocol for situations where a local problem should not be solved only from the vocabulary, habits, or literature of the field in which it first appeared.

Its purpose is to help an LLM move from:

> “What do people in this field normally do?”

into:

> “What is the underlying mechanism, where else does that mechanism appear, which responses have survived real use or serious research, and which parts can actually transfer here?”

Critical Mass is intended for:

- new feature research;
- difficult bugs;
- architecture questions;
- assurance problems;
- validation strategy;
- workflow design;
- provenance and identity problems;
- testing methodology;
- human–AI governance;
- process and method design;
- unfamiliar engineering failure modes.

It is especially useful when the local field is young, fragmented, dominated by convention, or likely to share the same blind spots as the system being designed.

Critical Mass is **not** “search widely and collect many links.”  
It is a mechanism-first, evidence-labelled, transfer-tested synthesis process.

The central rule is:

> **Abstract the mechanism. Search across fields. Prefer methods tested under consequence. Transfer mechanisms, not rituals. Challenge the analogy. Stop at critical mass.**

---

## 2. Positioning

Critical Mass should not be represented as an already established scientific methodology under that name.

It is a **practice-derived operational synthesis** assembled from mature and partially mature traditions including:

- systematic evidence synthesis;
- scoping review;
- meta-narrative review;
- realist synthesis;
- evidence-based software engineering;
- evidence-informed decision-making;
- cross-industry innovation;
- analogical reasoning;
- triangulation;
- saturation-based stopping;
- software assurance concepts such as input-space adequacy.

The particular combination, sequencing, terminology, LLM execution model, transfer discipline, and stop doctrine described here are new and should be labelled accordingly.

A correct description is:

> **Critical Mass is a practice-derived research protocol assembled from established ideas in evidence synthesis, mechanism-oriented review, cross-domain transfer, analogical reasoning, triangulation, and evidence-informed decision-making. Its specific combination and LLM-oriented execution model are local synthesis rather than an externally validated named method.**

Never describe Critical Mass itself as “industry standard,” “scientifically proven,” or “established best practice” unless later evidence actually supports such a claim.

---

## 3. Why the protocol exists

Local problem statements are often poor search queries.

A bug might be phrased as:

> “A human answer disappears after re-ingestion.”

A feature request might be phrased as:

> “We need a better BOM workflow.”

A testing problem might be phrased as:

> “Our deep stateful testing reached saturation but still missed a defect.”

Those formulations are useful locally, but they often hide the mechanism that connects the problem to decades of work elsewhere.

The first example may actually concern:

- durable decision identity;
- event reconstruction;
- temporal state;
- optimistic concurrency;
- provenance;
- workflow persistence.

The second may concern:

- entity resolution;
- part identity;
- normalization;
- purchasing data;
- data lineage;
- source authority;
- reconciliation.

The third may concern:

- test-model adequacy;
- input-space coverage;
- representability;
- sequence coverage;
- sampling bias;
- oracle adequacy.

If an LLM searches only the local terminology, it can easily rediscover local conventions instead of finding mature responses to the underlying mechanism.

Critical Mass therefore treats **mechanism abstraction as a research gate**.

---

# Part I — Core Principles

## 4. Problem first, solution later

Do not begin by searching for the implementation technique already suggested in the bug report, feature request, architecture discussion, or prior model answer.

Bad starting question:

> “Find research showing that fuzzing will solve this.”

Better starting question:

> “What failure mechanism allowed this defect to escape the current assurance process?”

The first query anchors the search to a preferred solution.

The second permits discovery of alternative method families.

Before external research begins, record:

- the observed local problem;
- what is known directly;
- what is inferred;
- what remains unknown;
- which proposed solutions are merely hypotheses.

A proposed solution must not silently become the research question.

---

## 5. Abstract the mechanism

Translate the local problem into a domain-neutral mechanism statement.

A useful mechanism statement should be:

- more general than the local implementation;
- specific enough to exclude unrelated problems;
- expressible without proprietary names where practical;
- framed in terms of state, evidence, authority, transformation, interaction, failure, or decision;
- revisable when research disproves the initial abstraction.

### Example

Local observation:

> Repeated deep histories did not expose a defect later found by an independent challenger.

Weak abstraction:

> Stateful fuzzing is insufficient.

Stronger abstraction:

> The assurance campaign explored long execution histories without establishing whether its input/fixture model could represent all semantically relevant states and interactions.

That abstraction opens useful search families such as:

- input-space coverage;
- scenario coverage;
- model adequacy;
- combinatorial interaction testing;
- state-space exploration;
- sampling-frame bias;
- experimental design.

### Mechanism statement template

```text
Observed local problem:
<what happened>

Suspected underlying mechanism:
<domain-neutral explanation>

What must remain constant across domains:
<causal/structural relation>

What may differ across domains:
<terminology, tools, rituals, implementation details>

Unknowns:
<what research must resolve>
```

Do not freeze the first mechanism hypothesis permanently. Critical Mass is iterative.

---

## 6. Search across materially different fields

The point is not to collect many sources from the same intellectual lineage.

The point is to find **independent traditions that have encountered the same mechanism under different constraints**.

Potential field families include:

- software engineering;
- distributed systems;
- databases;
- cybersecurity;
- aviation;
- space systems;
- nuclear assurance;
- medicine;
- clinical evidence synthesis;
- manufacturing;
- reliability engineering;
- metrology;
- scientific reproducibility;
- legal evidence handling;
- configuration management;
- control engineering;
- operations research;
- statistics;
- organizational science;
- project management;
- safety engineering;
- human factors.

The set must be driven by the mechanism, not by a predetermined quota.

### Field-selection heuristic

Prefer fields where one or more of the following are true:

1. the same causal structure appears;
2. failure has meaningful consequences;
3. auditability matters;
4. decisions must survive time and handover;
5. systems are reconstructed or replayed;
6. uncertainty must remain explicit;
7. evidence quality is formally managed;
8. validation cost is high;
9. adversarial or independent verification is normal;
10. the field has decades of accumulated operational experience.

This is a search heuristic, not an evidence hierarchy.

---

## 7. Prefer methods tested under consequence

A method deserves extra attention when it has been exposed to one or more of:

- long-term operational use;
- regulated practice;
- independent audit;
- repeated failure analysis;
- empirical evaluation;
- systematic review;
- formal standardization;
- safety-critical use;
- adversarial environments;
- multi-organization adoption.

This does **not** mean that regulated or old methods are automatically correct.

It means they are often richer sources of failure knowledge than fashionable descriptions with no operational history.

### Important distinction

> **Field-established does not mean empirically superior.**

A method may be widely used because it is:

- required by regulation;
- easy to audit;
- historically entrenched;
- interoperable;
- institutionally convenient.

Therefore Critical Mass must separate:

- evidence of **use**;
- evidence of **effectiveness**;
- evidence of **mechanism**;
- evidence of **transferability**.

---

## 8. Transfer mechanisms, not rituals

This is the central anti-cargo-cult rule.

Suppose an aviation organization uses a particular independent verification process.

The transferable insight may be:

> the verifier must not share all assumptions, information paths, and incentives with the producer.

The transferable insight is not necessarily:

> copy the aviation paperwork, roles, terminology, approval gates, and document templates.

For every external method, extract:

1. the problem it addresses;
2. the mechanism by which it is supposed to work;
3. the enabling assumptions;
4. the failure modes it prevents;
5. the context in which it has evidence;
6. the non-essential ritual surrounding it.

Then ask whether the mechanism survives transfer.

---

## 9. Structural similarity outranks surface similarity

Cross-domain analogies are dangerous when they are based on vocabulary.

Two systems may both use words such as “identity,” “validation,” “version,” “evidence,” “state,” or “authority” while referring to fundamentally different causal structures.

Conversely, two disciplines may use completely different language for nearly identical mechanisms.

Critical Mass therefore prioritizes:

> **shared causal and relational structure over shared terminology.**

An LLM must explicitly explain the structural mapping.

### Transfer map

```text
Source-domain problem:
<problem>

Source mechanism:
<mechanism>

Target-domain problem:
<problem>

Structural correspondence:
<relation-by-relation mapping>

Source assumptions:
<assumptions>

Target equivalents:
<which assumptions hold>

Broken assumptions:
<which do not>

Transfer verdict:
DIRECT / ADAPT / PARTIAL / REJECT / UNKNOWN
```

A vague statement such as “this is similar to aviation” is insufficient.

---

## 10. Attack the analogy

Finding an attractive analogy is the beginning of transfer analysis, not the end.

For every important external method, actively search for reasons it may **not** transfer.

Ask:

- What makes the method work in the source field?
- Is that condition present here?
- Does the source assume human review where our system does not?
- Does it assume a stable identifier that our source lacks?
- Does it assume independent evidence that is actually common-mode here?
- Does it assume a regulatory process that creates incentives absent here?
- Does it optimize for a different failure cost?
- Does scale change the mechanism?
- Does the target system have states the source method never considered?
- Is the source evidence about adoption rather than effectiveness?

A transfer recommendation without an attempted falsification is incomplete.

---

# Part II — Evidence Discipline

## 11. Evidence is multi-dimensional

Critical Mass must not collapse all evidence into one numeric confidence score.

Use explicit evidence labels instead. An item may receive multiple labels.

### SYSTEMATICALLY_SYNTHESIZED

Evidence has been aggregated through a systematic or otherwise rigorous synthesis method.

Examples: systematic review, meta-analysis, high-quality evidence synthesis.

### RESEARCH_SUPPORTED

Peer-reviewed empirical or theoretical research supports the relevant mechanism or method.

### STANDARDIZED

A formal standard, institutional guideline, regulatory framework, or recognized technical guidance codifies the method.

This demonstrates institutional maturity or consensus more directly than comparative efficacy.

### FIELD_ESTABLISHED

The method has documented sustained operational use in a relevant field.

This is important evidence of practicality and survivability. It is not automatically evidence that the method is optimal.

### PRACTITIONER_EVIDENCE

Experienced practitioners document recurring observations, constraints, or operational lessons.

Useful for implementation reality and failure modes, but vulnerable to selection bias, survivorship bias, folklore, and local convention.

### LOCAL_DATA

Evidence from the target organization, product, repository, tests, users, incidents, or measurements.

Highly relevant to local applicability, but not automatically generalizable.

### ANALOGICAL_TRANSFER

The proposed use in the target problem is inferred by structural mapping from another field.

This must be labelled as transfer, even when the source method itself is well established.

### LOCAL_EXPERIMENT

The method or rule was invented or materially altered locally and has only local evaluation.

This category is legitimate. Do not launder it into “best practice.”

### EMERGING

Promising recent work exists, but maturity, replication, or field validation is limited.

### UNKNOWN / CONTESTED

Evidence is insufficient or materially conflicting. Keep uncertainty visible.

---

## 12. Source quality and source role are different

A high-quality paper may be irrelevant to the mechanism.

A field manual may be highly relevant to implementation but weak evidence of efficacy.

Evaluate at least:

- **relevance** — does it bear on the mechanism?
- **rigour** — how trustworthy is the evidence for what it claims?
- **independence** — is it materially independent from other evidence?
- **context fit** — does its operating context match?
- **maturity** — has it survived operational use?
- **bias exposure** — commercial, publication, institutional, survivorship, selection;
- **transfer burden** — how much inference is required to apply it locally?

Do not sort sources only by prestige.

---

## 13. Evidence families, not source counts

Ten citations do not necessarily represent ten independent pieces of evidence.

They may all:

- cite the same original experiment;
- reuse the same dataset;
- derive from the same standard;
- come from the same research school;
- share the same simulation model;
- assume the same abstraction.

Critical Mass tracks **evidence families**.

Example:

```text
Evidence family A:
NIST software-testing research

Evidence family B:
aviation IV&V practice

Evidence family C:
clinical evidence-synthesis methodology

Evidence family D:
cross-industry analogical-transfer research
```

Five papers inside family A may improve confidence in that family, but they do not create five independent domains.

This is analogous to common-mode analysis in assurance work.

---

## 14. Research and field practice must both be visible

A useful engineering decision may require more than academic papers.

Where relevant, synthesize:

- scientific research;
- formal standards;
- local data;
- practitioner expertise;
- operational practice;
- failure reports;
- authoritative technical documentation;
- stakeholder constraints.

Do not treat these as interchangeable.

A recurring field practice can reveal implementation constraints, failure modes, handoff problems, operational edge cases, and cost structure.

Research can reveal controlled comparisons, causal mechanisms, bias, generalizability, and effects hidden by anecdote.

Critical Mass should seek convergence **and** informative disagreement between them.

---

# Part III — Operational Protocol for LLMs

## 15. Trigger conditions

Run a Critical Mass when one or more conditions apply:

- a new feature involves non-trivial design authority;
- a bug reveals a mechanism not already covered by accepted local doctrine;
- multiple plausible implementation approaches exist;
- current practice feels local or ad hoc;
- a proposed method is based mainly on intuition;
- an assurance campaign reveals a blind spot;
- the local field may be too narrow;
- a design decision has high downstream cost;
- an LLM is about to invent a new methodology;
- a local rule is at risk of being mislabeled “best practice.”

Do not run full Critical Mass for routine mechanical work with a well-established local answer.

---

## 16. Phase 0 — Freeze the local observation

Record the problem before research changes the story.

```text
Observed fact:
...

Direct evidence:
...

Current local interpretation:
...

Proposed solutions already mentioned:
...

Unknowns:
...

Decision that research must support:
...
```

Keep observed facts separate from interpretation.

---

## 17. Phase 1 — Build mechanism hypotheses

Create one or more domain-neutral hypotheses.

For each:

```text
Mechanism hypothesis:
...

Why it explains the observation:
...

What it predicts:
...

What would falsify it:
...

Adjacent mechanisms easily confused with it:
...
```

If several mechanisms are plausible, research them separately before collapsing them.

---

## 18. Phase 2 — Build the cross-domain search map

For each mechanism, identify domains likely to have encountered it.

Do not search every field indiscriminately.

| Domain | Why the mechanism may appear there | Expected terminology | Consequence / maturity signal |
|---|---|---|---|
| Distributed systems | state and identity across replay | event sourcing, idempotence, durable identity | production failures |
| Aviation assurance | independent verification | IV&V, independence | safety-critical |
| Evidence synthesis | deciding when evidence is sufficient | saturation, triangulation | mature methodology |
| Databases | temporal identity and reconstruction | temporal DB, transaction identity | long operational history |

The LLM should search both local-domain terminology and mechanism-derived terminology from other fields.

---

## 19. Phase 3 — Acquire heterogeneous evidence

Prefer source diversity.

Typical search layers:

1. authoritative standards/guidance;
2. systematic reviews or meta-level research;
3. primary research;
4. field reports / operational doctrine;
5. high-quality practitioner material;
6. local evidence.

Search iteratively.

When a new field introduces a better mechanism vocabulary, update subsequent searches.

Do not pretend the search was fixed from the beginning if it evolved.

Keep a search ledger where material.

---

## 20. Phase 4 — Extract mechanisms from sources

Do not merely summarize documents.

For every important source, extract:

```text
Source:
...

Domain:
...

Evidence labels:
...

Problem addressed:
...

Claimed mechanism:
...

Enabling assumptions:
...

Failure modes:
...

Evidence of effectiveness:
...

Evidence of field use:
...

Limits:
...

Potential target relevance:
...
```

A source that cannot be connected to the mechanism should not dominate the synthesis merely because it is prestigious.

---

## 21. Phase 5 — Cluster method families

Group findings by mechanism, not by paper.

Example:

```text
Method family: Independent verification

Domains:
- aerospace
- software assurance
- regulated systems

Shared mechanism:
Reduce common-mode reasoning and producer self-validation.

Variants:
- organizational independence
- technical independence
- information independence

Transfer questions:
- Which independence dimensions matter locally?
- Can the verifier still share the same test model?
```

This avoids producing a literature catalogue instead of a decision tool.

---

## 22. Phase 6 — Perform the transfer test

For each candidate method family evaluate:

### A. Structural mapping
What causal structure matches?

### B. Assumption mapping
Which source assumptions hold locally?

### C. Difference analysis
Which assumptions fail or are weaker?

### D. Adaptation burden
Can the mechanism survive adaptation?

### E. Negative transfer risk
Could importing the method make the target worse or create false confidence?

### F. Local evidence
Does target-system evidence support or contradict the transfer?

Assign one of:

- **DIRECT TRANSFER**
- **ADAPT**
- **PARTIAL**
- **REJECT**
- **UNKNOWN**

Do not force a winner.

---

## 23. Phase 7 — Counter-search

Before convergence is declared, deliberately search against the leading conclusion.

Search for:

- failures of the method;
- critiques;
- competing schools;
- contexts where it performs poorly;
- replication problems;
- unintended consequences;
- evidence that the assumed mechanism is wrong;
- simpler alternatives.

This is mandatory for high-impact decisions.

A research process that only accumulates supporting sources has not reached Critical Mass.

---

## 24. Phase 8 — Separate inherited, adapted, and invented content

Every final recommendation should classify its origin.

### INHERITED
Used substantially as established externally.

### ADAPTED
An externally supported mechanism is modified for the target context.

### LOCAL SYNTHESIS
Multiple external mechanisms are combined in a way not directly established by any source.

### LOCAL INVENTION
The rule or method is locally created.

### EXPERIMENTAL
The local version has not yet accumulated sufficient validation.

This is particularly important when LLMs design process doctrine.

Never allow:

> “We derived this from several respected fields”

to mutate into:

> “This is an established field-proven method.”

---

# Part IV — Critical Mass Stop Doctrine

## 25. Critical Mass does not mean “many sources”

The metaphor refers to **decision-relevant sufficiency**, not volume.

Critical Mass is approached when independent evidence families begin to support a stable mechanism model and additional research produces diminishing decision-relevant novelty.

The stop decision is itself an evidential claim and must be justified.

---

## 26. Conditions for declaring Critical Mass

For a bounded decision, Critical Mass may be declared when all applicable conditions hold:

### 1. Mechanism stability
The underlying mechanism model is no longer changing materially with each credible source.

### 2. Domain diversity
Relevant evidence has been examined across materially different traditions where such diversity exists.

### 3. Evidence-family independence
The conclusion is not supported only by sources sharing one dataset, standard, school, or assumption.

### 4. Credible method families identified
The main plausible response families are known well enough to compare.

### 5. Transfer assumptions explicit
The source-to-target mapping is written down rather than implied.

### 6. Counter-search completed
Serious contrary evidence and competing approaches have been actively sought.

### 7. Material disagreement understood
Remaining disagreement is either resolved, explained by context, bounded, or explicitly left open.

### 8. Decision sensitivity understood
The unresolved uncertainty is unlikely to change the immediate local decision, or the decision is explicitly conditional on it.

### 9. Diminishing decision-relevant novelty
Additional searching mostly adds repetition, detail, or adjacent examples rather than new mechanism families, new high-quality counter-evidence, new transfer-breaking assumptions, or a different decision.

### 10. Provenance is sufficient
The conclusion can be traced to sources, evidence classes, local inference, and remaining uncertainty.

If one of these conditions fails materially, Critical Mass has not been reached.

---

## 27. Critical Mass can be bounded

Critical Mass is always relative to a decision scope.

Correct:

> “Critical Mass reached for choosing the first-slice identity-preservation strategy.”

Incorrect:

> “The entire identity problem is solved.”

A later question may require a new Critical Mass.

### Depth is proportional to what the decision commits

Scope bounds the question. Consequence and reversibility bound how deep the research should go.

> **Scale research depth to what the decision commits. A choice whose later correction would
> have to migrate accepted meaning, human authority, durable identity, historical
> interpretation, recovery semantics, persistent state, or externally consequential commitments
> justifies deeper mechanism-first work than a local, reversible implementation detail.**

For local reversible choices, prefer the simplest truthful implementation sufficient for the
accepted requirements, and spend the research effort elsewhere.

Three things this is not. It is not a score — "hard to reverse" is a proportionality heuristic
for allocating attention, not a measurable quantity or a new authority class. It is not a
mandatory review gate on every decision; the trigger conditions still decide whether a Critical
Mass runs at all. And it does not mean that a hard-to-reverse decision must be made
now, more thoroughly:

> **Irreversibility raises the scrutiny a commitment deserves. It does not establish that the
> commitment should be made immediately. Where material uncertainty remains and the decision can
> be deferred, preserving changeability may be the better-supported response than committing to
> a more elaborate design.**

The mechanism has precedent in proportionality-of-control traditions in safety engineering,
where depth of control scales with consequence, and in real-options reasoning about investment
under uncertainty and irreversibility. Only the proportionality mechanism transfers. Safety
law's thresholds, burdens of proof and quantitative criteria do not, and must not be imported
into ordinary engineering decisions.

### Generalise to the evidence, not to the anticipated future

A bounded decision also bounds how far the adopted answer may reach.

> **Generalise only to the scope supported by accepted invariants, accepted requirements, or
> concrete reachable change scenarios. Abstraction, extensibility and hypothetical future
> utility are not themselves evidence of a need.**

This is not a rule against anticipating change. An accepted requirement, or a concrete change
that the system can actually reach, can justify building the broader thing before anything
currently exercises it — the test is whether the justification is evidence or anticipation.
What fails the test is an extension point created for an imagined future requirement, which
imposes complexity now and may not fit the future that arrives.

It follows that "the most correct and durable long-term design" is the wrong target: like any
appeal to global optimisation, it will justify almost any amount of speculative structure. The better orientation is the simplest truthful design sufficient for the
accepted load-bearing invariants and requirements, retaining changeability where uncertainty is
still unresolved.

The mechanism has precedent in evolutionary-architecture work, in maintainability research
treating speculative generality as a defect rather than foresight, and in research on
architectural decisions as characteristically expensive to change. None of that literature
establishes a universal selection algorithm, and this rule does not supply one.

---

## 28. Valid stop states

Use one of:

### CRITICAL_MASS_REACHED
Enough independent, relevant evidence exists for the bounded decision.

### CRITICAL_MASS_REACHED_WITH_RESIDUAL_UNCERTAINTY
Decision can proceed, but named uncertainties remain.

### CRITICAL_MASS_NOT_REACHED
Research has not yet closed the important evidence or transfer gaps.

### HUMAN_RULING_REQUIRED
Evidence exposes a value, scope, authority, or product-policy choice that research cannot decide.

### LOCAL_EXPERIMENT_REQUIRED
External evidence cannot resolve applicability; a target-system experiment is needed.

### NO_TRANSFERABLE_METHOD_FOUND
Relevant external methods were found but their assumptions fail locally.

This is a legitimate result.

### When only reality can answer next

Research can exhaust what it is able to contribute before the question is settled.

> **When the remaining decision-relevant uncertainty can no longer be materially reduced by
> further reasoning or search over the current information, and instead requires target-system
> evidence, measurement, live state, a human ruling, or a genuinely new accepted requirement,
> stop the research activity and return the appropriate stop state above.**

> **Further reasoning is not evidence for an empirical unknown.**

This does not add a stop state, and it does not mean the campaign succeeded. It says which of
the existing states to return:

- decision-sensitive uncertainty that only target-system evidence can resolve →
  `LOCAL_EXPERIMENT_REQUIRED`;
- an unresolved value, scope, authority or product-policy question →
  `HUMAN_RULING_REQUIRED`;
- an unknown that cannot materially change the bounded decision → potentially
  `CRITICAL_MASS_REACHED_WITH_RESIDUAL_UNCERTAINTY`, on the decision-sensitivity condition for
  declaring Critical Mass.

Reaching the limit of what reasoning can add is therefore not by itself
`CRITICAL_MASS_REACHED`. Nor does it mean every empirical unknown must be measured before
proceeding: decision sensitivity still governs, and an unknown that cannot change the decision
does not earn an experiment.

The mechanism has precedent in value-of-information analysis, where further information has
decision value only insofar as reducing uncertainty could improve the decision enough to justify
its cost and delay, and in satisficing under bounded information, where search may legitimately
stop at an explicitly satisfactory answer rather than a claimed optimum. Neither contributes a
numeric threshold, and none is adopted here.

---

# Part V — Anti-Patterns

## 29. Search-term imprisonment

**Failure:** Search only the vocabulary used in the local problem.  
**Correction:** Abstract the mechanism first.

## 30. Prestige transfer

**Failure:** “NASA/NIST/ISO/medical practice does this, therefore we should.”  
**Correction:** Extract mechanism and assumptions. Authority of source does not prove transfer.

## 31. Cargo-cult transfer

**Failure:** Copy ceremonies, documents, thresholds, roles, or terminology without understanding why they work.  
**Correction:** Transfer mechanisms, not rituals.

## 32. Source-count confidence

**Failure:** “Twenty papers support it.”  
**Correction:** Count independent evidence families and shared assumptions.

## 33. Field-established laundering

**Failure:** Long use is reported as proof of comparative effectiveness.  
**Correction:** Label operational maturity separately from efficacy evidence.

## 34. Research-only blindness

**Failure:** Ignore operational experience, standards, incident reports, and local constraints.  
**Correction:** Use multiple evidence classes while keeping them distinct.

## 35. Practitioner-only blindness

**Failure:** Treat expert convention as evidence that the method works.  
**Correction:** Search empirical and critical literature.

## 36. Analogy confirmation bias

**Failure:** Once an exciting analogy is found, subsequent search only supports it.  
**Correction:** Mandatory counter-search and negative-transfer analysis.

## 37. Premature convergence

**Failure:** Stop when one plausible solution appears.  
**Correction:** Identify competing method families and test decision sensitivity.

## 38. Endless research

**Failure:** Continue because another source could always exist.  
**Correction:** Use the Critical Mass Stop Doctrine and bounded decision scope.

## 39. Local invention laundering

**Failure:** An LLM combines established methods into a new rule, then calls the rule “field-proven.”  
**Correction:** Mark the combination as LOCAL SYNTHESIS or LOCAL INVENTION.

---

# Part VI — Relationship to Other Human-Driven AI Methods

## 40. Human Sandwich Model

The Human Sandwich Model primarily answers:

> **Who has authority to decide?**

Critical Mass can inform the COULD space with stronger evidence.

It does not replace the human SHOULD decision.

Research may identify strong options while leaving legitimate product, risk, scope, or value choices to the human authority.

---

## 41. VLD / The Sandwich Skewer

VLD concerns semantic authority:

> **Vibe the implementation. Lock the meaning.**

Critical Mass can be used before meaning is locked when the correct contract or method is unclear.

It can also be used later when a defect reveals that the current locked meaning may be incomplete.

Critical Mass must not silently override an accepted semantic contract. If external research conflicts with accepted local authority, report the conflict for human adjudication.

---

## 42. Nuke Testing

Nuke Testing asks:

> **What evidence justifies trusting that implementation preserves the locked meaning?**

Critical Mass asks a different question:

> **What mature knowledge should inform the method, feature, repair, or assurance strategy in the first place?**

The two reinforce one another.

Nuke Testing can discover a new problem. Critical Mass can investigate the underlying mechanism across disciplines. The resulting method can then return to Nuke Testing for adversarial validation.

A useful loop is:

```text
local observation
    ↓
mechanism abstraction
    ↓
CRITICAL MASS
    ↓
human decision / local adaptation
    ↓
implementation
    ↓
NUKE TESTING
    ↓
new evidence or failure
    ↺
```

---

# Part VII — Worked Examples

## 43. Example: deep history testing misses a defect

### Local observation

A stateful assurance campaign explores very long histories and reaches its local saturation criterion, yet a fresh challenger finds a short defect path.

### Mechanism abstraction

The problem may not be insufficient history depth.

It may be:

> the fixture/input model cannot instantiate a semantically relevant state or interaction.

### Cross-domain search

Relevant traditions include:

- software input-space coverage;
- combinatorial testing;
- model-based testing;
- experimental design;
- scenario coverage;
- sampling-frame methodology.

### Transferable mechanism

A coverage measure over executed tests does not establish adequacy of the model that generated those tests.

### Local adaptation

Separate:

- representable;
- reachable;
- exercised;
- observed;
- verdict-influential.

### Status

The external mechanism can be research-supported.

The exact five-part operational distinction may still be a local synthesis and must be labelled as such.

---

## 44. Example: authoritative decision disappears after reconstruction

### Local observation

A previously valid human decision does not survive a semantically equivalent reconstruction/re-ingestion.

### Mechanism abstraction

Potential mechanism:

> durable authoritative state is bound to episode-specific representation identity rather than semantic identity.

### Cross-domain search candidates

- event sourcing;
- workflow engines;
- temporal databases;
- distributed systems;
- configuration management;
- provenance systems;
- version control;
- regulated decision records.

### Research task

Do not ask only:

> “How should the local system persist this answer?”

Ask:

> “How do mature systems preserve authoritative decisions across replay or reconstruction while still invalidating them on genuine evidence change?”

### Transfer test

A database method may assume globally durable source identifiers.

If the target source format does not provide such identity, direct transfer may fail.

The mechanism may still transfer after adaptation.

---

# Part VIII — LLM Execution Contract

## 45. Mandatory behaviour

When instructed to “run a Critical Mass,” an LLM must:

1. restate the bounded decision;
2. record direct local evidence separately from inference;
3. derive mechanism hypotheses before solution search;
4. search materially different relevant domains;
5. prefer primary, authoritative, systematic, and operationally mature sources;
6. label evidence type;
7. identify shared evidence lineages/common-mode assumptions;
8. extract mechanisms and enabling assumptions;
9. map source mechanism to target structure;
10. attempt to falsify important transfers;
11. distinguish inherited/adapted/invented content;
12. conduct a counter-search;
13. state unresolved disagreement;
14. apply the Critical Mass Stop Doctrine;
15. report why research stopped.

---

## 46. Forbidden behaviour

An LLM running Critical Mass must not:

- search only for support of a preferred solution;
- treat source prestige as transfer proof;
- equate popularity with efficacy;
- count citations as independent evidence;
- silently merge field practice with research evidence;
- call a local synthesis “established best practice”;
- hide source disagreement;
- invent universal thresholds for evidence sufficiency;
- continue searching indefinitely without decision relevance;
- change accepted local authority without human adjudication.

---

## 47. Recommended output schema

```text
CRITICAL MASS REPORT

1. Bounded decision
2. Local observation
3. Direct evidence
4. Initial mechanism hypotheses
5. Search domains
6. Search strategy / major queries
7. Evidence families
8. Candidate method families
9. Mechanism extraction
10. Structural transfer maps
11. Transfer-assumption failures
12. Counter-evidence / competing approaches
13. Local data alignment
14. Inherited methods
15. Adapted methods
16. Local synthesis / invention
17. Residual uncertainty
18. Decision implications
19. Stop-doctrine assessment
20. Final status:
    CRITICAL_MASS_REACHED /
    CRITICAL_MASS_REACHED_WITH_RESIDUAL_UNCERTAINTY /
    CRITICAL_MASS_NOT_REACHED /
    HUMAN_RULING_REQUIRED /
    LOCAL_EXPERIMENT_REQUIRED /
    NO_TRANSFERABLE_METHOD_FOUND
```

For engineering use, include source provenance next to decision-relevant claims.

---

# Part IX — Method Maturity

## 48. What is mature

The following components have substantial precedent:

- structured evidence searching and appraisal;
- systematic evidence synthesis;
- broad evidence mapping through scoping approaches;
- comparison of heterogeneous research traditions through meta-narrative review;
- mechanism/context-oriented explanation through realist synthesis;
- evidence-based software engineering;
- analogical and cross-industry knowledge transfer;
- triangulation across evidence forms;
- explicit concern for search saturation;
- input-model adequacy as distinct from structural execution coverage.

These support the general architecture of Critical Mass.

---

## 49. What is adapted

Critical Mass adapts these ideas into a decision-oriented engineering workflow that:

- starts with mechanism abstraction;
- deliberately searches distant fields;
- ranks operational consequence as a search signal;
- requires structural transfer mapping;
- explicitly attacks the analogy;
- tracks common-mode evidence families;
- separates field maturity from efficacy;
- integrates local engineering evidence.

The exact combination is not inherited wholesale from one source.

---

## 50. What is locally invented / experimental

The following should currently be treated as local synthesis or experimental doctrine:

- the name **Critical Mass**;
- the complete sequence in this document;
- the exact evidence-label vocabulary;
- the exact transfer verdict vocabulary;
- the Critical Mass Stop Doctrine as a unified set;
- the use of the protocol as a direct LLM execution contract;
- any future fixed numeric thresholds unless separately validated.

Do not retroactively green these as externally established merely because their components have precedents.

---

# Part X — Research Basis

## 51. Evidence-synthesis discipline

The Cochrane Handbook provides mature guidance on structured searching, source selection, sensitivity, bias reduction, and documentation. Its current guidance also notes that in qualitative evidence synthesis searching can be iterative and may stop when new information ceases to emerge, with the stopping rationale documented in terms such as saturation.

**Relevance to Critical Mass:** search discipline, transparency, heterogeneous source strategy, and a precedent for justified non-exhaustive stopping in appropriate review types.

Reference:

- Lefebvre C, Glanville J, Briscoe S, et al. *Cochrane Handbook for Systematic Reviews of Interventions*, Chapter 4: Searching for and selecting studies, version 6.5.1, updated 2025.  
  https://www.cochrane.org/authors/handbooks-and-manuals/handbook/current/chapter-04

---

## 52. Meta-narrative review

RAMESES meta-narrative review is designed for heterogeneous topics where different research traditions have studied the same or similar problem in contrasting ways.

**Relevance to Critical Mass:** disciplines may encode the same mechanism using different concepts, questions, assumptions, and methods. Cross-domain synthesis must understand those traditions rather than flatten them.

Reference:

- Wong G, Greenhalgh T, Westhorp G, Buckingham J, Pawson R. *RAMESES publication standards: meta-narrative reviews.* BMC Medicine 11, 20 (2013).  
  https://doi.org/10.1186/1741-7015-11-20

---

## 53. Realist synthesis

Realist synthesis focuses on explanation: how and why an intervention or method works, in which contexts, and through which mechanisms. RAMESES guidance also emphasizes transparency, judgement, and theory-driven iteration rather than treating complex synthesis as a purely linear checklist.

**Relevance to Critical Mass:** transfer should preserve the mechanism and test the enabling context rather than copy a ritual.

Reference:

- Wong G, Greenhalgh T, Westhorp G, Buckingham J, Pawson R. *RAMESES publication standards: realist syntheses.* BMC Medicine 11, 21 (2013).  
  https://doi.org/10.1186/1741-7015-11-21

---

## 54. Evidence-based software engineering

Evidence-Based Software Engineering explicitly adapted evidence-based practice ideas to software engineering and argued for answerable questions, acquisition of evidence, critical appraisal, application, and evaluation.

**Relevance to Critical Mass:** engineering decisions should be evidence-informed rather than convention-only, and software engineering itself already contains precedent for structured evidence use.

Reference:

- Kitchenham BA, Dybå T, Jørgensen M. *Evidence-Based Software Engineering.* ICSE 2004, pp. 273–281.  
  https://doi.org/10.1109/ICSE.2004.1317449

---

## 55. Cross-industry innovation and analogical transfer

Research on cross-industry innovation examines transfer of technologies, practices, concepts, and knowledge across industry boundaries. A 2023 systematic literature review documents this as a distinct innovation research field. More recent work has explicitly tried to operationalize transfer between conceptually dissimilar industries by abstracting principles rather than directly copying practices.

**Relevance to Critical Mass:** distant industries can be useful sources of solutions, but successful transfer depends on identifying the underlying structure and adapting it to the target context.

References:

- Carmona-Lavado A, Gimenez-Fernandez EM, Vlaisavljevic V, Cabello-Medina C. *Cross-industry innovation: A systematic literature review.* Technovation 124 (2023), 102743.  
  https://doi.org/10.1016/j.technovation.2023.102743

- *Real-to-Real: synthesizing a practical method for translating project practices across conceptually dissimilar industries.* International Journal of Managing Projects in Business (2026).  
  https://www.emerald.com/ijmpb/article/19/8/124/1350856/Real-to-Real-synthesizing-a-practical-method-for

---

## 56. Input-space coverage and test-model adequacy

NIST researchers have argued that structural coverage alone can miss faults associated with rare or absent inputs, and that assurance should also examine input-space coverage and the adequacy of the input model.

**Relevance to Critical Mass:** a local failure can often be better understood by searching for the underlying assurance mechanism in adjacent research rather than merely extending the existing local test technique.

Reference:

- Kuhn DR, Kacker RN, Lei Y, Simos DE. *Input Space Coverage Matters.* IEEE Computer 53(1), 2020.  
  https://doi.org/10.1109/MC.2019.2951980  
  NIST record: https://www.nist.gov/publications/input-space-coverage-matters

---

# Part XI — Compact Doctrine

## 57. Critical Mass in twelve rules

1. **Start from the observed problem, not the preferred solution.**
2. **Abstract the underlying mechanism before broad search.**
3. **Search across materially different fields.**
4. **Prefer evidence that has survived research, use, consequence, or audit.**
5. **Distinguish field maturity from demonstrated effectiveness.**
6. **Cluster evidence into independent families.**
7. **Extract mechanisms and assumptions, not just recommendations.**
8. **Transfer mechanisms, not rituals.**
9. **Prefer structural similarity over vocabulary similarity.**
10. **Attack every important analogy.**
11. **Label inherited, adapted, and locally invented content honestly.**
12. **Stop when additional research no longer materially changes the mechanism model, credible method families, transfer assumptions, or bounded decision.**

---

## 58. Canonical short definition

> **Critical Mass is a mechanism-first cross-domain research protocol for discovering and evaluating field-proven methods. It abstracts a local problem into its underlying mechanism, searches materially different disciplines for mature responses, separates evidence of use from evidence of effectiveness, tests whether source assumptions survive transfer, actively challenges attractive analogies, and stops when additional research no longer materially changes the decision-relevant mechanism model or method choice.**

---

## 59. Canonical operational instruction

> **Run a Critical Mass on the problem before proposing a solution. Freeze the local observation, derive the underlying mechanism, search across materially different mature fields, identify independent evidence families and candidate method families, extract why each method works and under which assumptions, test structural transfer to the target, counter-search for failure and alternatives, label inherited versus adapted versus locally invented content, and stop only when the Critical Mass criteria are satisfied.**

---

## 60. Final principle

Critical Mass is not a machine for manufacturing consensus.

Its job is to make the decision landscape harder to fool.

A successful run may conclude that:

- several mature fields converge;
- one method transfers cleanly;
- only part of a method transfers;
- external practice conflicts with local evidence;
- the analogy fails;
- a human policy decision is required;
- a local experiment is required;
- no mature method exists.

All are valid outcomes.

The desired result is not:

> “Research says yes.”

It is:

> **“We understand the mechanism, we know where the evidence comes from, we know which assumptions permit transfer, we know what remains uncertain, and we know why we have enough—or do not yet have enough—to decide.”**

That is Critical Mass.
