# Execute a focused revision of the reproducible research lesson

Work in `/Users/timdennis/projects/lessons/content/lc-reproducible-research`.

Revise the lesson so librarians leave with concrete practices for helping researchers connect materials, methods, decisions, and findings. Read the recent changes first and build on them. Implement the bounded plan below and leave a reviewable local diff.

## Read before editing

Read applicable project instructions and inspect git status and the complete current lesson, including untracked episode files. There are substantial existing edits from a recent narrative revision. Preserve them. The lesson now has six episodes; the old combined overview has been replaced.

Read these files in order:

1. `dev/notes/narrative-revision-implementation-2026-09-18.md`
2. `dev/notes/reproducibility-resources-2026-09-18.md`
3. `dev/notes/practices-revision-plan-2026-09-18.md`
4. `dev/notes/HANDOFF.md`

The practices revision plan reflects a review of the current six-episode working tree. Earlier review documents are background; do not rerun the earlier prompt or restore the old structure. Verify each finding against the current file before changing it, because other edits may have occurred.

Name the exact files you intend to edit and proceed. Expected scope: `index.md`, the six current episode files, `instructors/instructor-notes.md`, and `learners/reference.md` only where new or corrected terminology requires it. Update development notes and the handoff under `dev/notes/`. Preserve the episode order in `config.yaml`; no structure change is needed. Do not commit, push, open a PR, or change lifecycle status.

## Intended learning outcome

Given a research workflow, a learner can identify what someone would need to follow or check it, recommend a concrete improvement, and explain who could carry it out and assess it.

Use these practices to guide the revision: documenting methods and decisions; preserving provenance and meaning; managing versions and dependencies; connecting evidence to findings; enabling responsible access; and performing or describing scoped checks. Integrate them into the current three Tools questions: understand materials, repeat analysis steps, trace findings. Do not add six new sections or ask learners to memorize a second framework.

Librarians can teach, implement, collaborate, and assess according to their expertise, authorized access, and service capacity. Keep the pilot's warning that no librarian must do everything. Remove categorical exclusions such as "not the librarian" and unsupported claims that the library usually only identifies and clarifies materials. Include a credible technical contribution as well as documentation and qualitative contributions, without requiring learners to run code.

## Implement

1. Keep all six episodes, the light Cool Access LA case, the existing tool inventory, and the no-programming prerequisites. Preserve the coin example, Git's explicit starting assumptions, and the optional crisis discussion. Do not expand into a full RT2, archive curation, AI, evidence-synthesis, or statistics curriculum.

2. Tighten the Introduction and landing page around the learning outcome above. Distinguish making work checkable from successfully completing a check. Explain briefly that reproducibility sits within a broader open-science context, without turning this into a new open-science survey. Adjust the existing three lesson outcomes only as needed for alignment.

3. In Making Research Checkable, retain one clear openness/reproducibility assessment and replace the other repetitive classification/construction exercise with a short evidence-mapping task. Introduce a small fictional packet in Markdown: one named survey output, its supporting file relationships, and a qualitative claim with an approved source excerpt or analytic-note fragment. Reuse the existing survey codebook entry. Make the packet internally coherent and explicitly fictional. Do not add real participant data, invent facts about the cited UCLA studies, or require file downloads or software execution.

4. Reuse the packet in Tools. Extend the incomplete-README activity so learners identify a missing connection and propose a precise improvement, then explain what check the improvement would enable. They can request missing facts or write explicit placeholders; they must not invent an unknown dataset version or software requirement. If extra time is needed, replace the redundant codebook-choice activity. Preserve the missing-value consequence and committed-script comparison exercises.

5. Replace the "Name four" exit check with a concise transfer task: identify a gap, choose a practice/artifact, and describe a check or limitation. Update the episode objective that currently requires listing four tools, and show where all retained objectives are assessed. Tool names should still appear as useful examples, but recall of product names is not the main accomplishment.

6. Strengthen the closing library-action note. Require a specific contribution and how someone would know it helped, with ownership appropriate to local expertise. Keep documentation review, direct technical work, and collaboration as valid options. Do not assume documentation is absent merely because a researcher asks for help with a statement; inspect what exists, or explicitly supply the gap in the fictional request. Preserve the access boundaries for interview recordings.

7. Revise the Mermaid consultation flow and its prose. Both quantitative and qualitative work require traceable evidence; a computational rerun is one type of check and can occur in either kind of project. Show the route from a question or output through supporting materials, a gap and improvement where needed, an appropriate check, and an agreed next action. Keep planning distinct from completed verification. Avoid implying that every project follows identical sequential steps or that a rerun proves scientific validity. Keep the diagrams limited to the existing introduction/conclusion locations, with consistent accessible text equivalents.

8. Fix the bounded overclaims identified in the review: undocumented materials do not establish reproducibility, but this does not prove nobody could rerun the work; depositing three named artifacts is not by itself sufficient; qualitative software alone does not establish traceable reasoning. Label new activity misconceptions as anticipated, not observed. Avoid treating restricted access as automatic impossibility or de-identification as automatic permission.

## Sources

Read relevant sections before adapting. Use citations close to the claims they support and keep most deeper pathways in instructor notes:

- TOP 2025: https://www.cos.io/initiatives/top-guidelines
- The Turing Way, research compendia: https://book.the-turing-way.org/reproducible-research/compendia/
- UKRN primers: https://www.ukrn.org/primers/
- UKRN qualitative resource announcement: https://www.ukrn.org/2025/01/17/new-resources-empower-qualitative-researchers-to-embrace-open-research-practices/
- QDR ATI preparation guidance: https://qdr.syr.edu/node/20665
- Social Science Data Editors README: https://social-science-data-editors.github.io/template_README/
- BITSS RT2 2026 program/materials: https://www.bitss.org/events/research-transparency-and-reproducibility-training-rt2-2026/
- ACRe scoping and assessment: https://bitss.github.io/ACRE/intro.html

The README template is labeled CC BY-NC. Link to it and write original teaching examples; do not copy its text into this CC BY lesson. Do not describe older sources as newly published or claim to have reviewed a slide deck when only its listing was read. Keep TOP's policy/certification framework as instructor context, not a new assessment obligation for novice librarians.

## Timing and validation

Before editing, make a compact outcome/activity map. After editing, reconcile front matter, named activity times, debrief allowances, optional activities, and total duration. The reviewed baseline declares 166 minutes core; explicit activity sums currently give 163 because three minutes are unallocated across Episodes 2 and 3. Optional activities add 18 minutes overall, not 18 in Episode 2 alone. Aim to preserve the current core budget by replacing repetitive work; report any necessary increase honestly. All revised timings remain unpiloted estimates.

Use the repository's existing checker and R/sandpaper setup, discovered from local instructions or configuration. Run the lesson checker, `sandpaper::validate_lesson()`, and the normal build. Inspect rendered episode order, challenge/solution structure, links and diagrams. Mermaid source markup plus a bundled script does not prove a diagram displayed successfully: inspect it in a browser. If browser verification is unavailable, record that exact limitation rather than claiming it passed. Ensure both diagram occurrences have a usable text equivalent or a clearly accessible route to it.

Check the final lesson against the acceptance criteria in the revision plan. Record an outcome-to-assessment map, before/after timing, source adaptations, exact validation results, and remaining pilot questions in `dev/notes/practices-revision-implementation-2026-09-18.md`. Update `dev/notes/HANDOFF.md` without replacing unrelated context or rewriting historical reviews as if their tests were newly run.

Finish with a concise account of what learners can now do, which existing activities were replaced, timing changes, files changed, and any validation limits. Leave all changes local for review.
