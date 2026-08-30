# Executable Intent

## A project-agnostic theory and operating standard for literate specification, adversarial verification, and evidence-driven software development

**Version:** 0.1  
**Date:** 2026-08-29  
**Status:** Draft for adoption and experimentation  
**Scope:** Human- and agent-built software systems, applications, services, libraries, tools, contracts, and repositories

---

## Abstract

Software is not correct because its author is confident, because an agent says it is complete, or because a test suite is green. Correctness is a claim that an implementation realizes accepted human intent under stated assumptions. That claim can be supported, weakened, or falsified by evidence; it cannot normally be manufactured by the implementation or its author.

This standard treats a repository as an executable body of knowledge and an experimental environment. Human intent is formalized into a durable literate specification. The specification states meaning, scope, claims, invariants, boundaries, forbidden behaviour, failure semantics, and uncertainty. Implementation and verification are separate projections of that accepted specification. Tests, properties, models, simulations, architecture rules, compatibility suites, and production observations are experiments. Their outputs are observations. Conformance is a scoped interpretation of those observations, not a declaration of universal correctness.

The central dependency is:

```text
human need and domain understanding
              ↓
       proposed intent
              ↓
  accepted literate specification
        ┌─────┴──────────────┐
        ↓                    ↓
 implementation       independent experiments
        │                    │
        └────────┬───────────┘
                 ↓
          reproducible observations
                 ↓
           scoped evidence
                 ↓
       conformance judgment +
       explicit unverified surface
```

The central prohibition is:

```text
implementation
      ↓
expectations reverse-engineered from that implementation
      ↓
tests confirm that the implementation matches itself
      ↓
unsupported claim of correctness
```

The goal is not maximal ceremony, maximal test count, or maximal formalism. The goal is the smallest independent body of specification and evidence capable of constraining an implementation and exposing meaningful error.

---

## 1. Purpose

This document defines a reusable philosophy and prescriptive operating standard for projects in which humans and AI agents design, implement, test, review, and operate software.

It exists to answer five questions:

1. How does a project preserve what users and domain owners actually intend?
2. How can that intent constrain implementations without becoming a second implementation?
3. How should agents generate experiments that try to disprove their own work rather than merely confirm it?
4. What evidence is sufficient to claim completion within a declared scope?
5. How can the resulting knowledge remain useful to later humans and agents without depending on private conversation history?

This standard is deliberately technology-neutral. It does not mandate a programming language, database, test framework, formal method, agent vendor, repository structure, or literate-programming tool. Each adopting project maintains a local adoption profile that explains how its chosen tools realize the requirements.

The standard applies to accepted software, not necessarily to every exploratory keystroke. Spikes may begin with incomplete understanding. They remain experiments until their intended semantics, constraints, and evidence have been made explicit.

---

## 2. Normative language

The terms **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**, and **MAY** are normative.

- **MUST / REQUIRED**: necessary for conformance to this standard at the declared assurance level.
- **MUST NOT**: prohibited because it defeats a core property of the standard.
- **SHOULD / SHOULD NOT**: expected unless a documented local reason justifies an exception.
- **MAY**: permitted but optional.

A project can adopt the philosophy before it satisfies every operational requirement. It MUST state its current assurance level, gaps, and accepted exceptions rather than presenting partial adoption as complete conformance.

---

## 3. Foundational thesis

### 3.1 Software implements a model of intent, not intent itself

A user request, issue, conversation, diagram, policy, or domain explanation is evidence of intent. None is automatically a complete specification. The implementation is another interpretation of that evidence. It cannot serve as the sole authority for what the user meant.

Natural-language intent is often incomplete, inconsistent, contextual, or wrong. Formalization is therefore not mechanical transcription. It is a process of making commitments visible:

- which behaviour is promised;
- which concepts have stable meaning;
- which assumptions are accepted;
- which cases are undefined;
- which failures are tolerable;
- which risks require stronger assurance;
- which uncertainties remain unresolved.

A specification is itself an authored claim and may be amended. Its value comes from being explicit, reviewable, simpler than the implementation, and sufficiently independent to constrain it.

### 3.2 A repository is an executable body of knowledge

A repository should preserve and connect:

- domain vocabulary and rationale;
- accepted intent;
- normative claims and invariants;
- public contracts and authority;
- executable examples and properties;
- implementation source;
- experiment definitions;
- build and execution environments;
- conformance observations;
- known limitations and unresolved questions.

These artifacts need not live in one file. “Single source of truth” means clear authority and derivation, not physical centralization. The repository should maintain as little independent repetition as possible and derive every representation that can be derived reliably from more authoritative information.

### 3.3 Verification is experimental

A test is an experiment performed on an implementation under particular conditions. Its result is an observation. A passing result means only that the experiment did not expose a contradiction under those conditions.

The scientifically honest conclusion is usually:

> No counterexample was found within the declared experiment scope.

It is usually not:

> The software is correct.

Evidence becomes stronger when experiments are:

- derived from accepted claims rather than implementation details;
- capable of failing on plausible wrong implementations;
- independent in authorship, abstraction, data, or oracle;
- heterogeneous in method;
- reproducible;
- explicit about assumptions and untested surfaces.

### 3.4 Agents change the bottleneck

Agents make implementation cheap enough that verification, semantic review, and harness quality become the limiting resources. The correct response is not merely to ask agents for more tests. It is to give agents a durable specification, separate implementation and falsification roles, design experiments that discriminate between conforming and nonconforming behaviour, and publish the resulting evidence.

Human attention should concentrate on the scarce semantic work:

- accepting intent;
- resolving ambiguity;
- choosing authority and boundaries;
- deciding acceptable risk;
- reviewing specification changes;
- judging whether the evidence scope is adequate.

Agents and automation should perform the abundant mechanical work:

- generating candidate implementations;
- deriving examples and properties;
- searching for counterexamples;
- exploring edge cases and failure modes;
- running compatibility matrices;
- validating experiments against known-bad variants;
- collecting deterministic evidence;
- keeping publications current.

---

## 4. The epistemic model

This standard distinguishes statements by their role.

### 4.1 Intent

A statement about what an actor wants the software to accomplish or preserve.

Intent does not prove that the requested behaviour is coherent, safe, feasible, or complete.

### 4.2 Accepted intent

Intent that the responsible human or domain authority has approved as the basis for implementation within a declared scope.

Accepted intent may remain partly informal. The applicable normative claims must nevertheless be explicit enough to review and verify.

### 4.3 Claim

A proposition asserted by a specification, implementation, experiment, person, or agent.

Examples:

- “A completed session is derived from the presence of an end observation.”
- “This endpoint is idempotent for a stable request identity.”
- “This change preserves compatibility with contract version 2.”
- “The complete test suite passed in environment X.”

Claims have sources and scopes. A claim is not automatically true because it appears in a specification or report.

### 4.4 Normative claim

A versioned proposition in an accepted specification that defines required, forbidden, or permitted behaviour.

Normative claims are the primary unit of traceability in this standard. Examples, tests, properties, architecture rules, and evidence SHOULD identify the normative claims they support or challenge.

### 4.5 Observation

A time- and context-bound report of what an experiment, tool, system, or person observed.

### 4.6 Evidence

An observation relevant to whether a normative claim should be accepted, rejected, weakened, or left unresolved.

### 4.7 Conformance

A scoped judgment that an implementation has not been shown to violate a declared set of normative claims under a declared observation model and experiment set.

### 4.8 Counterexample

An input, state, execution trace, schedule, dependency condition, or environment that demonstrates a violation of a normative claim.

### 4.9 Oracle

A source used by an experiment to determine expected behaviour or distinguish acceptable from unacceptable outcomes.

An oracle may be an explicit expected value, property, reference model, independent implementation, schema, contract, invariant, human judgment, formal proof obligation, or external source.

An oracle that is merely the production implementation called through another path is not independent.

### 4.10 Experiment

A reproducible procedure designed to produce observations relevant to one or more claims.

Experiments include ordinary tests, property checks, model-based tests, mutation tests, fuzzing, static checks, architecture fitness functions, simulations, compatibility tests, fault injection, formal model checking, differential testing, benchmarks, and operational probes.

---

## 5. Laws

### Law 1: Intent must become durable before acceptance

Accepted behaviour MUST be discoverable from repository-resident artifacts or an explicitly versioned external authority.

Private chat context is not durable specification.

### Law 2: Specification authority precedes implementation authority

Normative behavioural expectations MUST originate in a versioned specification, contract, policy, or accepted change record.

Implementation MUST NOT silently redefine expected behaviour.

### Law 3: Claims are the unit of semantic traceability

Meaningful behaviour SHOULD be stated as stable normative claims. Experiments and evidence SHOULD identify which claims they address.

### Law 4: Tests are not the specification

Tests MAY encode examples or executable projections of claims, but test code is not automatically authoritative for semantics.

A failing test may reveal a defect in the implementation, test, specification, or domain understanding.

### Law 5: Implementation and verification are sibling activities

Implementation and verification SHOULD both be derived from accepted intent. Verification SHOULD NOT be solely derived from the implementation under test.

### Law 6: Verification must seek falsification

For each material claim, the project SHOULD identify plausible ways the claim could be false and design experiments capable of exposing those failures.

### Law 7: An experiment must be capable of discriminating

A useful experiment MUST fail for at least one plausible nonconforming behaviour relevant to its claim.

Where practical, this SHOULD be demonstrated using a known-bad implementation, semantic mutation, historical defect, negative fixture, or deliberately violated contract.

### Law 8: Independent evidence is stronger than self-confirmation

Higher-risk claims SHOULD receive verification with meaningful independence from the implementation activity.

Independence may come from a different agent, different context, different model, different abstraction, hidden evaluator-owned cases, a reference model, formal method, or human review.

### Law 9: Multiple weak tests do not equal one strong oracle

Test count, line coverage, and assertion count are observations, not measures of semantic correctness. Projects SHOULD optimize for discriminating evidence, not test volume.

### Law 10: General properties dominate enumerated examples when appropriate

When behaviour can be expressed as an invariant or algebraic/temporal property, projects SHOULD prefer a general property plus generated exploration over a large hand-curated list of examples.

Examples remain valuable for communication, regression, boundaries, and representative semantics.

### Law 11: Evidence is scoped

Every conformance claim MUST state or link to the applicable specification, implementation revision, environment, experiment set, and limitations.

### Law 12: No green boolean may erase uncertainty

Projects MUST NOT represent universal correctness as a derived `true` merely because declared experiments passed.

Machine-readable judgments SHOULD use calibrated terms such as:

- `supported-within-scope`;
- `not-falsified-within-scope`;
- `falsified`;
- `inconclusive`;
- `not-checked`.

### Law 13: Counterexamples are first-class knowledge

A counterexample MUST be preserved with enough information to reproduce it where security and privacy allow.

Shrunk/minimized counterexamples SHOULD become durable regression evidence when the normative claim remains accepted.

### Law 14: Specifications are fallible

A counterexample may show that the implementation is wrong or that the specification is wrong. Agents MUST NOT weaken a claim automatically merely to restore green verification.

Semantic amendments require explicit authority.

### Law 15: Generated artifacts are projections

Generated docs, schemas, diagrams, tests, manifests, and reports MUST identify their authoritative inputs and MUST NOT become independently maintained competing truth.

### Law 16: Stable rules migrate into tooling

Repeated mechanically checkable review rules SHOULD become executable checks. Prose explains purpose and scope; tooling enforces the rule.

### Law 17: Evidence must be published

Evidence confined to an agent’s private reasoning, terminal session, or ephemeral environment does not satisfy Definition of Done.

### Law 18: The harness is part of the product

When agents repeatedly fail because of missing context, weak fixtures, nondeterministic environments, unclear ownership, or unverifiable requirements, the repository SHOULD be improved so the next attempt has a stronger experimental harness.

---

## 6. Specification hierarchy

An adopting project SHOULD distinguish these levels:

1. theory/philosophy;
2. project adoption profile;
3. system/domain constitution;
4. capability/application specifications;
5. public contract specifications;
6. change specifications;
7. executable projections and experiments;
8. implementation;
9. observations/evidence;
10. published conformance judgments.

Higher semantic levels constrain lower implementation levels. Lower levels MUST NOT silently redefine higher levels.

---

## 7. Literate specification

A literate specification is an authoritative human-readable description linked to executable claims and evidence. It does not require all source code to live inside prose.

Each significant capability SHOULD identify:

- purpose and user/domain intent;
- vocabulary;
- authority;
- assumptions;
- normative claims;
- invariants;
- examples;
- forbidden behaviour;
- failure semantics;
- external effects;
- public contracts;
- observability;
- uncertainty;
- non-goals;
- experiment strategy;
- unverified surface.

Each normative claim SHOULD have a stable identity.

A claim should normally be expressed at a level above implementation mechanics. For example:

> `session/completion-derived-from-end`: A session is complete if and only if an authoritative end observation exists in the applicable fact basis.

is preferable to:

> Call `session.core/completed?` and expect `true` when its current branch condition returns true.

The first constrains multiple possible implementations. The second mirrors one.

---

## 8. Experiment classes

Projects SHOULD choose the smallest combination appropriate to the claim and risk.

### 8.1 Executable examples
Representative specific cases with explicit expected semantics.

### 8.2 Property-based experiments
Generate many cases and seek counterexamples to a general property.

### 8.3 Model-based experiments
Compare implementation traces against a simpler state machine, transition model, or reference semantics.

### 8.4 Metamorphic experiments
Assert relationships across transformations when exact expected outputs are hard to enumerate.

### 8.5 Differential experiments
Compare independent implementations or versions over the same inputs.

### 8.6 Mutation experiments
Introduce plausible semantic defects and verify that the experiment suite detects them.

### 8.7 Fuzzing
Explore malformed, unexpected, boundary, and adversarial inputs.

### 8.8 Contract/compatibility experiments
Exercise independently versioned producers and consumers.

### 8.9 Architecture fitness functions
Mechanically enforce structural claims such as forbidden dependency directions or private-state access.

### 8.10 Failure experiments
Exercise timeout, duplication, loss, reordering, stale data, dependency outage, partial completion, and ambiguity where applicable.

### 8.11 Formal/model checking
Explore mathematically defined state spaces and temporal properties when risk/complexity warrants it.

### 8.12 Operational experiments
Verify observable runtime claims in a declared environment.

No project is required to use every class.

---

## 9. Experiment validity

A passing experiment is only useful if it could have failed for a meaningful defect.

For important claims, the verifier SHOULD ask:

1. What plausible wrong implementation would still pass this experiment?
2. Can we construct that implementation or mutation?
3. Does the experiment fail against it?
4. Is the oracle independent of the production implementation?
5. Is the generated input distribution exercising meaningful boundaries?
6. Does the experiment accidentally encode the same misunderstanding as the implementation?
7. Are hidden assumptions explicit?

An experiment that passes both the intended implementation and relevant known-bad variants is weak evidence and SHOULD be repaired or downgraded.

---

## 10. Independence model

Independence is not binary. Projects SHOULD classify important verification roughly as:

- **I0 — self-confirming:** implementation and experiment produced together from the same local context/oracle;
- **I1 — claim-derived:** experiments explicitly derived from accepted claims rather than implementation details;
- **I2 — contextual independence:** verifier operates without implementation-author reasoning and independently chooses cases/properties;
- **I3 — oracle independence:** hidden cases, independent model, alternate implementation, formal semantics, or evaluator-owned tests;
- **I4 — external independence:** independent human/domain review or externally maintained conformance authority.

Low-risk changes may rely heavily on I1. High-risk semantics SHOULD combine multiple evidence types and stronger independence.

Different agents using the same specification can provide useful contextual independence, but merely changing agent identity is not automatically independent if both share the same flawed oracle.

---

## 11. Agent operating model

Projects using coding agents SHOULD separate roles conceptually even when one model performs multiple roles sequentially.

### Specification role

- inspect user intent and existing authoritative artifacts;
- identify ambiguity and semantic changes;
- propose normative claims, examples, invariants, and forbidden behaviour;
- do not silently accept material semantic assumptions.

### Implementation role

- treat accepted claims as constraints;
- implement the smallest coherent change;
- do not weaken claims/tests to accommodate the implementation;
- add implementation-proximate regression checks as useful.

### Falsification role

- begin from the accepted claims, not the implementation author’s explanation;
- construct plausible counterexamples;
- use properties, generated inputs, semantic mutations, failure injection, and boundary exploration;
- report falsifications and uncertainty rather than optimizing for green.

### Evidence role

- run declared reproducible commands;
- capture observations as deterministic data;
- identify implementation/spec/environment revisions;
- publish limitations and unverified surfaces.

A project MAY use one agent sequentially for these roles, but higher assurance SHOULD isolate context or use separate agents/evaluators.

---

## 12. Change workflow

For every material accepted change:

1. Inspect the current specification, implementation, tests, evidence, and relevant runtime observations.
2. Classify the change: semantic change, implementation-preserving change, defect against spec, specification defect, contract change, operational change, or experiment.
3. State the intended semantic delta.
4. Identify affected normative claims.
5. Amend or add claims only with appropriate authority.
6. Define representative examples and falsification targets before or independently of implementation where practical.
7. Implement the smallest coherent change.
8. Run the full ordinary validation suite.
9. Run claim-linked experiments.
10. Independently attempt falsification.
11. Validate important experiments with negative controls or semantic mutations.
12. Record counterexamples, if found.
13. Resolve whether a failure belongs to implementation, experiment, specification, or domain understanding.
14. Publish observations and scoped judgments.
15. Record remaining uncertainty.

---

## 13. Assurance levels

Projects MAY define stricter local levels; the following provides a common baseline.

### A0 — exploratory

- intent may be provisional;
- experiments may be ad hoc;
- not releasable as an accepted capability without explicit exception.

### A1 — ordinary

Required:

- accepted intent/claims;
- ordinary automated tests/checks;
- at least one claim-linked experiment for changed semantics;
- reproducible project validation;
- published scoped evidence;
- limitations stated.

### A2 — adversarial

A1 plus:

- independent falsification activity;
- property/model/fuzz/failure experiments where applicable;
- experiment validity demonstrated through negative controls, mutation, or known-bad behaviour;
- important claims traceable to evidence.

### A3 — critical

A2 plus a risk-appropriate combination of:

- hidden evaluator-owned cases;
- formal model/proof obligations;
- independent implementations;
- external/domain review;
- extensive fault injection;
- production canary or runtime evidence;
- stronger supply-chain/reproducibility controls.

Assurance level is not a quality grade. It describes the required evidence burden.

---

## 14. Evidence model

Evidence SHOULD preserve primary observations rather than only a derived pass/fail status.

A machine-readable record SHOULD identify:

- project/application/capability identity;
- specification identity/version/revision;
- normative claim identities;
- implementation revision/artifact identity;
- environment/tool revisions;
- experiment identities/revisions;
- independence level where useful;
- generated-input parameters/seeds where reproducibility requires them;
- counts/results/counterexamples;
- derived scoped judgments;
- limitations;
- unverified claims/surfaces.

A record SHOULD prefer:

```text
property cases: 10,000
counterexamples: 0
mutations tested: 5
mutations detected: 5
```

over:

```text
correct: true
```

Judgments are projections of evidence. Primary observations should remain inspectable.

---

## 15. Literate tooling contract

An adopting project MAY use Org mode, Markdown, notebooks, executable documentation, DSLs, or other mechanisms. The relationships are normative; the format is local.

Where a literate source embeds or selects executable checks, projects SHOULD maintain distinct operations for mutation and verification:

- **spec-update**: execute authoritative checks and refresh recorded deterministic evidence;
- **spec-check**: read-only recomputation that fails when results are stale, inconsistent, or failing;
- **spec-publish**: derive human/machine publications from the verified specification/evidence graph.

CI MUST use read-only verification. CI MUST NOT silently rewrite authoritative specifications to make them current.

Ordinary test suites SHOULD remain independently runnable. A literate runner should select claim-linked experiments and collect structured evidence, not replace the project’s normal test discovery system.

---

## 16. Definition of Done

A material change is complete only when, within its declared assurance level:

- prior state was inspected;
- user/domain intent is durable;
- semantic delta is explicit;
- affected normative claims are identified;
- specification changes are intentional and reviewed by the appropriate authority;
- implementation exists as the smallest coherent slice;
- full ordinary checks pass;
- changed semantic claims have claim-linked experiments;
- relevant failure modes have been considered and exercised where applicable;
- required independent falsification has occurred;
- important experiment validity has been demonstrated where required;
- contract compatibility has been checked where affected;
- reproducible declared environment was used;
- observations have been captured as durable evidence;
- counterexamples are resolved or explicitly accepted;
- remaining uncertainty and unverified surfaces are stated;
- generated publications are current;
- final diff does not introduce accidental authority, duplication, weakened checks, or speculative abstraction.

“Agent says done” is not a completion criterion.

“All tests pass” is necessary evidence where tests apply, but not sufficient by itself.

---

## 17. Prohibited patterns

The following violate the philosophy unless explicitly scoped as exploration:

- deriving expected behaviour solely from the production implementation;
- automatically changing specifications when implementation tests fail;
- using generated test quantity as a proxy for correctness;
- claiming universal correctness from finite testing;
- hiding unverified high-risk behaviour behind a single green status;
- allowing implementation agents to edit hidden evaluator-owned tests;
- committing nondeterministic evidence that cannot be meaningfully compared;
- duplicating normative semantics across prose, test, implementation, and generated docs without declared authority;
- treating coverage targets as semantic evidence by themselves;
- inventing a generalized specification DSL before recurring stable forms justify it;
- building a multi-agent orchestration platform before a simple sequential implementation/falsification workflow demonstrates need;
- treating a second agent as independent when it merely repeats the same implementation-derived oracle.

---

## 18. Minimal repository embodiment

Exact paths are not normative. A practical shape is:

```text
docs/
  theory/
  adoption/
  domain/
  decisions/

specifications/
  capabilities/
  contracts/
  changes/

experiments/
  examples/
  properties/
  models/
  architecture/
  compatibility/
  failure/
  fuzz/

src/
tests/

evidence/
  conformance/

generated/
  specifications/
  schemas/
  reports/

AGENTS.md
```

Projects SHOULD begin smaller and add categories only when they contain real artifacts.

---

## 19. Adoption protocol

A new project adopts this standard incrementally:

1. Copy/reference the canonical standard and record the adopted version.
2. Create a project adoption profile mapping requirements onto actual tools and paths.
3. Add a concise AGENTS guide locating authoritative artifacts and validation commands.
4. Select one real capability—not a fake demonstration subsystem.
5. Write a literate capability specification with 2–5 important normative claims.
6. Link existing ordinary tests where they genuinely support those claims.
7. Add one stronger falsification-oriented experiment, preferably property-based or model-based where appropriate.
8. Demonstrate that the stronger experiment detects at least one plausible wrong variant.
9. Publish deterministic evidence with limitations.
10. Run the workflow on several real changes before adding DSLs, generalized schedulers, or orchestration machinery.

The adoption profile MUST distinguish universal requirements from project-specific technology choices.

---

## 20. Agent constitution

Agents operating in an adopting project MUST:

1. inspect authoritative context before editing;
2. identify the accepted intent and affected normative claims;
3. classify semantic vs implementation changes;
4. never weaken a specification solely to make code pass;
5. distinguish examples, experiments, observations, evidence, and judgments;
6. implement the smallest coherent change;
7. prefer general properties over enumerated examples when they better express the claim;
8. independently seek counterexamples after implementation;
9. challenge whether experiments could detect plausible wrong behaviour;
10. preserve reproducible counterexamples;
11. use project-owned reproducible commands/environment;
12. report what was actually executed and observed;
13. state uncertainty and unverified surfaces;
14. update durable project knowledge when private explanation was required;
15. avoid speculative abstractions, DSLs, frameworks, and agent infrastructure not justified by current repeated need.

Agents SHOULD use language such as:

> “No counterexample was found in 10,000 generated cases under property P.”

rather than:

> “The feature is definitely correct.”

---

## 21. Prescriptive requirements catalogue

### Intent and authority

- **EI-001** Accepted semantics MUST have a durable authority.
- **EI-002** Semantic changes MUST intentionally amend that authority.
- **EI-003** Implementation MUST NOT be the sole source of expected semantics.
- **EI-004** Material claims SHOULD have stable identities.
- **EI-005** Specifications MUST state known uncertainty where material.

### Literate specification

- **EI-010** Significant capabilities SHOULD have a human-readable specification.
- **EI-011** The specification SHOULD include intent, claims, examples, forbidden behaviour, failures, and non-goals.
- **EI-012** Mechanically verifiable claims SHOULD link to executable experiments.
- **EI-013** Narrative and executable representations MUST have declared authority/derivation relationships.
- **EI-014** Generated publications MUST NOT become independent semantic authority.

### Implementation

- **EI-020** Implementation MUST be constrained by the accepted specification.
- **EI-021** Implementation-preserving refactors SHOULD NOT rewrite normative claims.
- **EI-022** The implementation SHOULD expose stable boundaries suitable for observation without coupling experiments to internals unnecessarily.

### Verification

- **EI-030** Verification MUST include the project’s ordinary validation path.
- **EI-031** Changed semantics MUST have claim-linked experiments at A1+.
- **EI-032** A2+ MUST include independent falsification activity.
- **EI-033** A2+ SHOULD include experiment validity checks via negative controls or mutations for important claims.
- **EI-034** Property/model-based methods SHOULD be used when a claim naturally generalizes.
- **EI-035** Distributed/external interactions SHOULD exercise relevant failure semantics.
- **EI-036** Public contract changes SHOULD exercise independent-version compatibility.
- **EI-037** Test count/coverage MUST NOT be presented as sufficient semantic proof.
- **EI-038** Evaluator-owned hidden tests MUST NOT be editable by the implementation role.

### Evidence

- **EI-040** Evidence MUST identify applicable specification and implementation revisions.
- **EI-041** Evidence MUST identify the declared environment sufficiently for reproduction.
- **EI-042** Evidence SHOULD preserve primary observations.
- **EI-043** Evidence MUST state limitations/unverified surfaces for material claims.
- **EI-044** Falsified claims MUST preserve reproducible counterexamples where allowed.
- **EI-045** Conformance judgments MUST be scoped and MUST NOT assert universal correctness without proof warranting that statement.
- **EI-046** Required evidence MUST be durable and linked to the change/release.

### Tooling

- **EI-050** CI verification MUST be read-only with respect to authoritative specifications.
- **EI-051** Recorded literate results MUST be checked for staleness if committed.
- **EI-052** Generated evidence SHOULD be deterministic except for explicit recorded random seeds/inputs.
- **EI-053** Stable mechanically checkable rules SHOULD migrate from prose to tooling.
- **EI-054** The project MUST retain a canonical ordinary validation command or equivalent documented command set.

### Agents

- **EI-060** Agents MUST inspect before asserting current state.
- **EI-061** Agents MUST distinguish semantic and implementation changes.
- **EI-062** Agents MUST NOT automatically weaken claims/tests because implementation fails.
- **EI-063** Agents performing falsification SHOULD begin from claims without relying on the implementation author’s private reasoning.
- **EI-064** Agent completion reports MUST state commands/evidence actually observed.
- **EI-065** Agents MUST report material uncertainty.
- **EI-066** Repeated missing-context failures SHOULD result in repository/harness improvements.

### Complexity control

- **EI-070** Adoption MUST NOT require a custom specification DSL.
- **EI-071** Adoption MUST NOT require a multi-agent orchestrator.
- **EI-072** New verification infrastructure MUST justify its conceptual and maintenance cost with a current evidence need.

---

## 22. Example

Consider the claim:

> A session is complete if and only if an authoritative end observation exists.

A weak workflow is:

```text
implement completed?
write examples matching implementation
examples pass
```

A stronger workflow is:

```text
accepted claim
   ├── example: no end => incomplete
   ├── example: end exists => complete
   ├── property: completed?(basis) == contains-end?(basis)
   ├── metamorphic: adding unrelated facts cannot change completion
   └── architecture rule: persisted status is not read by completion derivation

implementation

falsification:
   - generate arbitrary valid fact bases
   - inject arbitrary unrelated facts
   - inject :status values
   - mutate implementation to always true
   - mutate implementation to always false
   - mutate implementation to read status

observations:
   examples: 4/4 pass
   generated cases: 10,000
   counterexamples: 0
   semantic mutations: 3
   mutations detected: 3

judgment:
   normative claim not falsified within declared scope

unverified:
   concurrent writers
   malformed temporal observations
```

This is more informative than “tests pass” while remaining much cheaper than proving the entire application correct.

---

## 23. What this standard does not claim

This standard does not claim that:

- specifications perfectly capture human intent;
- agents can independently verify themselves without oracle risk;
- property testing is proof;
- formal methods remove modeling error;
- separate agents guarantee independence;
- hidden tests guarantee real-world correctness;
- every capability warrants sophisticated verification;
- all uncertainty can be eliminated.

It instead requires uncertainty to be represented honestly and the verification burden to scale with consequence and risk.

---

## 24. Project-local adoption questions

Each project SHOULD answer:

1. Where does accepted semantic intent live?
2. What artifact format is used for literate specifications?
3. How are normative claims identified?
4. What is the ordinary validation command?
5. Which property/model/fuzz tools are available?
6. How are experiments linked to claims?
7. How are negative controls or mutations performed?
8. How is verification context isolated from implementation when A2+ is required?
9. Where are evaluator-owned checks stored?
10. How are deterministic evidence records produced?
11. What conformance serialization is used?
12. What are the project’s assurance classes?
13. Which claims require human/domain approval?
14. What remains manual review?
15. Which exceptions to this standard are accepted and why?

---

## 25. Evolution of the standard

This standard is itself a set of claims. It should be challenged by project experience and research.

Changes to the standard SHOULD record:

- the claim being amended;
- new evidence or counterexample;
- expected project impact;
- whether the change is philosophical, normative, or illustrative;
- migration guidance where required.

Projects SHOULD pin an adopted version rather than silently inheriting every upstream amendment.

---

## 26. Canonical summary

Software development under this standard is a disciplined cycle of interpretation and attempted falsification:

```text
understand intent
    ↓
state accepted claims
    ↓
make claims durable and executable where useful
    ↓
implement independently of the verifier
    ↓
construct experiments from the claims
    ↓
try to falsify the implementation
    ↓
try to falsify the experiments
    ↓
preserve observations and counterexamples
    ↓
derive only the confidence those observations warrant
    ↓
publish what remains unknown
```

The standard's most important rule is simple:

> Do not ask software—or an agent—to certify itself by agreeing with expectations derived from itself.

Instead, preserve intent separately, express meaningful claims, and build a repository that can continually produce evidence both for and against its own implementations.
