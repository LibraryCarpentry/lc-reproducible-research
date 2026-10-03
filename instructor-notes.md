---
title: 'Instructor Notes'
---

## Pacing

The Introduction, Understanding Reproducibility, and Making Research Checkable episodes carry most of the conceptual weight. In a community pilot (UMass Amherst, June 2026), the first discussion in the (then-combined) What is Reproducible Research? episode was budgeted 5 minutes but ran closer to 15, and the whole episode ran about 50 minutes against a 20-minute teaching estimate. That episode has since been split into two (Understanding Reproducibility and Making Research Checkable), and front matter across all six episodes has been revised to more realistic (though still un-piloted) numbers. Suggested per-activity timing:

| Episode | Teaching | Key activity times |
|---|---|---|
| 1. Introduction | 17 min | Openness/reproducibility challenge ~5 min, funder/journal discussion ~3 min (8 min required core, matches declared). Teaching time includes the consultation-flow diagram, which adds reading but no exercise time. |
| 2. Understanding Reproducibility | 14 min | Classification challenge ~5 min, methodological-comparison discussion ~5 min (10 min required core against 12 declared - the extra 2 min is debrief/transition buffer, not an unallocated gap); first classification ~3 min and additional-examples discussion ~5 min are optional, ~8 min more if both are run |
| 3. Making Research Checkable | 10 min | Case-classification challenge ~5 min, "what connects to what?" evidence-mapping challenge ~5 min (10 min required core, matches declared exactly); the "reproducibility crisis" discussion is optional background, ~10 min more if run |
| 4. Benefits and Challenges | 10 min | Both discussions ~5 min each (10 min required core, matches declared) |
| 5. Tools | 30 min | Sort-the-stages ~3 min, "what would go wrong" ~2 min, "what would you ask for - and what would you do next?" (the extended README hand-off exercise) ~6 min, version-control scenario ~4 min, qualitative-auditability ~5 min, "before you go" transfer task ~3 min (23 min total, all required, matches declared) |
| 6. Role of Libraries | 15 min | Service-choice challenge (one of two alternative scenarios, not both) ~4 min, reflection ~4 min (8 min required core, matches declared) |

These are still planning estimates, not measured pilot times - treat this table as a script to test, not a guarantee. Declared front matter across all six episodes totals 167 min (25 + 26 + 20 + 20 + 53 + 23). Named required-core activities plus teaching sum to 165 (the 2-min gap is Episode 2's debrief buffer, noted above; every other episode's named activities match its declared total exactly). Optional activities add 18 min total across the lesson (8 in Episode 2, 10 in Episode 3). With every optional activity run, the full lesson is about 185 min before breaks. If you're short on time, compress the Cool Access LA recaps in Episodes 4 and 6 (a sentence or two, not the full scenario). In Episode 2, the first classification challenge and the "additional examples from disciplines" discussion are optional. In Episode 3, the "reproducibility crisis" discussion (and its background reading) is optional. In Episode 6, the two "which service applies?" scenarios are alternatives, not both required - pick whichever fits your audience. Skip any of these if you're tight on time. Do not cut any other challenge or discussion - several episode objectives are only assessed through those activities.

## Terms that trip learners up

Several terms in this lesson assume background knowledge that a general library audience may not have. Most are now defined inline on first use (see the glossary in `learners/reference.md` for the full list), but be ready for follow-up questions on:

- **Student t-test** - no longer used in the coin-toss example (see below), but mentioned here for instructors who want to extend the example for a more statistically sophisticated audience; the episode itself never mentions it to learners
- **Active citation** and **code capsule** (Tools for Reproducible Research Workflows) - neither is a familiar term outside specific research communities
- **Robust**, in the reproducibility matrix (Understanding Reproducibility) - distinct from reproduced/replicated/generalized, and easy to skip past without noticing it's a fourth category

## The coin-toss example no longer uses a significance test

The original version asked learners to accept that "no significant difference from chance" meant the coin was fair, then treated two such non-significant results as "reproducing" the finding. That's a real statistical misconception (failing to detect a difference isn't the same as proving there isn't one), and teaching it alongside the reproducibility concept risked confusing both ideas at once. The current example uses a plain proportion (53 tails out of 100 tosses) instead, so reproducing the study just means recalculating the same proportion from the same data. If a learner asks about extending the example for a more statistically sophisticated audience, you can introduce a **Student t-test** as a common way to compare an observed average against an expected value, but be careful to teach that a non-significant result means "we did not detect a difference," not "we proved there is none."

## The "Role of the Libraries" episode

No single librarian is expected to do everything on this episode's list of ways libraries can help - lean into that framing when teaching, rather than presenting it as a checklist every library should complete. Equally, nothing on the list is off-limits to a librarian who has the skills, authorized access, and service mandate for it: the framing is task-specific (teach, implement directly, collaborate, or refer, depending on actual capacity), not a fixed rule in either direction. If a learner pushes back that "surely no librarian does version control," the honest answer is that some do and some don't, and that variation is the point of the reflection discussion.

## Interconnected lessons

The Tools episode points learners to two sibling Library Carpentry lessons for hands-on qualitative tool practice: `lc-qualitative-qualcoder` and the Taguette lesson (`lc-open-qualitative-research`). Worth calling out explicitly if it comes up: Sebastian Karcher, Director of the Qualitative Data Repository (QDR) at Syracuse, co-taught the Taguette lesson's pilot workshop. QDR is also the organization behind ATI (Annotation for Transparent Inquiry), the more tooled-up descendant of Active Citation covered in this episode - so the qualitative-tools thread in this lesson and the sibling qualitative lessons trace back to the same expertise.

## Cool Access LA (running example, Episodes 3-6)

Episodes 3-6 return to a single fictional composite case, Cool Access LA, introduced in "Making Research Checkable." It is explicitly labeled as a teaching composite inspired by real UCLA heat-equity research (the Heat Lab's *Red Hot LA* project and a UCLA cooling-centers study), not a description of any real research team's actual workflow. If a learner asks whether Cool Access LA is real, say clearly that it isn't - the citations in the Episode 3 callout are real research, but the fictional researcher (Dr. Torres) and her team are not.

Each later episode only restates one or two sentences of the case rather than adding new plot - if you're running short on time, the Episode 4 and 6 references to it are the first things you can compress, since the substantive use of the case is in Episodes 3 and 5.

### The project packet and its deliberate evidence gap

Making Research Checkable introduces a small fictional packet: a survey file and codebook entry, an analysis script said to produce a named figure, and an interview claim ("several residents...") backed by exactly one shown excerpt and analytic note. That mismatch is intentional - the episode's exercise asks learners to notice that one excerpt supports a claim about one participant, not "several," and to name what's missing (more excerpts, or a narrower claim) rather than accept the packet's framing at face value. Don't let learners "fix" this by assuming the missing excerpts exist; the point is to practice asking for what isn't there. The Tools episode's extended README exercise reuses the same packet one step further: propose an improvement to the hand-off note, and say what check it would enable. If you're teaching only one of the two episodes (e.g. a shortened workshop), each exercise still works from its own text.

## The consultation-flow diagram

The Introduction and the Role of Libraries episode share one Mermaid flowchart, appearing only in those two places (introduced briefly, then returned to at the end). It depicts identifying materials, planning a *scoped* check, attempting it, and recording the outcome - deliberately not gating any check on full traceability first, since a limited attempt (a partial rerun, a documentation skim, a version comparison) is often exactly what surfaces a specific gap. A blocked attempt and a completed one both lead to an agreed next action; a completed check can show a match, a discrepancy, or a partial result, not only success. The diagram doesn't sort checks by quantitative/qualitative, since either kind of project can need a rerun-style check, an evidence-tracing check, or both. If a learner asks who actually attempts the check, the answer is: whoever has the access and skill to do it safely - the researcher, an appropriately trained librarian, or a partner service - which is the judgment call the Role of Libraries exercises practice.

Each occurrence has a plain-text ordered-list callout directly below it (for screen readers and non-Mermaid renderers), and both diagrams set Mermaid's `accTitle`/`accDescr` directives, which populate the rendered SVG's own accessible name and description (its `aria-labelledby`/`aria-describedby` point to a `<title>`/`<desc>` pair inside the SVG - the standards-compliant mechanism screen readers use). A separate "Please enter an accessible description" prompt may still be visible below the diagram; that comes from an unrelated, client-side viewer feature with no Markdown-level control in the current theme, not a gap in the diagram's actual accessibility metadata. Don't spend teaching time on it - the SVG's real accessible name/description is populated, and the callout below each diagram is the intended reading path regardless.

## Instructor reading list

For your own background, not required learner reading. Keep to the reproducibility scope of this lesson - these sources cover more ground than the lesson does.

- **[TOP (Transparency and Openness Promotion) 2025 guidelines](https://www.cos.io/initiatives/top-guidelines)**, Center for Open Science - the clearest current framing of *disclosure* (saying what you did) versus *verification* (someone checking it), which underlies this lesson's split between "is this checkable" and "has this been checked." Written for journals/funders setting policy, not for teaching novices directly.
- **[The Turing Way: Research Compendia](https://book.the-turing-way.org/reproducible-research/compendia/)** - the idea that a project's data, methods, documentation, and outputs belong together as one connected object, rather than being a list of separate tools. This lesson's project packet is a small, fictional instance of that idea.
- **[UKRN primers](https://www.ukrn.org/primers/)** - short introductions to reproducibility topics including qualitative open-research practices, useful if a learner wants a next step beyond this lesson's qualitative coverage (coding schemes, Active Citation).
- **[Social Science Data Editors' README template](https://social-science-data-editors.github.io/template_README/)** - a more detailed alternative to the Cornell template linked in the Tools episode, for instructors who want a second concrete model of what a complete README covers. Its text is CC BY-NC; link to it rather than copying it into learner materials (this lesson is CC BY).
- **[RT2 2026](https://www.bitss.org/events/research-transparency-and-reproducibility-training-rt2-2026/)** (BITSS) - optional, deeper-learning pathway for instructors or advanced learners; assumes R/Stata proficiency this lesson doesn't require.

## Common questions

- Learners sometimes ask why reproducibility and open science are being treated as separate things. The Reproducibility and Open Research section is designed to address this directly - point learners there if the question comes up earlier than expected.
- The "reproducibility crisis" discussion tends to generate genuine disagreement. That's intentional - the lesson links to two papers that take different positions on whether "crisis" is the right framing, and the discussion works best when the group doesn't converge on one answer.
- Learners sometimes assume that running a coding tool like QualCoder automatically makes an analysis auditable. It doesn't by itself - what makes it auditable is keeping the excerpts, applied codes, and analytic notes together and reviewable; the software just makes that easier to sustain than scattered documents would.
