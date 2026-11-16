# Error Handling and Defensive Code

Choose protections based on evidence of occurrence, consequences, and handling cost. Do not invent failure probabilities or enumerate every theoretical combination.

- Check external inputs, model outputs, and external service results at trust boundaries. Pass validated data internally instead of repeatedly cleaning it and guessing its shape at every layer.
- For paths with clear internal invariants, prefer explicit types, necessary assertions, and tests to express constraints. Do not hide programming errors behind broad exception handling, null substitutions, or default results.
- Handle realistically encountered timeouts and disconnections explicitly. Retry only reasonably transient failures, keep attempts bounded, and avoid duplicated retries across layers. Consider the consequences of repeating operations with side effects first.
- Rare combinations without evidence generally do not need dedicated branches. Still assess necessary protection for low-probability failures that could cause serious loss.
- Failure may be shown explicitly. Do not silently fall back to a different scoring system, dataset, permission model, or business rule and label the result a normal success without discussion. Development simulations must also be distinguishable from real execution.

Record only unhandled cases that affect acceptance, operation, or future decisions. Do not write a manual for every imagined exception.
