# Review and revision plan: practices librarians can support

Reviewed 2026-09-18 against the current uncommitted six-episode lesson, including the new episode files, instructor notes, landing page, and narrative implementation note. This supersedes earlier structural suggestions where noted. It is a source-content and pedagogical review; I did not rerun the build or observe a browser rendering in this pass.

## Recommendation

Keep the six episodes and the revised Tools organization. Make a bounded revision that gives learners practice connecting materials, decisions, and findings, then choosing and explaining a concrete improvement. The latest changes provide a useful consultation process, but the substantive practices within that process still need to be clearer.

## What to retain

- The Overview split creates two manageable units: definitions and methodological differences, followed by openness and Cool Access LA. Do not revisit the split merely because we have new resources.
- Tools now interleaves examples and exercises under understand materials / repeat steps / trace findings. This is a stronger teaching sequence than the earlier catalogue.
- The incomplete README provides an actual artifact to inspect. The missing-value and Git exercises give learners specific problems to reason about.
- The closing note asks for something usable: known information, missing information, and an action with an owner.
- Keep the corrected coin example, explicit Git assumptions, restricted-data boundaries, novice prerequisites, optional crisis discussion, and light use of the fictional case.

## Findings and suggested changes

### 1. The library-role framing excludes capable practitioners

`episodes/library-repro-role.md:34` explicitly says the researcher's team, "not the librarian," reruns work. Lines 71 and 93 characterize technical advising as usually a stretch and confine the library's usual contribution to identifying and clarifying materials. These claims are broader than the evidence provided and conflict with the Introduction's allowance for a skilled librarian to carry out a check.

Replace role restrictions with task-specific scope: librarians may teach, implement, collaborate, or assess according to skills, authorized access, service commitments, and capacity. Give one concrete direct technical contribution, such as comparing committed script versions or helping restore a documented environment, alongside documentation and qualitative support. Retain the pilot's concern that no individual librarian must provide every service. Do not turn the lesson into mandatory code execution.

### 2. Making Research Checkable still mostly tests classification

`episodes/making-research-checkable.md` has one objective about constructing openness examples. Both challenges largely repeat classification work already done in Episodes 1 and 2. The title promises a practical question that is deferred until Tools.

Retain one explicit openness/reproducibility assessment. Replace the other activity with a brief evidence-mapping task: connect one named survey figure to its inputs and steps, and connect one interview claim to its approved source material and analytic explanation. Introduce a tiny project packet here and reuse it in Tools. Update the episode objective and keypoints to match. Do not add a third exercise.

### 3. Practice is still assessed mainly through tool selection

`episodes/repro-tools.md:85` asks for missing details, but stops before choosing a repair or describing how someone would assess its adequacy. The exit check at line 181 still emphasizes naming four tools. The current three section headings should remain; the six practices in the resource note are a design aid, not six additional learner sections to memorize.

Extend the existing packet task from "what is missing?" to "what would you change, and what would that enable someone to check?" Use a supplied fact or an explicit placeholder, never invent an unknown version. Replace the redundant two-minute codebook-choice activity if time is needed. Replace the exit recall task with one short transfer response identifying a gap, a practice/artifact, and a check or limit. Update the tools-list objective deliberately so the new assessment stays aligned.

### 4. The diagrams and prose make the methods divide too rigid

`episodes/repro-tools.md:148` and the Mermaid diagrams associate quantitative work with rerunning and qualitative work with tracing. Both kinds of work need provenance and traceable reasoning; qualitative projects may also contain computational steps. A rerun checks a specific computational result, not every aspect of quantitative validity.

Keep the accessible examples but describe possible checks by task, with computational rerun and evidence/interpretation tracing as examples that can coexist. Distinguish planning a check, making an improvement, and reporting a check actually performed. Revise the diagram to include choosing an improvement and its responsible person, then identifying an appropriate check; avoid implying that reading documentation establishes reproducibility.

### 5. Several answer keys and instructor claims exceed the evidence

- `episodes/making-research-checkable.md:73` again says no one, including the author, could redo an undocumented analysis. Say that the supplied package does not establish or adequately support reproduction.
- The Introduction says depositing raw data, code, and a README makes reproduction possible. Missing dependencies or incomplete instructions can still prevent it; qualify the example.
- The final scenario's answer asserts that documentation is missing, although the request only establishes that the researcher does not know how to write the statement. Inspect existing records first, or make the missing record explicit in the fictional prompt.
- Instructor notes call a README misconception "the most common" without evidence that the new exercise has been piloted. Label it an anticipated misconception.
- Open science is defined mainly as making outputs available. Briefly acknowledge its wider concern with participation, collaboration, and equitable access without adding a survey of the whole movement.

### 6. Timing and validation claims need reconciliation

Current front matter totals 166 minutes: 25 + 26 + 20 + 20 + 52 + 23. Named required activities plus teaching total 163: Episode 2 lists 10 exercise minutes against 12 declared; Episode 3 lists 9 against 10. Those differences could be intentional debrief time, but need labels. Optional activities add 18 minutes overall: 8 in Episode 2 and 10 in Episode 3. The instructor table incorrectly says the two Episode 2 options add 18 minutes. With the current front matter, the planned total including options is 184 minutes before breaks; using named core activities alone gives 181. Select one explicit accounting convention and recalculate after edits.

The implementation note reports successful checker/validate/build runs. It describes Mermaid markup and the bundled rendering script as proof of an actual diagram. Those establish integration, but do not by themselves demonstrate successful browser rendering. It also claims both diagram occurrences have an ordered-list equivalent; only the Introduction currently has that full list. Ask Claude to inspect the actual rendered diagrams and correct the accessibility or reporting mismatch. Do not declare rendering broken without observing a failure.

## Implementation sequence

1. Preserve the current structure and document a short objective-to-assessment map before editing.
2. State the practices-based promise in the landing page and Introduction. Keep roughly three lesson outcomes, revising wording only where the actual assessment changes.
3. Create one compact, fictional packet within existing episode Markdown: a named output, short file/relationship information, the current codebook entry, and a small interview evidence example. Introduce the relationships in Episode 3; inspect and improve them in Episode 5. Do not create a dataset or runnable software project.
4. Revise Tools assessments and the closing library-action note to require an improvement and an appropriate check or acknowledged limit. Preserve the Git and qualitative examples.
5. Correct practitioner framing, overclaims, and diagrams. Update instructor answers, anticipated misconceptions, timings, and source attribution.
6. Run the existing checker and sandpaper validation/build, then inspect rendered navigation, activities, solutions, and diagrams. Record exact results and remaining pilot questions.

## Resource use and scope

Use `reproducibility-resources-2026-09-18.md` for the full source map. TOP 2025 informs availability versus verification; The Turing Way informs connected project materials; UKRN and QDR inform methodological breadth; the Social Science Data Editors' README informs questions about inputs and execution. Link to that README rather than copying its CC BY-NC text into this CC BY lesson. RT2 2026 and ACRe are instructor/deeper-learning pathways. Keep preregistration, PRISMA-S, AI, robustness analysis, and formal curation certification outside the required core.

The six cross-cutting practices are documentation of methods/decisions; provenance/meaning; versions/dependencies; evidence-to-finding connections; responsible access; and scoped checking. They should clarify the existing three Tools questions, not become a competing taxonomy or a new episode sequence.

## Acceptance criteria

- Learners can identify a missing connection, recommend a specific improvement, explain what it permits someone to check, and identify an appropriate practitioner or collaborator.
- A novice can complete the required activities using the page and a browser, without coding or guessing project facts.
- At least one assessment distinguishes supplied documentation, a proposed check, and evidence from a completed check.
- Technical library contributions are legitimate options, with no universal obligation to provide them.
- Six episodes and the established tool list remain; activities are replaced rather than accumulated. Aim to stay within the current 166-minute declared core, labeling any necessary change honestly.
- Timing, objectives, expected answers, links, diagrams, and implementation claims agree with the actual result. Estimates remain unpiloted.
