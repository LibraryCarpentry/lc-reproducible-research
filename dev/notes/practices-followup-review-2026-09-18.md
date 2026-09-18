# Follow-up review of the practices revision

Reviewed the current uncommitted six-episode lesson on 2026-09-18, including its implementation report and instructor notes. No lesson sources changed in this review.

## Judgment

The revision substantially addresses the earlier concern. The lesson now has a coherent practical direction: identify supporting materials, find a gap, propose an improvement, and identify an appropriate check and practitioner. Keep the six-episode structure, tool grouping, README exercise, transfer question, and expanded library-role framing. A short correction pass is warranted before piloting; another structural rewrite is not.

## Findings to resolve

### 1. Repair the qualitative evidence example and answer key

Location: `episodes/making-research-checkable.md:69` and `:85`.

The packet says an excerpt and analytic note exist, but supplies neither. Its claim concerns several residents using library air conditioning, while the single named excerpt is said to have been coded as an access barrier. Learners cannot inspect that relationship, and the text does not explain how one excerpt supports a plural claim or why cooling use indicates a barrier.

The answer then says a coding scheme lets someone determine whether a label was applied consistently. A scheme supplies criteria; assessing application across material also requires relevant excerpts, applied codes, and decision records. Consistency is also not a universal quality criterion for every qualitative approach. This answer introduces that methodological assumption without defining the approach.

Recommended repair: show a very short, explicitly fictional approved excerpt and matching analytic-note fragment. Use a claim about one participant, or deliberately retain the plural claim and ask what additional evidence it needs. Accept requests for the source passage, context, claim coverage, and analytic explanation as well as an applicable coding scheme. Say what each permits someone to inspect and what remains unknown. QDR's guidance treats source material and analytic explanation together: https://qdr.syr.edu/ati/ati-instructions

This can replace the current descriptive bullet and solution within the existing five-minute exercise. No larger dataset is needed.

### 2. Assess the final promised check, not only a service choice

Locations: `index.md` final objective; `episodes/library-repro-role.md:40` onward.

The landing page promises that learners can recommend a proportionate check and identify who can carry it out. The final exercise asks for known information, a missing item, and a next action/owner. Its solution stops at organizing documentation. The second scenario asks which service or partner to use. Learners can answer both successfully without specifying what anyone would check or what evidence would show that the improvement helped.

Retain the three-line note, but require a concrete check and its limit in the final line alongside an owner. For example, an authorized colleague traces one report claim through an approved excerpt and analytic note, recording where the explanation is incomplete. Another acceptable answer could compare recorded package requirements with the installed environment while explicitly stating that no result has yet been reproduced. Update the solution and local objective. If two scenarios plus the note do not fit four minutes, use the second scenario as an alternative rather than silently increasing the workload.

### 3. Remove an unnecessary full-traceability gate in the diagram

Locations: `episodes/introduction.md:76` onward and the corresponding flow in `episodes/library-repro-role.md`.

The diagram requires the connection to be traceable end to end before planning any check. But a documentation review, version comparison, or limited execution attempt can itself discover a missing connection. The gap branch loops until it is repaired and supplies no clear route for an unresolved access or resource limit. The caption also says a completed check establishes that work can be followed and assessed; an attempted check can instead show that it cannot yet be followed.

Use "enough information and access for the proposed check?" or otherwise allow a scoped check with recorded limits. Permit an actionable stopping point when a gap cannot be closed. Record the observed outcome, including failure or inability to proceed; do not imply that completion means success. Preserve the distinctions between a proposed check and a completed one, and between a successful rerun and scientific validity. Keep both diagrams and text equivalents synchronized.

### 4. Finish the source and instructor handoff

The implementation report says the Social Science Data Editors' README is already linked. A search of learner/instructor source finds only the Cornell README link. The research note contains the newer resources, but instructors will not encounter development notes through the lesson site. The main request to draw on current resources is therefore only partly delivered.

Add a short instructor reading list with purpose-specific annotations for TOP 2025, The Turing Way compendia, and QDR or UKRN's qualitative guidance; RT2 2026 can be one optional deeper-learning link. Keep Cornell's useful template. Either add the intended Social Science Data Editors link as further guidance or correct the implementation report to say it was consulted, not linked. Do not copy CC BY-NC template text.

Move session-specific browser results, revision history, and unresolved implementation commentary out of public instructor notes and into development notes. The instructor page should explain how to teach the current lesson, not recount successive agent passes. This is a bounded cleanup, not a general rewrite.

The implementation report acknowledges a visible "Please enter an accessible description" prompt under both Mermaid diagrams. Complete the theme-supported description rather than leave an authoring placeholder in the published lesson. Keep the existing text alternatives as well. I have not independently reproduced the browser appearance; this finding is based on the implementation report and should be checked during the correction pass.

## Small seams to fix in the same pass

- Tools twice calls the project packet part of "the previous episode" (`:67`, `:93`). It is in Making Research Checkable, two episodes earlier. Use the episode title and a working link.
- Tools says one section covers quantitative analysis and the next qualitative analysis, even though the latter now discusses evidence tracing across methods. Make those introductions match the revised section contents.
- The Introduction still equates an undocumented public dataset with "not reproducible." Use "does not establish reproducibility" to match its own more careful solution.
- A coding tool does not automatically make reasoning auditable. Qualify the Tools description by requiring recorded links, coding decisions, and analytic explanations.
- Update Making Research Checkable's opening question to include its new evidence-mapping objective.

## Verification and scope

I reread all six episode sources and reviewed the landing page, instructor notes, source links, and implementation report. `git diff --check` passed. A fresh `Rscript -e 'sandpaper::validate_lesson()'` completed successfully with only two locale warnings about `LC_ALL=C.UTF-8`; fenced-div and internal-link/image validation ran. I did not rerun the full build or browser checks. The separate checker executable was not on the current PATH; the preceding implementation report records its successful run.

The current timing arithmetic is coherent: 167 minutes declared core, including Episode 2's labeled two-minute buffer; 18 optional minutes gives 185 before breaks. These are still planning estimates. The main pacing question is now empirical, especially the multi-part six-minute README exercise and four-minute final service exercise.

After this correction pass, prioritize a timed pilot over further conceptual expansion. Observe whether a novice can identify a specific missing connection, propose a useful improvement, and distinguish a proposed check from evidence of a completed check. Preserve unresolved learner responses as evidence for the next revision.
