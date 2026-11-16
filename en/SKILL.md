---
name: architecture-first
description: "Architecture and complexity conventions for software projects, covering initial design, feature development, fixes, refactoring, UI changes, and stage acceptance. Read only the design, code change, UI, contract, risk, or verification rules relevant to the task; do not load the entire workflow. Purely conceptual questions do not trigger implementation workflows."
---

**English** | [简体中文](../SKILL.md)

# Architecture First and Complexity Control

Take responsibility for engineering judgment and deliver maintainable results that support the agreed user workflows. The user decides business goals and significant tradeoffs; task evidence, project conventions, and risk determine the specific methods. These conventions protect outcomes and decision authority without requiring every task to follow the same steps.

## Basis for Decisions

- **Understand the task through the intended user outcome.** A user's sentence is a starting point. Use the conversation, actual workflows, and project conventions to identify supported implicit requirements. Locally correct code does not establish that the user workflow works. Completion is defined by the agreed outcome; do not casually expand the task into project-wide governance.
- **Reserve confirmation for genuine tradeoffs.** For unresolved requirements, business rules, overall layouts, module responsibilities, or scope choices that materially change the outcome, present a concrete interpretation, options, and a recommendation, then wait for confirmation. Proceed within authorization on confirmed plans, explicit conventions, and reliably inferred requirements. Do not use confirmation to hand routine engineering judgment back to the user. Honor explicit authorization to decide independently; keep read-only reviews read-only.
- **Let evidence guide investigation.** Start with the relevant location and its direct relationships. Expand when you discover shared impact or insufficient evidence. Reuse existing context; do not scan an entire project or generate process reports for small changes. Investigate as far as necessary to support the judgment.
- **Make structure serve current needs.** Respect the architecture specified by the user. Without one, do not automatically impose plugins, microservices, or directory templates. Added complexity should address a current need or concrete risk. Avoid speculative extensibility and accumulated defenses against unlikely cases, while retaining necessary protections. Change the rule that owns the problem and check related impact; do not let a patch become a competing rule system.
- **Support completion claims with evidence.** For everyday changes, perform a brief self-check and proportionate verification. Stage completion, overall delivery, or release readiness requires thorough independent review, actual testing, and closure of blocking issues. Read the stage rules before reaching that conclusion. Reuse still-valid reviews and tests, filling only gaps. Account for real deployment conditions during design and implementation, and assess stage acceptance separately from release readiness.

## Read According to the Current Task

First identify the work at hand and read only the matching files. Simple tasks may need only this entrypoint. Do not preload every reference merely to “follow everything completely.” Combine references as needed for mixed tasks, adding more when the stage or impact changes. Do not reread unchanged material already loaded and still present in the current context.

| Current work or decision | Read |
|---|---|
| New project, major feature, or architecture change requiring discussion of core workflows and responsibilities | [Initial design](references/design.md) |
| Changing existing business code, fixing logic, refactoring, or reviewing structure without edits | [Code changes](references/changes.md) |
| Building UI, fixing layout/styles/interactions, or changing shared UI components | [UI](references/ui.md) |
| Considering a new abstraction, dependency, configuration, cache, queue, or plugin mechanism | [Complexity](references/complexity.md) |
| Integrating or changing module interfaces, plugins, prompts, editable configuration, or data contracts | [Contracts and effective configuration](references/contracts.md) |
| Handling errors, timeouts, retries, compatibility, or fallback semantics | [Failure handling](references/failures.md) |
| Designing substantive acceptance checks, running tests, or checking delivery evidence | [Verification and delivery](references/verification.md) |
| Recording design decisions, updating usage/architecture/deployment guidance, preserving stage evidence, or organizing project documentation | [Documentation maintenance](references/documentation.md) |
| Completing an independently acceptable stage, accepting a major feature as a whole, or preparing delivery or release | [Independent stage review](references/stage-review.md) and [Verification and delivery](references/verification.md) |

These are reading conditions, not a sequence of mandatory phases. Fixing button alignment usually needs only UI guidance. Investigating configuration that saves but does not take effect starts with code changes and contracts. Discussing an initial proposal does not require preloading implementation, UI, or delivery details. UI guidance already includes visual acceptance; ordinary visual checks do not automatically require the entire testing workflow.
