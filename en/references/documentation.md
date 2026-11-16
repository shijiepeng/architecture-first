# Project Documentation Maintenance

Read this only when an important decision needs recording, a change invalidates existing guidance, stage acceptance evidence needs preserving, or the user asks to organize documentation. First inspect the purpose and existing conventions of relevant documents, then reuse the appropriate locations. “Create fewer files” does not mean putting everything in the README. Small changes without documentation impact do not require new documents or work logs.

## Organize Content by Purpose

- **README**: help newcomers understand the purpose, quick start, common commands, and documentation entrypoints. A brief architecture overview and key usage limitations may remain here. Move growing architecture detail, change plans, daily progress, and test logs to appropriate documents and link to them.
- **Current architecture**: maintain currently applicable responsibilities, dependencies, data flows, key decisions, and existing limitations. Update the relevant content in place after implementation changes. Readers should not have to combine multiple days of records to infer the current state.
- **Plans and decision history**: record reasoning, tradeoffs, and status when they have lasting value. Distinguish proposed, confirmed but not implemented, implemented, and superseded decisions. Reflect implemented plans in current documentation. Reuse existing task or decision records instead of creating a new set of files for every change.
- **Stage review and acceptance records**: tie records to a version, scope, environment, and evidence; track issue closure or deferral. Reference existing reviews, CI results, and test reports instead of copying their entire output. Subsequent verification should identify its new version and result. Do not rewrite historical failures as if they had already passed at the time.
- **Usage, interface, testing, and deployment guidance**: include actual steps, prerequisites, and limitations, and update them when behavior changes. Short guidance can remain in an existing file; split it out when it grows and has an independent use. Temporary paths, elapsed times, or troubleshooting details from a single run do not automatically belong in long-term operating instructions.

These are content responsibilities, not a mandatory list of directories or files. A small project may need only a README. Split documents only when content is already mixed, readers have different needs, or maintenance frequency differs significantly. Respect existing naming and organization. Do not set fixed line limits or pre-create empty documents or sets of GOALS, PLANS, ROADMAP, and logs.

## Updating and Organizing

Choose one primary maintenance location for each fact. Elsewhere, use necessary summaries and links instead of copying entire passages that are then updated independently. When moving content, update README entrypoints and affected links. Do not retain two independently evolving full copies.

Update resolved issues in current guidance promptly. Preserve valuable old baselines, decision rationales, and review evidence in historical records, identifying which version or decision superseded them. Do not describe proposed designs as implemented structures, or leave the body stale while only appending a “latest update” at the end.

Preserve still-valid constraints, unresolved matters, and acceptance evidence when organizing documentation; do not silently remove them for brevity. Handle only documents relevant to this task instead of reorganizing the whole documentation system during a local change. A read-only review still only proposes recommendations; do not move files without authorization.

Afterward, check affected entrypoints and local links, confirm that current guidance matches the implementation, verify that plan status is clear, and ensure historical evidence remains locatable. Claims that “tests passed” require corresponding evidence. Moving old records is not rerunning tests.
