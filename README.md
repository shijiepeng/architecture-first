# architecture-first

**English** | [简体中文](README.zh-CN.md)

Engineering conventions for AI-assisted software development, covering project setup, ongoing changes, UI adjustments, and stage delivery. It turns a project owner's expectations for architecture, complexity, collaboration, and acceptance into a reusable skill that loads guidance as needed across projects and later changes.

## The problem it addresses

When AI is used to develop a project over time, individual changes can look complete while the overall project becomes harder to maintain: new features pile into existing files, rules are duplicated, module responsibilities become mixed, UI fixes accumulate as style patches, and documentation grows with every round of changes.

Problems also arise in understanding requirements and delivering results. A user's sentence usually describes an immediate need, while complete workflows, existing conventions, and reasonable unstated expectations sit behind it. Development needs to account for that context without expanding scope on its own. When the project is ready for real use, core workflows, real dependencies, runtime environments, and testing should already be part of the work, rather than added only after another reminder.

This skill asks the AI to take responsibility for those engineering judgments from the start and maintain the conventions through later changes. The user primarily participates in business goals and significant tradeoffs, without repeatedly reminding the AI about architecture, UI consistency, documentation organization, and basic verification.

## How it approaches the work

**Understand the intended user outcome before deciding how to organize code.** For new projects and significant features, first map core workflows, data and state movement, module responsibilities, and interfaces. Use conversation and project context to identify supported implicit requirements. For unresolved choices that materially affect the outcome, offer concrete options and a recommendation, then wait for confirmation. Proceed directly on confirmed plans and routine changes within authorization.

**Choose architecture for current needs and control maintenance costs.** If the user specifies a plugin architecture, design around plugin responsibilities, interfaces, and lifecycles. Otherwise, choose according to actual requirements. New abstractions, configuration, dependencies, and defensive logic need a current requirement or concrete risk. Changes should land where the relevant rule is owned, with structural adjustments when needed, rather than accumulating forwarding layers, duplicate rules, or extensions for imagined requirements.

**Match effort to impact.** Start investigation at the issue's location and direct relationships. Expand when shared impact or insufficient evidence emerges. Keep local changes lightweight. Discuss unresolved choices involving overall layout, module responsibilities, business rules, or substantial scope expansion. Keep everyday self-checks brief so small changes remain easy to complete.

**Maintain UI and documentation as parts of the whole project.** For UI changes, locate the effective rule and its owner, check related components, interaction states, and actual rendered views, and remove superseded style patches. Follow existing documentation organization: the README provides entrypoints, current architecture is updated in place, and plans and historical evidence live in appropriate locations. Update documentation when the change affects it.

**Judge completion by actual evidence.** Use proportionate verification for everyday changes. Independently acceptable stages, major feature acceptance, and release preparation require thorough independent review, actual testing, and rechecking after fixes. Reuse still-valid Codex reviews, CI results, and other test evidence, filling uncovered or invalidated areas. Consider the target runtime environment and real dependencies during design. Assess stage goals separately from release readiness.

These conventions emphasize goals, decision criteria, and reasons, leaving specific implementation methods to the task. Detailed rules are separated by work scenario so each change does not require loading the entire process.

## How the skill works

In Codex, invoke it explicitly:

```text
Use $architecture-first to help me advance this project.
```

It also applies to specific tasks, such as discussing a new project's plugin architecture, changing an existing feature, fixing page layout, or accepting a completed stage. [agents/openai.yaml](en/agents/openai.yaml) defines the display name, default prompt, and automatic task-based selection setting. The name and description in [SKILL.md](en/SKILL.md) describe when the skill applies.

The model first reads `SKILL.md` for shared conventions and reference routing, then reads files relevant to the current task. It adds guidance when entering a new stage or discovering a new impact area. Simple tasks can rely on the entrypoint alone; already loaded, still-valid content is reused.

| Current work | Reference |
|---|---|
| New projects, major features, and architecture tradeoffs | [design.md](en/references/design.md) |
| Feature changes, bug fixes, and refactoring | [changes.md](en/references/changes.md) |
| New abstractions, dependencies, configuration, or plugin mechanisms | [complexity.md](en/references/complexity.md) |
| Module interfaces, plugins, prompts, and configuration taking effect | [contracts.md](en/references/contracts.md) |
| Errors, timeouts, retries, and fallbacks | [failures.md](en/references/failures.md) |
| Layout, styles, interactions, and shared UI components | [ui.md](en/references/ui.md) |
| Behavioral verification, testing, and delivery notes | [verification.md](en/references/verification.md) |
| Independent stage review and deployment acceptance | [stage-review.md](en/references/stage-review.md) |
| Design records, usage guidance, and documentation organization | [documentation.md](en/references/documentation.md) |

For example, button alignment fixes primarily load UI guidance. Investigating “settings were saved but execution did not change” loads code change and contract guidance. Stage acceptance loads stage review and verification guidance. File selection follows the actual work, not the table's order.

After loading, the model works from the project's existing code, documentation, and conversation context, using file editing, browser, testing, and review tools available in the environment. It discusses significant tradeoffs requiring the user's decision, verifies implementation according to impact, and organizes independent review and handles findings at stage delivery. The detailed execution rules live in `SKILL.md` and its references; this README explains their purpose and operation.

## Language and installation

| | Skill | Files to install |
|---|---|---|
| English | [Architecture First and Complexity Control](en/SKILL.md) | Contents of `en/` |
| 简体中文 | [架构先行与复杂度控制](SKILL.md) | Root `SKILL.md`, `references/`, and `agents/` |

Copy the selected files into a folder named `architecture-first` in your agent's skills directory. For example, use `~/.claude/skills/architecture-first/` for Claude Code or `~/.codex/skills/architecture-first/` for Codex. Install one language at a time; both editions use the same skill name. To update an existing installation, back it up before replacing its files. The English edition includes the complete entrypoint, all nine references, and interface configuration.
