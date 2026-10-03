# Narrative review: a practical takeaway for librarians

Reviewed 2026-09-18 against the current working tree, including the uncommitted corrections made after the earlier review. Compared with the user-supplied Turing Way and Library Carpentry pages and selected linked chapters. This is an evaluation and bounded revision proposal; no lesson sources were edited.

**Recommendation:** keep the five-episode sequence and Cool Access LA's existing light-spine role. Make the lesson's recurring question explicit: “What would another person need to follow this work, and what can I help the researcher improve?” The learner should finish able to conduct an initial reproducibility-support conversation, identify a concrete gap, and agree a next step or referral.

The current lesson now has good individual exercises. Its remaining narrative weakness is that the librarian's method of working is implicit. Learners move from definitions to benefits to tools to services, but must assemble for themselves how to use those pieces in a consultation. Repeating the same project name provides continuity; carrying a question and a decision through those episodes would provide progression.

## What the reference materials contribute

The [Turing Way guide introduction](https://book.the-turing-way.org/reproducible-research/reproducible-research/) frames reproducibility around rerunning analysis and introduces the connections among data, tools, code and results. Our lesson covers the principal concepts and introduces appropriate practices. The handbook's full technical breadth is not an appropriate completeness checklist for a novice library lesson. Its [environment chapter](https://book.the-turing-way.org/reproducible-research/renv/) explicitly targets intermediate/advanced readers and assumes command-line experience. Here the librarian needs to recognize an environment requirement and identify help, rather than learn its implementation.

The strongest Turing Way addition is conceptual: treat the project's materials as a connected whole. Its [research compendia chapter](https://book.the-turing-way.org/reproducible-research/compendia/) connects data, methods, documentation, environment information and outputs. We can use “project materials” in the learner text without introducing another technical term. In our current Tools episode, the components are mostly explained one tool at a time. A short example showing which input and analysis produce a particular figure would connect them.

The [Curating for Reproducibility Workflows introduction](https://librarycarpentry.github.io/lc-curation-workflows/) identifies itself as the second lesson of the CuRe curriculum; [Reproducibility Assessment](https://librarycarpentry.github.io/lc-reproducibility-assessment/) is the third and prepares learners for later packaging/publishing. This is a specialized curation sequence. Our lesson can borrow its questions while retaining a broader research-support audience and allowing intervention during an active project.

| Source | Concept worth borrowing | Adaptation within this lesson |
|---|---|---|
| [Data Quality Review framework](https://librarycarpentry.github.io/lc-curation-workflows/01-dqr.html) | Examine relationships among materials and recognize that different work requires different expertise. | Ask what is missing from the path to a result and who can help. This supports the existing documentation/referral framing. |
| [Documentation Review](https://librarycarpentry.github.io/lc-curation-workflows/03-doc-review.html) | A README should explain file relationships, methods, software requirements and access conditions. | Replace the current imaginary README completion with inspection of a short, deliberately incomplete fictional README. |
| [File Review](https://librarycarpentry.github.io/lc-curation-workflows/02-file-review.html) | Compare an account of the files with the files actually provided. | Ask whether the README names the input file and output being discussed. Keep preservation formats, checksums and repository metadata outside this lesson. |
| [Output Review](https://librarycarpentry.github.io/lc-reproducibility-assessment/03-review.html) | Successful execution must be connected to the reported result. | Ask “Which figure or table should the authorized analyst compare?” This clarifies the purpose of the workflow without requiring the learner to execute it. |

The linked Library Carpentry sites currently display pre-alpha status and include unfinished exercises/placeholders. They are useful conceptual sources, not evidence of a tested follow-on course. If passages or exercises are adapted, credit the specific source and preserve the applicable CC BY attribution. Acknowledge their draft status when recommending them to instructors.

Do not import the full DQR taxonomy, deposit acceptance rules, detailed code inspection/execution, or certification of a package into this lesson. Doing a helpful initial documentation consultation is not equivalent to completing a DQR. These are choices to preserve the user's intended scope, not judgments that those specialist practices are unimportant.

## The current story, episode by episode

| Episode | What works now | Where the story loses momentum | Smallest useful change |
|---|---|---|---|
| 1. Introduction | Establishes importance and separates access from reproducibility. | Motivation mainly comes from funders, journals and research integrity. The learner's everyday task is less prominent. | In the existing audience paragraph, state the practical outcome: help a researcher identify what another person would need to follow the work and choose the next support action. No new case or exercise is needed. |
| 2. What is Reproducible Research? | Definitions, the arithmetic example and Cool Access LA establish distinctions well. | The case is followed by the crisis discussion, so the episode ends on a broad debate rather than the question learners will carry forward. | End that existing discussion with “What would you ask a researcher for before you could judge whether a result can be checked?” Carry that answer into barriers in Episode 3. |
| 3. Benefits and Challenges | Makes limitations and support visible. | It revisits Episode 1's motivation and emphasizes the restricted interviews again. The restriction becomes the case's dominant recurring issue. | Reword the short case recap around a new team member needing to follow the documented work while interview access stays restricted. In the existing partner task, have learners name a feasible next action and explain how it addresses their chosen barrier. |
| 4. Tools | The codebook and Git exercises now give real application. | Learners see a long catalogue before the strongest connection among materials, methods and results. They can identify a tool without learning what to ask for first. | Keep the tool list and stage headings. Introduce the list as responses to particular gaps. Replace the current six-minute README-template activity with a short artifact review connecting an input, an analysis and an expected output. |
| 5. Library role | Clear boundaries, referral scenario and capacity reflection. | Reassures learners about their role but does not quite produce a reusable consultation response. | Tighten the existing four-minute service-choice task: ask for one missing detail, one action the library can take, and one researcher/partner responsibility. Keep the reflection and the brief case presence. |

This gives each episode a different job: establish the purpose, clarify what counts as evidence, identify the barrier, choose a response, and agree who will act. The case need not grow into a project simulation. Its substantial use stays in Episodes 2 and 4, with brief references in 3 and 5.

## A bounded replacement for the README exercise

Location: `episodes/repro-tools.md`, “Exercises,” first discussion item. Replace the existing six-minute prompt asking learners to visit the Cornell template and imagine completing it. Keep the template as a reference.

Display an intentionally incomplete fictional note, created for this lesson:

> Cool Access LA survey analysis. Use `survey.csv` and `analysis.R` to make the chart in the report. Run it in R. Interview recordings are restricted; only approved excerpts are included here.

Ask pairs to identify two details they would request and explain why each matters. Supply enough context that this is a comprehension task, not guessing syntax. Good answers include the survey file's version and variable definitions, the steps and software requirements needed to run the analysis, and the identity of the figure/output to compare. Where restricted materials are relevant, ask for the documented access route or responsible contact, not the restricted content itself.

Model a useful query: “Which version of the survey generated Figure 1, and where are the run instructions and software requirements recorded?” The researcher supplies those facts; the librarian helps make the documentation understandable. Do not have learners invent missing project details or imply that finding two omissions completes a reproducibility assessment.

One simple mapping in the existing case bullets can make the exercise easier: survey data → documented analysis → named figure. For the interviews, use the corresponding but distinct relationship: permitted excerpt → coding/decision record → report interpretation. That preserves the mixed-methods scope without claiming qualitative transparency is a computational rerun.

This change is conceptually informed by the curation material, but the prompt above is an original adaptation for this fictional case. Its value is that librarians practice asking a precise question about evidence, rather than merely recognizing a README as a useful object.

## What librarians should leave able to do

A portable set of consultation questions, expressed as ordinary questions rather than a new framework to memorize:

1. What specific result or interpretation does someone need to check?
2. What data, source material and documentation support it, and who is allowed to access them?
3. Are the analysis steps, relevant versions, or interpretive decisions recorded clearly enough to follow?
4. What would count as checking it: comparing rerun outputs, or tracing the reasoning behind an interpretation?
5. What is the next useful action, and should the library, researcher or another service take it?

The output can be a three-line note: “What we know; what is missing; agreed next action and responsible person.” This can fit inside Episode 5's current task. It is evidence of attaining the existing third lesson objective, not a new outcome or a full curation checklist.

For Cool Access LA, a credible response is: “We can help clarify the README, codebook and access description. The research team needs to identify the input version and expected output and have an authorized analyst check the workflow. If recreating the software environment requires additional expertise, we can connect them with research computing.” The actual allocation depends on local services; technical librarians may contribute more where that is part of their role.

## Scope and recommendation

The current working-tree changes already resolve the earlier major timing-accounting and example issues: optional Overview activities, a 24-minute Tools exercise budget, removal of the visible statistics detour, recorded Git history, clearer sharing assumptions, and an improved environment referral. This review does not reopen those findings.

Against The Turing Way, the lesson has a sensible selection of foundational content. Against the curation sequence, it already contains useful ingredients but could better connect them into a librarian's conversation with a researcher. The missing element is not more coverage; it is an explicit connection between a result, the materials supporting it, the gap a learner notices, and the next person who can act.

Make the few framing/transition edits above and replace one existing exercise with the short README review. Retain the episode order, case domain, brief Episode 3/5 use, tool list and novice prerequisites. Keep the qualitative interpretation branch explicit. Refer instructors to the source lessons for optional specialist development. The existing three lesson-level objectives can remain unchanged.
