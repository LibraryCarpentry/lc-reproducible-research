# Re-evaluation of Reproducible Research Workflows

Reviewed 2026-09-18 at commit `80ee155`, including the changes since `7f63027`. The working tree was clean when review began. Read all five episodes, landing page, setup, glossary, learner profiles, instructor notes and previous review/handoff. This is a pedagogical/content review, not a repeat of the already-reported successful mechanical checks. No lesson source or lifecycle setting was changed.

**Verdict: this now has the design of a solid introductory lesson for library staff. My editorial assessment is 8/10, up from 6/10.** It has a clear purpose, relevant practice, a coherent running case, and realistic service boundaries. I would make the bounded corrections below and then use it for a beta pilot with an instructor outside the development team. More wholesale redesign or additional tool coverage is unnecessary. Actual learning and runtime still need observation; the score is a judgment, not a measured outcome or certification.

## What is substantially improved

- `index.md:23–25` now promises three observable outcomes that the episodes largely deliver: distinguish concepts, select practices, and recommend services/referrals. The previous implication of tool-operation proficiency is gone.
- Introduction checks openness/reproducibility directly, rather than asking novices to distinguish terms before instruction.
- Overview asks learners to construct two versions of Cool Access LA, not merely recognize labels. Its qualitative section now explains traceability without requiring agreement in interpretation. The different-city answer allows replication and generalizability to overlap.
- Benefits/challenges now explicitly asks for four benefits, four challenges, and an integrity connection. All four objectives have a corresponding prompt.
- Tools now includes a concrete codebook entry, a missing-value consequence question, a version-control scenario, and a four-tool exit check. These are substantial improvements in application, not cosmetic additions.
- Library role explicitly tests both local help and referral, and removes the universal low-effort/high-effort ladder.
- The Open Data glossary contradiction is fixed. The glossary, no-installation setup, and new Deshawn learner profile support the intended novice audience.

## Assessment alignment now

| Episode | Coverage | Remaining concern |
|---|---|---|
| Introduction, two objectives | Both have relevant checks: openness comparison and funder/journal rationale. | The first solution claims more than the scenario establishes about impossibility of reproduction. |
| Overview, three objectives | Classification with reasoning, construction of examples, and quantitative/qualitative comparison cover all three. | Some classification answers assume an unchanged method that the prompt does not state. |
| Benefits/challenges, four objectives | Every objective now appears in the two discussion prompts. | Whole-group production of four answers can hide individual confusion. Use individual thinking before pooling answers. |
| Tools, three objectives | Stage sorting; tool-to-gap exit check; documentation and version-control scenarios cover them. | Git recovery needs an explicit existing version history; exercises exceed the allocated minutes. |
| Library role, two objectives | Service selection and reflection cover both; the added scenario tests referral. | The software-environment answer creates an unwarranted distinction from documentation. |

This is substantially aligned with [CLDT's formative-assessment guidance](https://carpentries.github.io/lesson-development-training/formative-assessment.html). It does not require a separate exercise per objective. The next improvement is to make answers diagnostically reliable and hear from more than the quickest volunteers. In Episode 3, reserve the first minute of each existing discussion for individual notes, then pair/share; this need not extend the time budget.

## Changes to make before the next teaching

### 1. The activity budgets still do not reconcile

**Locations:** Overview front matter and activities at lines 47, 88, 108, 128, 157, 177 and 213; Tools front matter and timed activities at lines 43, 109, 123, 137, 153, 159 and 168; instructor timing table at lines 9–15.

The timing increases were accompanied by additional activities, so the previous suggested totals no longer fit the final text.

| Episode | Declared exercise time | Current activity accounting |
|---|---:|---|
| Overview | 32 min | Explicit labels total 29: 5 + 5 + 5 + 4 + 10. The instructor table implies another approximately 3 for initial classification and 5 for the first case challenge: about **37 minutes**, making 60 with teaching. |
| Tools | 20 min | Explicit labels total **24**: 3 + 2 + 4 + 2 + 6 + 5 + 2. With 30 teaching minutes, this is **54 minutes**, not 50. |

**Fix:** For Overview, make the first classification and the broad “additional examples from disciplines” discussion optional, retaining the stronger later classification, methodological comparison, case and constructed examples. That leaves approximately 29 core exercise minutes within a 32-minute allocation, allowing a little transition time. For Tools, declare 24 exercise minutes/54 total if all current exercises remain required. Give every required activity one explicit allocation, including its debrief, and make the instructor table match.

The prohibition on cutting any challenges/discussions in `instructors/instructor-notes.md:17` is too broad. Name the optional redundant activities and identify the essential checks that must stay. All revised durations remain estimates. The current declared lesson total is 171 minutes before breaks; schedule the pilot with room for transitions and feedback rather than advertising exactly that runtime.

### 2. The learner-facing statistics callout undoes the simplification

**Location:** `episodes/reproducible-research-overview.md:82–84`; accompanying instructor notes at lines 23 and 27–29.

The arithmetic example is much easier for the target audience. But the next visible callout introduces t-tests, statistical significance, non-significance and an account of the previous drafting decision. The handoff calls this an instructor callout; the source actually uses `::: callout`, so it is learner-facing. A novice must now process the statistical discussion the revision was intended to remove.

**Fix:** Keep the rationale in the existing instructor notes, remove the visible callout, and remove the invitation to extend this novice lesson with a t-test. A single relevant learner-facing sentence would be: “Matching calculations show that the result can be reproduced; they do not by themselves show that the study's methods or conclusions are sound.” This also supplies a general principle currently made explicit mainly in the Git answer.

### 3. Some correct answers depend on unstated facts

**Locations:** `episodes/repro-tools.md:125–129`; `episodes/reproducible-research-overview.md:49–57`, `78`, and `93–99`.

- The Git scenario promises recovery of yesterday's script without saying it was committed before the edit. Starting version control now cannot reconstruct an unrecorded earlier state. **Fix:** “The team already uses Git and committed yesterday's working script. Today an edit changed a figure; the input data and software environment are unchanged.” Then compare the saved versions and rerun the earlier one. [Git's documentation](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository) explains that commits record selected snapshots.
- The initial classification answer supplies “same analysis method,” although the selected option only says “re-analyze data.” **Fix:** put “using the original analysis steps” in the answer option itself.
- The survey classification states the same questionnaire but not the same analysis. **Fix:** add “and analysis method.”
- The coin example switches to a new coin while claiming the same question. That can work for a study of a population of coins, but the initial example has not specified that population. **Fix:** collect 100 new tosses of the same coin under the same procedure. This changes only the data and gives novices a cleaner contrast with rerunning the original observations. Different-coin generalization is unnecessary here.

These are small edits with a meaningful payoff: careful learners should not be penalized for noticing information that an answer key assumes.

### 4. The environment-referral solution is overconfident

**Location:** `episodes/library-repro-role.md:51–55`.

“Cannot recreate the software setup” is a symptom. Missing installation instructions, missing versions, unavailable dependencies, or local machine restrictions could cause it. Saying it is “not a documentation” problem contradicts the lesson's own explanation that environment management records software requirements. Pairing version-control and environment advice also risks blurring their distinct purposes.

**Fix:** “Start by checking the setup instructions and recorded software versions. If rebuilding the environment needs expertise beyond the library, refer the researcher to research computing or an appropriate IT partner.” Keep renv/containers as possible partner-supported approaches, not a solution implied by the symptom alone.

This would teach a stronger librarian skill: clarify a request, identify missing information, then refer appropriately.

### 5. The case's sharing conditions mix survey data and interview excerpts

**Location:** `episodes/reproducible-research-overview.md:153`; later excerpt use in `episodes/repro-tools.md:104`.

The survey can supposedly be shared after “each participant has approved sharing their specific excerpt.” Excerpts belong to the interview example, and this sentence leaves unclear what is public, what remains restricted, and what the fictional team has permission to share. Those distinctions are central to the exercise, not incidental detail.

**Fix:** separate the fictional assumptions: “For this teaching case, the team has permission to share a de-identified survey dataset and selected, participant-approved interview excerpts. Full recordings remain restricted.” This specifies the case rather than presenting a general rule about consent or de-identification.

### 6. Distinguish missing evidence of reproducibility from proof of impossibility

**Locations:** `episodes/introduction.md:44,56`; `episodes/reproducible-research-overview.md:186`; glossary at `learners/reference.md:7–11`.

The public dataset example concludes that nobody could rerun it, including its original researcher. The scenario establishes that the public package lacks enough instructions, not that nobody has knowledge or materials elsewhere. Similarly, absence of version history does not necessarily prevent reproducing a static, adequately specified workflow.

**Fix:** say “The public package does not provide enough information for another analyst to reliably repeat the reported analysis; public access alone does not establish reproducibility.” Use this narrower conclusion in both solutions. Align the short glossary definition with the improved episode definition by including “same analysis steps.”

## Instructor handoff and final polish

The expanded notes are useful, but the qualitative-comparison discussion still has no concrete expected answer. Add two or three lines: quantitative checking examines input data, analysis steps/software and matching outputs; qualitative checking examines source selection, coding definitions, decision notes and the connection between excerpts and claims. Document what misunderstanding should cause an instructor to pause and explain again.

The handoff already records checking whether organizers have a next-pilot feedback plan. Preserve that distinction: the plan is not in the inspected instructor materials, but it may exist elsewhere. Before teaching, link it or agree who records actual durations, confusing terms, and learner responses; collect a short end-of-session reflection and debrief with the instructor. [CLDT's preparation guidance](https://carpentries.github.io/lesson-development-training/preparing.html) supports making those responsibilities explicit.

Lower-priority polish can happen alongside beta teaching: remove “current lesson proposal” from the landing page; shorten long tool bullets without changing the agreed tool list; define provenance/variable inline where first needed rather than relying only on the glossary; accept justified workflow-stage overlaps; and change the instructor claim that the crisis discussion works best without convergence to welcoming evidence-based agreement or disagreement.

**Final judgment:** the lesson now offers a useful and teachable progression from concepts to researcher support. The earlier unassessed objectives and lack of concrete application are largely repaired. Correct the timing, remove the visible statistical detour, and tighten the answer keys/case assumptions before handing it to the next instructor. Those are finishing changes to a sound design. An outside-instructor beta pilot is the right next test; stable-release confidence should come from that teaching evidence rather than another round of adding content.

## Adjudication outcome (2026-09-18)

All 6 numbered findings verified against the actual source (not taken on trust) and adopted. No rejections this round.

1. **Timing budgets** - Overview: marked the first classification challenge and the "additional examples from disciplines" discussion optional (~3 min, ~5 min), added the missing `(~5 min)` label to the Cool Access LA case challenge, leaving 29 required core minutes in the 32-minute allocation. Tools: `exercises: 20` → `24` to match the actual 3+2+4+2+6+5+2=24 min of labeled activities (54 min total with 30 teaching). Instructor pacing table and the "do not cut challenges" line updated to name the two optional Episode 2 activities.
2. Removed the learner-facing `::: callout` with the Student t-test/significance detour after the coin example; replaced with one neutral sentence. Instructor-notes.md's two references to that callout rewritten since it no longer exists in the episode - the t-test now only appears in instructor notes.
3. Git scenario now states the script was already committed yesterday and that data/environment are unchanged. Both classification challenges' answer options now spell out "same analysis steps"/"analysis method" instead of relying on an unstated assumption. Third-researcher coin example changed from "a new coin" to "the same coin, 100 more tosses" (lower-priority item, applied anyway - no cost, sound reasoning).
4. Library-repro-role.md's environment-referral answer rewritten to check setup instructions/recorded versions first, refer only if rebuilding needs expertise beyond the library.
5. Cool Access LA sharing-conditions sentence rewritten to cleanly separate survey (de-identified dataset) from interview (selected, approved excerpts; full recordings restricted).
6. Introduction's openness/reproducibility solution narrowed to "the package alone doesn't provide enough information," dropping the "no one... could rerun" overclaim. Glossary's short Reproducibility definition now matches the episode's fuller "same data and the same analysis steps."

Verified clean after all edits: `carpentries-workbench-checker` (0 errors/0 warnings/0 notes), `sandpaper::validate_lesson()`, `sandpaper::build_lesson()`.
