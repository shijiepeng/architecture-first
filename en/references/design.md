# Initial Design and Major Architecture Changes

For new projects, major capabilities, or architecture changes. Reuse existing context and designs; identify unresolved goals and implicit requirements. When no proposal exists, proactively offer a concrete design. Wait for confirmation before implementing key tradeoffs that materially affect the outcome. Do not seek renewed approval for existing plans or engineering choices already delegated to you. A simple script needs proportionate design, not the entire workflow.

Use brief prose, a necessary flow diagram, or a small table to explain:

- The outcome to deliver now and the current scope.
- One core user workflow, including how requests, state, and data move.
- Who owns the main responsibilities and which contracts connect the modules.
- Which changes have evidence supporting a need for replaceability, and which are speculation.
- Key tradeoffs affecting the user, the recommended option, and its costs.

Discuss only genuine choices. Do not list architecture terminology or invent requirements for the user. Propose a design when one is missing instead of turning all design work into a questionnaire. For tradeoffs that require the user's decision, first provide concrete, assessable options. While waiting for confirmation, continue investigation and authorized work that is genuinely independent of that decision; do not implement the dependent parts prematurely.

Use a small end-to-end workflow to test the design before building a large framework whose real behavior has not yet worked. Do not force an additional prototype when requirements and discussion are already sufficient.

For projects intended for real deployment, establish the target runtime environment, core user workflows, real dependencies, and release acceptance criteria during design, then verify them throughout implementation. Reuse existing deployment plans. Discuss unresolved important conditions that affect implementation. A stage may have limited scope, but do not downgrade delivery to a demo or replace necessary real integrations with mocks without agreement.

Record confirmed designs and key tradeoffs that need to survive across sessions in an appropriate existing project location, following [Documentation maintenance](documentation.md). Clearly label unimplemented proposals and update current architecture documentation after implementation. Do not create design archives for simple scripts or every exploratory idea.
