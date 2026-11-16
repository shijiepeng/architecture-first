# Behavioral Verification and Delivery

After everyday changes, perform a brief self-check: have you completed the actual goal and supported implicit requirements, affected related calls or shared components, introduced duplicate rules or unjustified complexity, and collected evidence that supports your conclusion? Focus on this change and direct relationships; independent review and reports are not mandatory for ordinary changes. Escalate earlier if significant risk appears. Project stage completion, overall delivery, or release preparation must move to [Independent stage review](stage-review.md); self-checks cannot replace it.

Keep verification proportionate to risk and the change. Verify core user behavior first, then important failure paths and regression risks introduced by this change. Low-impact, reversible edits do not need tests merely for formality.

Tests should observe behavior at boundaries. For example, intercept a model request and check that the updated prompt actually enters it; replace a scoring implementation with another satisfying the same contract and check that unrelated modules still work. Do not merely check that a configuration file exists, that class names match, or that a mock returns its own preset value.

Reuse verifiable checks for the same deliverable in an applicable environment. Rerun only when evidence is missing, changes invalidate it, or new risk requires it; changing workflows is not a reason to repeat checks. Compilation, type checking, and linting each establish only limited properties and cannot replace functional verification. Distinguish mocked verification, real integration verification, and unverified items. Do not summarize checks you did not execute as “tests passed.”

At delivery, briefly explain behavioral changes, necessary architectural impact, verification evidence, and substantive gaps. If basic capabilities fail, take implementation responsibility and locate the gap instead of attributing inadequate engineering quality to the user's prompt. Improve conventions based on real failures, rather than endlessly adding rules for every isolated exception.
