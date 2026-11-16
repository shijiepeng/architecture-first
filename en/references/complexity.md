# Abstraction and Complexity Tradeoffs

A new module layer, interface, configuration, dependency, cache, queue, compatibility branch, or fallback mechanism must correspond to a current requirement, a confirmed change, existing duplication, or a concrete risk. “More general,” “more robust,” or “might be useful later” alone is not sufficient justification.

- Divide modules by responsibility and independent reasons for change. Do not split files at fixed line counts or build a general framework to reuse a few one-off lines.
- Allow limited duplication. When duplicated code embodies the same business rule and must change together, choose an appropriate shared source.
- A simple interface may have only one implementation. Introduce a plugin mechanism only when there is a real need for independent replacement, extension, or lifecycle management. Do not automatically add hot reload, a plugin marketplace, auto-discovery, or independent deployment.
- Before exposing a parameter to users, determine whether they actually need to make that choice. Do not turn internally decidable implementation details into a configuration burden.
- Do not aim for the opposite extreme of minimalism: necessary authorization, data consistency, and recoverability must not be omitted simply to write less code.
