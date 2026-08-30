# A Theory of Software

## Facts, Specifications, Autonomous Applications, Functions, Effects, and Evidence

**Version:** 0.4  
**Status:** Draft  
**Scope:** Project-agnostic engineering philosophy for software systems, applications, services, tools, repositories, and agent environments.

## Foundational thesis

A software system is a distributed federation of autonomous applications that collectively model a domain.

A software repository is an executable body of knowledge. It preserves rationale, describes promised behaviour, defines application authority, derives human and machine representations from authoritative specifications, implements those promises, and publishes evidence of conformance.

The governing chain is:

```text
theory
   ↓
domain vocabulary and authority
   ↓
application and contract specifications
   ├── human documentation
   ├── executable examples
   ├── properties and model checks
   ├── schemas and contracts
   ├── architecture fitness functions
   └── agent-readable context
   ↓
independently deployable implementations
   ↓
distributed execution and observation
   ↓
application and system conformance evidence
   ↓
published capability record
```

The implementation is not the specification. Tests are not an independently invented description of the system. Generated documentation is not a separate source of truth. Each representation must have explicit authority and provenance.

## Core axioms

1. Complexity is the primary engineering cost. New concepts carry the burden of proof.
2. A system knows claims, not reality. Unknown, disputed, stale, missing, and uncertain information are legitimate states of knowledge.
3. Authoritative change preserves evidence. Corrections normally add information rather than erase history.
4. Facts are authoritative; interpretations are functions. Do not store independent conclusions that can be derived from more fundamental facts and versioned rules.
5. Promised behaviour has a first-class specification.
6. The repository is executably literate: narrative specification, executable specification, and implementation remain connected but distinct.
7. Specifications and conformance evidence are scoped, independent, and fallible.
8. Decisions are pure relative to an explicit fact basis, rules, intent, and context.
9. Effects are uncertain until observed. Intent, attempt, acknowledgment, observed outcome, and interpretation are distinct.
10. Modules hide volatile design decisions rather than mirror procedural steps or framework nouns.
11. The system is a federation of autonomous applications. Distribution is accepted where it buys independent authority, lifecycle, failure containment, and evolution.
12. Distributed interaction is explicit and semantically honest about latency, partial failure, duplication, reordering, stale information, and version mismatch.
13. Builds, configuration, and deployments are values derived from declared versioned inputs.
14. Every change is a hypothesis; completion requires published evidence.

## Laws of specification and evidence

- Behavioural expectations originate in versioned specifications.
- A semantic specification change is an intentional domain change.
- Derivable artifacts should be generated rather than independently maintained.
- Specifications must remain sufficiently independent and simpler than implementations to provide useful constraint.
- Executable examples should be executable where practical.
- Every query, decision, projection, publication, and conformance claim is relative to an explicit basis and context.
- Consequential conclusions should be explainable as sourced facts + specification/rules + context = conclusion.
- Desired state and observed state are different inputs.
- Conformance evidence must identify application/specification/contract versions, implementation revision, environment, checks, result, scope, and limitations.
- Evidence that exists only in a terminal or agent context is not durable project evidence.
- Stable mechanically checkable rules should migrate from prose into tooling.
- Project-specific technology choices belong in adoption profiles, not the generic theory.

## Autonomous application laws

Every application should be independently specified, buildable, deployable, observable, rollbackable, replaceable, and removable.

Every authoritative proposition class must have an identified owner. Applications communicate through explicit versioned public contracts, never another application's private implementation or storage schema. A synchronous interaction creates availability and timing coupling and must be intentional. A required coordinated release is evidence of coupling and must be justified.

Repository placement, process placement, host placement, storage placement, and domain boundaries are distinct concerns. Shared infrastructure does not imply shared semantic authority.

## Specification hierarchy

Projects should distinguish:

1. theory;
2. project adoption profile;
3. system constitution;
4. domain models;
5. application/capability specifications;
6. contract specifications;
7. architectural and operational constraints;
8. derived artifacts;
9. implementation;
10. conformance evidence.

Higher semantic levels constrain lower levels. Lower levels do not silently redefine higher levels.

## Executable literacy

Executable literacy does not require every source file to become an essay or all code to be tangled from prose. It requires each important capability to be discoverable from coherent authoritative descriptions and mechanically connected evidence.

A capability specification should normally answer:

- what capability exists and why;
- what vocabulary and authority it owns;
- what facts are authoritative versus derived;
- what invariants and transitions are promised;
- what contracts are consumed/published;
- what effects and failures are possible;
- what examples illustrate intended semantics;
- what is mechanically verifiable;
- how conformance is observed;
- what remains uncertain or outside scope.

The prohibited dependency is:

```text
implementation
    ↓
expectation generated from implementation
    ↓
test confirms implementation matches itself
```

The preferred dependency is:

```text
accepted meaning
    ↓
normative claims/specifications
   ├── implementation
   └── independent experiments
            ↓
       observations/evidence
```

The detailed operational standard for this relationship is defined in [`EXECUTABLE-INTENT.md`](EXECUTABLE-INTENT.md).

## Agent constitution

Agents must inspect before reasoning, locate authority, classify semantic versus implementation changes, preserve application autonomy, choose the smallest coherent slice, keep decisions pure, model relevant distributed failure, maintain executable literacy, run declared checks, inspect the final diff, publish conformance evidence, and report observations rather than confidence.

When an agent fails because context, tooling, environment, authority, or guardrails are missing, improve the repository so subsequent agents do not require the same private explanation.

## Technology neutrality

This theory does not select a language, database, framework, configuration system, deployment system, cloud, transport, repository strategy, literate-programming tool, or agent vendor.

Technology-specific mappings are replaceable projections of the theory. They belong in project adoption profiles and architecture decisions.

## Evidence classifications

Major theoretical claims should be distinguishable as:

- formal results;
- empirical results;
- design principles;
- industrial case studies;
- architectural commitments;
- local hypotheses;
- preferences.

The theory itself is amendable and should be challenged by project experience and research.
