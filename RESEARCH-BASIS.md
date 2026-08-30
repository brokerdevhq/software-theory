# Research Basis

This document records research and prior art informing the Software Theory and Executable Intent standards. It is not itself normative.

## Core themes

### Intent formalization

The core reliability problem in agentic programming is not code generation alone but preserving and formalizing what users actually intend. Specifications should be explicit, versioned, reviewable, and independent enough from implementation to constrain it.

### Building to the test

Agents can optimize against visible evaluators in ways that satisfy tests while violating the intended reusable behaviour. This supports separating accepted intent, implementation, and evaluator-owned verification.

### Spec-driven test generation

Recent work indicates that deriving preconditions, postconditions, undefined behaviour, and other semantic constraints before generating tests can improve defect detection compared with direct test generation.

### Property-based testing by agents

Agentic workflows can infer useful general properties and search for counterexamples through property-based testing. This is particularly valuable when the property is derived from domain semantics rather than implementation mechanics.

### Test quantity is not correctness

More generated tests do not necessarily produce better issue resolution. Test count and coverage are weak proxies when the oracle itself is flawed.

### Verifier-driven agents

Training and workflows that alternate generation with executable verification can improve coding performance, but verifiers remain susceptible to reward hacking and specification error.

## Durable prior art

The standards also draw on established software and systems work:

- Donald Knuth, *Literate Programming*: organize programs and explanations for human understanding and derive representations from authoritative sources.
- John Hughes and QuickCheck: express general properties and automatically search generated input spaces for counterexamples.
- Leslie Lamport, TLA+: specify systems above implementation and mechanically explore state-space properties.
- AWS formal methods experience: use formal specification/model checking alongside conventional engineering to expose subtle distributed-system failures.
- David Parnas: modules should hide volatile design decisions rather than mirror procedural decomposition.
- Moseley and Marks, *Out of the Tar Pit*: reduce accidental complexity associated with state, control, and excessive code.
- End-to-End Arguments: correctness checks belong where the complete relevant outcome can actually be assessed.
- Waldo et al., *A Note on Distributed Computing*: remote interaction must not pretend to have local-call semantics.
- CALM: monotonicity characterizes coordination-free consistency under its formal model.
- Nix functional deployment model: explicit immutable inputs and reproducible/atomic deployment transitions provide a practical model for declared environments.

## Evidence classifications

Claims in the standards should be distinguished as one of:

- formal result;
- empirical result;
- design principle;
- industrial case study;
- architectural commitment;
- local hypothesis;
- preference.

This prevents project choices from being represented as universal scientific conclusions.

## Current research register

The register should be updated as stronger evidence, contradictory evidence, or counterexamples emerge. Particular attention should remain on:

- independent oracle construction;
- specification quality and semantic review;
- agent reward hacking against test harnesses;
- hidden/evaluator-owned verification;
- property and model generation;
- mutation-based validation of generated tests;
- reproducibility of agentic software engineering studies;
- cost/benefit of formal methods at different assurance levels.

The standards intentionally avoid tying their normative requirements to any single model vendor, benchmark, programming language, or testing framework.
