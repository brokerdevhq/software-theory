# Project Adoption Profile

**Project:** `<project>`  
**Adopted standard:** `Executable Intent <version/revision>`  
**Assurance default:** `<A0 | A1 | A2 | A3>`

## 1. Authority map

- Accepted semantic intent lives in:
- Capability specifications live in:
- Contract specifications live in:
- Change specifications live in:
- Architecture decisions live in:
- Generated publications live in:
- Conformance evidence lives in:

## 2. Technology mapping

- Primary implementation language/runtime:
- Build/environment system:
- Ordinary test framework:
- Property-based testing:
- Model-based testing:
- Fuzzing:
- Mutation/negative-control mechanism:
- Static/architecture checks:
- Contract compatibility checks:
- Literate specification format/tool:
- Machine-readable evidence format:

## 3. Canonical commands

- Build:
- Ordinary validation:
- Specification update:
- Read-only specification verification:
- Publication:
- Full CI-equivalent local check:

## 4. Agent workflow

Describe how the project separates or sequences:

- specification work;
- implementation work;
- falsification work;
- evidence publication.

State how context is isolated for A2/A3 verification, if applicable.

## 5. Assurance policy

Define which changes require which assurance level.

| Change class | Default assurance | Required independent evidence |
|---|---|---|
| ordinary implementation-preserving | | |
| semantic/domain behaviour | | |
| public contract | | |
| security/privacy | | |
| data migration | | |
| distributed coordination | | |
| deployment/operations | | |

## 6. Experiment policy

State which experiment classes are expected for common claim types.

## 7. Evidence policy

- Evidence serialization:
- Required revision identifiers:
- Random seed policy:
- Counterexample retention:
- CI artifact location:
- Committed vs ephemeral generated evidence:

## 8. Human authority

Identify who/what may approve:

- semantic specification changes;
- contract compatibility breaks;
- assurance exceptions;
- security/privacy exceptions;
- production-risk acceptance.

## 9. Accepted exceptions

| Requirement | Exception | Rationale | Scope | Revisit trigger |
|---|---|---|---|---|
| | | | | |

## 10. Local hypotheses

Record project-specific assumptions that should be evaluated rather than treated as universal principles.

## 11. Adoption status

- current assurance capability:
- missing tooling:
- known weak or self-confirming oracles:
- next adoption step:
