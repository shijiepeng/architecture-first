# Module Contracts and Effective Configuration

Confirm module boundaries from code, entrypoints, and calling relationships. UI, transport protocols, business rules, and infrastructure should have clear responsibilities, but a small project need not give every layer its own directory. Cross module boundaries through public contracts; do not bypass them by reading another module's private implementation.

Establish one authoritative source for a configuration or business rule. When defaults, database overrides, caches, or fallbacks are needed, explain their precedence and when they take effect. Do not maintain multiple implicit rules that can be edited independently.

Pay particular attention to these common disconnects:

- Editable configuration: follow the value from UI save through persistence and loading to its actual use during execution. A successful save does not prove that the value takes effect.
- Prompts and rule files: confirm that the calling path actually reads them. A directory's existence does not mean the feature is integrated.
- Types and schemas: ensure that external boundaries actually perform necessary validation. A definition's existence does not imply runtime validation.
- Plugins: make dependencies, inputs/outputs, failure meanings, and necessary lifecycle behavior explicit. Moving files into a plugins directory is not enough.
- Business results: make results traceable to the necessary inputs and rule versions. Choose recording granularity according to business needs; do not default to building a large audit system.
