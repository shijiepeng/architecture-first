# Changing Existing Code

For feature additions, bug fixes, refactoring, or structural review. Follow the entrypoint's confirmation and read-only boundaries.

Understand the issue's role in the actual user workflow by starting at its location and direct calling relationships. Reuse project conventions and known context. Expand the investigation when there is shared impact, a risk to state or data writes, or insufficient evidence. A component named by the user is a clue, not enough on its own to define completion scope.

When you find a related issue, determine whether it prevents the agreed outcome. “Pre-existing” describes its origin, not whether it needs fixing. Continue necessary, authorized work that blocks the current goal; do not rewrite unrelated technical debt along the way. If one dependency is blocked, first complete necessary work independent of it and explain the remaining impact. Do not use a single environmental gap as a substitute for assessing the whole task's completion.

Prefer changing the location that owns the responsibility and rule. If the existing boundary cannot support the requirement, explain the concrete conflict and make the necessary structural adjustment. Follow entrypoint confirmation rules for unresolved responsibilities or significant scope expansion. The smallest diff does not necessarily produce the lowest maintenance cost, but structural changes still need current evidence. After editing, check for duplicated rules, unnecessary dependencies, or unintended failure semantics.

If changes invalidate usage, interface, architecture, or deployment guidance, or if an important decision needs to persist, read [Documentation maintenance](documentation.md) and update the appropriate location. Documentation should help the next person use and change the project correctly; it is not an operation-by-operation log. Do not create extra records for local changes without documentation impact.
