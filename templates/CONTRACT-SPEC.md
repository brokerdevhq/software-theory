# Contract Specification: `<contract identity>`

**Owner:** `<application/protocol authority>`  
**Version:** `<version>`  
**Status:** `<proposed | accepted | deprecated | retired>`

## 1. Purpose

What interaction does this contract govern?

## 2. Parties and authority

Identify producer(s), consumer(s), and authority for each published proposition.

## 3. Vocabulary and semantics

Define message/field meaning independently of storage or implementation types.

## 4. Identity and time

- identity semantics;
- valid/event time;
- recorded/observation time;
- provenance;
- correlation/idempotency identity.

## 5. Data/protocol shape

Describe required/optional information, validation boundaries, unknown-field behaviour, and rejection semantics.

## 6. Delivery and failure semantics

State honestly:

- delivery guarantee, if any;
- duplication behaviour;
- ordering guarantee;
- loss/retry behaviour;
- timeout meaning;
- caller-timeout/callee-success ambiguity;
- stale information;
- unavailable-party behaviour;
- partial completion;
- reconciliation.

## 7. Compatibility and evolution

Define supported producer/consumer ranges, additive/breaking changes, deprecation, coexistence, migration, and any unavoidable coordinated transitions.

## 8. Normative claims

Use stable claim identities.

## 9. Executable examples

Include representative producer/consumer interactions and failure traces.

## 10. Compatibility experiment matrix

| Producer version | Consumer version | Scenario | Expected semantic result | Evidence |
|---|---|---|---|---|
| | | | | |

## 11. Falsification plan

Exercise applicable duplication, reordering, unknown/missing fields, stale versions, ambiguous completion, malformed-but-parseable input, and schema-valid semantic incompatibility.

## 12. Unverified surface

- 

## 13. Amendments

| Version | Semantic change | Compatibility consequence | Rationale | Authority |
|---|---|---|---|---|
| | | | | |
