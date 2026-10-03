# Practices follow-up implementation

Implements `dev/notes/claude-practices-followup-prompt-2026-09-18.md`, a bounded correction pass on `dev/notes/practices-followup-review-2026-09-18.md`'s four findings plus its small seams. Builds on the same-day practices-revision working tree (`dev/notes/practices-revision-implementation-2026-09-18.md`). Six episodes, unchanged order and case, no structure change. No commit, push, PR, or lifecycle change.

## Files edited

`episodes/making-research-checkable.md`, `episodes/repro-tools.md`, `episodes/introduction.md`, `episodes/library-repro-role.md`, `instructors/instructor-notes.md`, `index.md` (one objective clause, for alignment).

## Findings verified and fixed

Each finding was checked against the current file content before editing (line numbers in the review had drifted slightly from intervening edits, but the substance matched in every case):

1. **Qualitative example now shows the actual excerpt and analytic note** (`making-research-checkable.md`), not just a claim that they exist. The plural claim ("several residents") is deliberately kept against a single shown excerpt - the exercise now asks learners to notice that specific mismatch and name what closes it (more excerpts, or a narrower claim), rather than accept a coding scheme as sufficient on its own. The solution no longer implies consistency is a universal qualitative requirement.
2. **The final assessment now requires a concrete check, its performer, and its limit** (`library-repro-role.md`), not just a service choice. The first scenario's solution now specifies: an authorized team member traces one report claim through its excerpt and analytic note, and what that would and wouldn't establish. The second scenario is now explicitly framed as an *alternative* to the first (either/or, not both), preserving the 4-minute budget while letting its solution add the same specificity (a lockfile-vs-installed comparison, explicitly not a reproduced result). Both episode objectives and `index.md`'s matching objective were reworded.
3. **Both Mermaid diagrams no longer gate every check behind full traceability.** Redesigned flow: identify materials → plan a *scoped* check → attempt it → record the outcome, whether blocked by a gap (with a specific improvement and owner recommended) or completed (with a match, discrepancy, or partial result - not just success). Both branches converge on "agree the next action," so an unresolved gap still ends productively. Text equivalents in both episodes were rewritten to match exactly.
4. **Source list added, revision-history prose removed, and the description placeholder investigated.** See below for each part.

## The description-placeholder investigation (finding 4, part 3)

The review asked to "populate the actual Workbench/theme-supported accessible description" and to verify the mechanism before choosing syntax, since it had not independently reproduced the placeholder in a browser. This pass did the verification directly:

- Added Mermaid's standard `accTitle:`/`accDescr:` directives to both diagrams (Mermaid v11.12.1 is bundled in the installed varnish 1.0.9, confirmed to support this syntax).
- Rebuilt the site and, in Chrome via claude-in-chrome, inspected the rendered SVG's DOM directly (not just the markdown source or the presence of bundled JS). Confirmed: the SVG's `aria-labelledby`/`aria-describedby` attributes now point to a `<title>` and `<desc>` element inside the SVG, populated with our text - the standards-compliant mechanism screen readers use for an image's accessible name and description. Verified in both occurrences (`introduction.html` and `library-repro-role.html`).
- The visually similar "Please enter an accessible description" prompt the previous review saw is a **separate** element: a `<figcaption>` inside a client-side-injected `<figure class="mermaid-img-wrapper">`. Comparing the pre-JS static HTML (`site/docs/introduction.html` source: a bare `<pre class="mermaid"><code>...`) against the post-render DOM confirmed this figure/figcaption wrapper doesn't exist until a bundled script builds it, and nothing in the page source offers a Markdown-level hook to set its text. It appears to be an unrelated viewer feature (plausibly pan/zoom or a live-annotation affordance) bundled with this varnish version, not a configurable caption for the diagram.

**Conclusion, precisely stated**: the diagram's actual accessible name/description (the thing that matters for assistive technology) is fixed and verified. The visible "enter a description" text is a distinct UI element this pass could not resolve from lesson Markdown, because no such mechanism appears to exist in the current theme. This is reported as a real, verified limitation - not claimed as fixed, and not left unexplained.

## Small seams fixed

- `repro-tools.md`'s two "the previous episode" references to the project packet now name "Making Research Checkable" explicitly, with a working `.md`-style cross-episode link (validated by `sandpaper::validate_lesson()`'s internal-link check).
- `repro-tools.md`'s quantitative/qualitative section intros now match their actual content (the qualitative section also covers reporting tools used by both kinds of work).
- `introduction.md`: "makes it open but not reproducible" → "makes it open, but its lack of documentation does not establish that it's reproducible" (matches the more careful phrasing already used in that episode's own challenge solution).
- `repro-tools.md`: the coding-and-annotation tool description no longer implies the software itself makes analysis auditable; qualified to require the excerpts, applied codes, and analytic notes being kept together and reviewable.
- `making-research-checkable.md`'s opening question list now includes a question matching its evidence-mapping objective.

## Correcting a prior implementation-note error

`practices-revision-implementation-2026-09-18.md` (from the previous pass) claimed the Social Science Data Editors' README was "already linked... reused as further guidance." That was inaccurate - a search this pass confirmed only the Cornell template is linked anywhere in learner-facing text; the SSDE resource was read during the source scan but never actually linked. That prior note is left as-is (a historical record of what was believed at the time, not retroactively rewritten), and this note records the correction: the SSDE README template is now listed, correctly, in the new instructor reading list below (linked, not copied - it's CC BY-NC and this lesson is CC BY) rather than claimed as already present in learner text.

## Instructor reading list (new)

Added a compact, annotated "Instructor reading list" section to `instructors/instructor-notes.md`: TOP 2025 (disclosure vs. verification), The Turing Way's research compendia (the packet's conceptual source), UKRN primers (qualitative open-research practices), the Social Science Data Editors' README template (an alternative to Cornell's, for instructor reference), and RT2 2026 as an optional deeper pathway. This replaces the earlier gap where these sources existed only in `dev/notes/reproducibility-resources-2026-09-18.md`, which instructors teaching from the built site would never see.

## Revision-history cleanup

Removed from `instructors/instructor-notes.md`: narration of what an "earlier draft" or "a later review" found and changed (Role of Libraries section), the session-specific "verified by rendering the built site locally... this session" language (consultation-flow diagram section), and the "replaced the previous, shorter exercise" / "was removed as redundant" framing throughout the Tools section. All of that is preserved in this file and the prior implementation notes under `dev/notes/`, which is where it belongs - the public instructor page now states only what's true about teaching the *current* lesson.

## Timing

No exercise durations changed this pass - all four findings and five seams were content/framing fixes within existing time slots (the library-role scenario is now explicitly either/or rather than implicitly both, if anything reducing realistic in-room time). Declared core remains **167 min**, optional adds **18 min**, full lesson with all optional content **185 min**, matching the follow-up review's own reconciliation. All estimates remain unpiloted.

## Validation results (run this session)

- `carpentries-workbench-checker`: 0 errors, 0 warnings, 4 notes (all pre-existing contraction-count style notes, one new only because `making-research-checkable.md` now has more prose - not a defect)
- `sandpaper::validate_lesson()`: clean, no output (this run, not carried over from the follow-up review's own run, which the review reported separately)
- `sandpaper::build_lesson()`: clean build (only pre-existing pandoc `--mathml` deprecation warnings)
- **Browser-verified this session**: the new diagram branch structure renders correctly (both branches visible, converging on "Agree the next action") in both `introduction.html` and `library-repro-role.html`; the internal cross-episode link resolves to `making-research-checkable.html` correctly; the `accTitle`/`accDescr` fix was verified by direct DOM inspection of the rendered SVG (not just markup presence), as described above.

## Remaining pilot questions

- Everything touched across all three of today's passes (validation review, narrative revision, practices revision, this follow-up) is unpiloted. No teaching data confirms any timing, exercise design, or misconception label.
- The client-side "Please enter an accessible description" figcaption remains unresolved from lesson Markdown - flagged for a future pass to investigate at the varnish/theme level (not a lesson-content problem, but worth an upstream question or issue if it matters for the actual pilot audience's assistive-tech needs).
- Before a beta pilot: this is now four same-day passes on one working tree. A start-to-finish read of the built site (not the diffs) is still the right next step before teaching, per the same recommendation in the prior implementation note - now more overdue, not less.
- Per the follow-up review's own closing recommendation: the next substantive evaluation should be a timed pilot, not another redesign pass. This implementation agrees and made no structural changes.
