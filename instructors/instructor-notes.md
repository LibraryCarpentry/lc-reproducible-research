---
title: 'Instructor Notes'
---

## Pacing

The Introduction and What is Reproducible Research? episodes carry most of the conceptual weight. In a community pilot (UMass Amherst, June 2026), the first discussion in What is Reproducible Research? was budgeted 5 minutes but ran closer to 15, and the whole episode ran about 50 minutes against a 20-minute teaching estimate. A follow-up pedagogical review found the original time estimates didn't add up even on paper - front matter across all five episodes has since been revised to more realistic (though still un-piloted) numbers. Suggested per-activity timing:

| Episode | Teaching | Key activity times |
|---|---|---|
| 1. Introduction | 15 min | Openness/reproducibility challenge ~5 min, funder/journal discussion ~3 min |
| 2. What is Reproducible Research? | 23 min | Classification challenges ~3-5 min each, Cool Access LA challenges ~5-4 min, crisis discussion ~10 min |
| 3. Benefits and Challenges | 10 min | Both discussions ~5 min each |
| 4. Tools | 30 min | Sort-the-stages ~3 min, codebook/version-control challenges ~2-4 min each, README/qualitative exercises ~6/5 min, four-tools exit check ~2 min |
| 5. Role of Libraries | 15 min | Service-choice challenge (two scenarios) ~4 min, reflection ~4 min |

These are still planning estimates, not measured pilot times - treat this table as a script to test, not a guarantee. If you're short on time, compress the Cool Access LA recaps in Episodes 3 and 5 (a sentence or two, not the full scenario), but do not cut the challenges or discussions themselves - several episode objectives are only assessed through those activities, so cutting them removes the only check that learners got the concept.

## Terms that trip learners up

Several terms in this lesson assume background knowledge that a general library audience may not have. Most are now defined inline on first use (see the glossary in `learners/reference.md` for the full list), but be ready for follow-up questions on:

- **Student t-test** - no longer used in the coin-toss example (see below), but mentioned in a callout for anyone wanting to extend the example for a more statistically sophisticated audience
- **Active citation** and **code capsule** (Tools for Reproducible Research Workflows) - neither is a familiar term outside specific research communities
- **Robust**, in the reproducibility matrix (What is Reproducible Research?) - distinct from reproduced/replicated/generalized, and easy to skip past without noticing it's a fourth category

## The coin-toss example no longer uses a significance test

The original version asked learners to accept that "no significant difference from chance" meant the coin was fair, then treated two such non-significant results as "reproducing" the finding. That's a real statistical misconception (failing to detect a difference isn't the same as proving there isn't one), and teaching it alongside the reproducibility concept risked confusing both ideas at once. The current example uses a plain proportion (53 tails out of 100 tosses) instead, so reproducing the study just means recalculating the same proportion from the same data. A callout in the episode covers the statistical-test version for instructors who want to extend the example - use it carefully, with the caveat about what a non-significant result does and doesn't show.

## The "Role of the Libraries" episode

Pilot instructors pushed back on the idea that any single librarian could realistically do everything listed in this episode's list of ways libraries can help. The episode text now includes a line clarifying that libraries build different combinations of this support depending on staffing and expertise - lean into that framing when teaching, rather than presenting the list as a checklist every library should complete.

## Interconnected lessons

The Tools episode points learners to two sibling Library Carpentry lessons for hands-on qualitative tool practice: `lc-qualitative-qualcoder` and the Taguette lesson (`lc-open-qualitative-research`). Worth calling out explicitly if it comes up: Sebastian Karcher, Director of the Qualitative Data Repository (QDR) at Syracuse, co-taught the Taguette lesson's pilot workshop. QDR is also the organization behind ATI (Annotation for Transparent Inquiry), the more tooled-up descendant of Active Citation covered in this episode - so the qualitative-tools thread in this lesson and the sibling qualitative lessons trace back to the same expertise.

## Cool Access LA (running example, Episodes 2-5)

Episodes 2-5 now return to a single fictional composite case, Cool Access LA, introduced in "What is Reproducible Research?" It is explicitly labeled as a teaching composite inspired by real UCLA heat-equity research (the Heat Lab's *Red Hot LA* project and a UCLA cooling-centers study), not a description of any real research team's actual workflow. If a learner asks whether Cool Access LA is real, say clearly that it isn't - the citations in the Episode 2 callout are real research, but the fictional researcher (Dr. Torres) and her team are not.

Each later episode only restates one or two sentences of the case rather than adding new plot - if you're running short on time, the Episode 3 and 5 references to it are the first things you can compress, since the substantive use of the case is in Episodes 2 and 4.

## Common questions

- Learners sometimes ask why reproducibility and open science are being treated as separate things. The Reproducibility and Open Research section is designed to address this directly - point learners there if the question comes up earlier than expected.
- The "reproducibility crisis" discussion tends to generate genuine disagreement. That's intentional - the lesson links to two papers that take different positions on whether "crisis" is the right framing, and the discussion works best when the group doesn't converge on one answer.
