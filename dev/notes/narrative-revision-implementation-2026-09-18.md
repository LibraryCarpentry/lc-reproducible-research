# Narrative revision implementation

Implements `dev/notes/claude-narrative-revision-prompt-2026-09-18.md`, informed by `dev/notes/narrative-review-2026-09-18.md` and building on the corrections already applied from `dev/notes/validation-review-2026-09-18.md` (preserved, not reopened). No commit, push, PR, or lifecycle change made - working tree only.

## Episode structure (6 episodes, was 5)

1. Introduction (unchanged file, edited)
2. **Understanding Reproducibility** (new - first half of the old "What is Reproducible Research?")
3. **Making Research Checkable** (new - second half of the same split)
4. Benefits and Challenges (unchanged file, edited)
5. Tools for Reproducible Research Workflows (unchanged file, restructured)
6. The Role of Libraries in Supporting Reproducibility (unchanged file, edited)

### Why the split

`reproducible-research-overview.md` was evaluated against the prompt's two-part candidate (definitions/classification/quant-qual vs. openness/case/construction) before editing. The seams already existed in the episode's own headers, the three lesson objectives split cleanly 2/1 across the halves with no duplication, and the combined episode was the longest in the lesson (~52 min required-core, ~60 min with both then-required activities that are now optional). The split also let the reproducibility-crisis discussion become genuinely optional background instead of required content, which the narrative review didn't propose but the revision prompt explicitly invited ("consider making the crisis discussion optional"). `narrative-review-2026-09-18.md` itself recommended keeping five episodes and only reframing - that recommendation didn't evaluate chunking, so it isn't in tension with this decision so much as silent on the question the revision prompt asked me to evaluate.

## The concrete librarian takeaway

Made explicit for the first time as a throughline: *help a researcher identify what another person would need to follow the work, recognize what's missing, and agree on a useful next action or referral.* Stated in the Introduction's audience paragraph, carried as a bridge question from Making Research Checkable into Benefits and Challenges, and closed with a structured three-line note (what's known / what's missing / next action and who's responsible) in the Library Role exercise - the same shape the narrative review proposed.

A new Mermaid flowchart (natively supported by the installed varnish 1.0.9 theme - confirmed via its bundled `mermaid.js`, which targets `pre.mermaid`/`pre>code.language-mermaid`, and verified in the built HTML output) depicts that consultation flow. It appears twice only: briefly in the Introduction, and returned to at the conclusion of the Library Role episode, each time with a plain-text ordered-list equivalent for accessibility and non-Mermaid renderers.

## What was adapted from the assigned reading

Per the prompt's scope limits (concepts only, not the CuRe curriculum's taxonomy or execution/certification workflows):

- **Documentation Review** (`lc-curation-workflows`) motivated replacing the Tools episode's README-template-completion exercise with a short review of an intentionally incomplete fictional hand-off note, asking learners to identify two missing details and explain why each matters - adapted specifically for Cool Access LA, not imported wholesale.
- **Output Review** (`lc-reproducibility-assessment`) motivated the "which figure or table should this match" framing inside that same new exercise.
- The Turing Way's **research compendia** framing ("project materials" as a connected whole) motivated the Tools episode's reorganization around three verification questions (understand the materials / repeat the steps / trace the findings) instead of a stage-by-stage tool catalogue followed by all the practice.

Both curation-sequence sites carry pre-alpha notices; they're credited as conceptual sources in this note and in the episode's own tool links, not treated as a validated course.

## Timing

- Introduction: 15→17 min teaching (added diagram/framing content, no new exercise time)
- Understanding Reproducibility: 14 teaching + 12 exercises declared (10 min required exercise, 8 min more if both optional activities run)
- Making Research Checkable: 10 teaching + 10 exercises declared (9 min required exercise, 10 min more if the now-optional crisis discussion runs)
- Benefits and Challenges: unchanged (10 + 10)
- Tools: unchanged teaching (30); exercises 24→22 (six-minute README exercise replaced by a four-minute one; net -2)
- Library Role: unchanged (15 + 8)

Combined required-core time for the two split episodes is ~43 min, down from ~52 min in the single combined episode - entirely from moving the crisis discussion to optional. Total time across the two, with every optional activity run, is essentially unchanged (~61 vs ~60 min before). These remain **unpiloted planning estimates**, same caveat as the existing front matter throughout the lesson.

## Validation results (real, run this session)

- `carpentries-workbench-checker`: 0 errors, 0 warnings, 2 notes (pre-existing contraction-count style notes in introduction.md and library-repro-role.md, unrelated to this revision)
- `sandpaper::validate_lesson()`: clean, no output
- `sandpaper::build_lesson()`: clean build (only pre-existing pandoc `--mathml` deprecation warnings, unrelated to lesson content)
- Inspected built HTML: episode order and numbering correct (1 Introduction through 6 Library Role); the Mermaid diagram renders as `<pre class="mermaid"><code>...` in `introduction.html` and `library-repro-role.html` (confirming it will render as an actual diagram via varnish's bundled mermaid.js, not raw fenced-code text); the one place the literal ` ```mermaid` ` string appears as text (instructor-notes.html) is intentional - it's describing the syntax in an inline code span, not a live block

## Cross-references updated

All explicit episode-number references (introduction.md x3, learners/reference.md x1, instructor-notes.md pacing table + Cool Access LA section) renumbered for the 6-episode structure. Relative references ("the previous episode," "the previous two episodes") were checked and left alone - they remain accurate under the new numbering without editing, since Cool Access LA's introduction moved to the episode immediately preceding Benefits and Challenges, same as before.

## Remaining pilot questions (unchanged from the prior review)

- The lesson still has no observed teaching data confirming any timing (old or new) - only the June 2026 UMass pilot ran a full session, against the pre-revision episode.
- Whether workshop organizers already have a next-pilot feedback plan (observer roles, debrief structure) hasn't been confirmed one way or the other - not claimed to exist, not authored preemptively.
- The split adds one more episode to schedule; if the next pilot is time-boxed to a fixed number of sessions, confirm the 6-episode structure still fits before advertising it.

This is a bounded revision to a design that was already assessed as solid (8/10) before this pass, not a rewrite. **Do not treat any timing here as pilot-confirmed, and do not call the lesson stable** - both remain open until an outside-instructor pilot runs against this structure.
