# Software Theory

A project-agnostic engineering constitution for software systems and AI-assisted development.

This repository contains the canonical theory and adoption standards used by projects that choose to adopt them. Project-specific technologies, repository layouts, commands, and exceptions belong in each project's adoption profile rather than in the generic theory.

## Canonical documents

- [`THEORY.md`](THEORY.md) — the general theory of software.
- [`EXECUTABLE-INTENT.md`](EXECUTABLE-INTENT.md) — the normative standard for executable intent, falsification, and evidence-driven software development.
- [`RESEARCH-BASIS.md`](RESEARCH-BASIS.md) — research and prior art informing the standards.

## Adoption

Projects should not fork and independently rewrite the canonical theory. Instead they should identify the version they adopt and maintain local mappings for their actual stack and workflow.

Start with:

- [`templates/ADOPTION-PROFILE.md`](templates/ADOPTION-PROFILE.md)
- [`templates/AGENTS.md`](templates/AGENTS.md)
- [`templates/CAPABILITY-SPEC.md`](templates/CAPABILITY-SPEC.md)
- [`templates/CONTRACT-SPEC.md`](templates/CONTRACT-SPEC.md)
- [`templates/CHANGE-SPEC.md`](templates/CHANGE-SPEC.md)
- [`templates/PR-EVIDENCE.md`](templates/PR-EVIDENCE.md)

The objective is not ceremonial documentation. The objective is a repository in which accepted intent constrains implementation, independent experiments attempt to falsify claims, and durable evidence records what has actually been established within a declared scope.
