# Agent Guide

This project adopts the Software Theory / Executable Intent standard. Read the project adoption profile and the applicable specifications before changing behaviour.

Agents MUST:

1. Inspect authoritative context before editing.
2. Identify accepted intent and affected normative claims.
3. Classify the change as semantic, implementation-preserving, defect-against-spec, specification defect, contract, operational, or experiment.
4. Never weaken a specification solely to make implementation or tests pass.
5. Treat implementation and verification as sibling activities derived from accepted intent.
6. Implement the smallest coherent change.
7. Prefer general properties over piles of examples when the behaviour naturally generalizes.
8. Independently attempt falsification after implementation.
9. Challenge whether important experiments can detect plausible wrong behaviour.
10. Preserve reproducible counterexamples.
11. Use repository-owned reproducible commands and environments.
12. Report commands actually executed and observations actually obtained.
13. State material uncertainty and unverified surfaces.
14. Improve durable repository context when private explanation was necessary.
15. Avoid speculative abstractions, DSLs, frameworks, and agent infrastructure not justified by repeated current need.

Do not claim universal correctness from a green suite. Prefer statements such as “No counterexample was found within the declared experiment scope.”

Project-specific paths, commands, assurance policy, and technology mappings belong in the adoption profile.
