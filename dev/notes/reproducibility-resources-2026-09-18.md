# Reproducibility practices librarians can support: resource scan

Research date: 2026-09-18. Purpose: clarify the lesson's conceptual foundation using current primary sources. This is a targeted resource scan, not a systematic review or a fresh evaluation of the changing lesson files. Recommendations below are a synthesis, not a published competency standard. No lesson sources were edited.

## What the current sources suggest

Open science provides a broader context for reproducibility, including participation, access, infrastructure, and equity. Reproducibility remains a distinct practical concern within it. UNESCO's 2021 Recommendation explicitly incorporates reproducibility and methodological diversity: https://www.unesco.org/en/legal-affairs/recommendation-open-science

The most useful recent conceptual update is TOP 2025. It separates research practices from independent verification, and distinguishes disclosure, sharing/citation, and certification. This supports teaching librarians to distinguish making work checkable from actually checking it. The framework concerns empirical research; it is not a universal model for every scholarly tradition. Source: https://www.cos.io/initiatives/top-guidelines

My proposed organizing idea: librarians help researchers preserve and communicate the connection between questions, materials, decisions, and findings. That includes supporting appropriate checks and documenting what was checked. It can involve substantial technical work where the librarian has the expertise and service capacity.

## BITSS is still relevant

The RT2 2026 event page confirms a training held May 19-21 in Berkeley and links its presentations. Topics included GitHub, data management, R/Stata workflows, preregistration, pre-analysis plans, journal practices, and reproducible research with AI. Librarians and data stewards are explicitly included in its audience, but R or Stata proficiency is expected. It is an excellent instructor resource rather than a direct syllabus for this novice lesson.

Start with Sam Teplitzky's data-management presentation and the reproducible-workflows session. I verified the session listing and links, not the full slide contents. https://www.bitss.org/events/research-transparency-and-reproducibility-training-rt2-2026/

The Catalyst project listing also contains projects discussing 2025 developments and 2026 plans. This indicates continuing activity, but does not establish a currently open grant call: https://www.bitss.org/project-tag/catalyst-project/

## A practice framework for the lesson

| Practice | Conceptual contribution | Concrete support or artifact |
|---|---|---|
| Make methods and decisions explicit | Distinguish planned procedures, actual actions, and subsequent changes | Protocol, decision log, explanation of deviations; help locate a suitable registration route when appropriate |
| Document materials and provenance | Explain what materials mean, where they came from, and how they changed | README, codebook, file relationships, source citations, records of cleaning and exclusions |
| Preserve versions and dependencies | Identify the particular inputs and conditions behind a result | Version history, release identifier, software versions, environment record; scripting and dependency capture where skills allow |
| Connect evidence to findings | Identify which materials and procedures support a specific claim | Table-to-script mapping, source annotation, analytic memo, documented search strategy |
| Enable responsible access and reuse | Explain who can obtain what and under which conditions | Repository record, persistent identifier, access statement, appropriate permissions and metadata |
| Check and communicate limits | Separate documentation review, execution, result comparison, and scientific appraisal | Scoped check report identifying materials used, observed problems, unresolved questions, and next action |

These are related practices, not a mandatory linear checklist. Apply them while research is underway, not only at deposit. Preregistration does not fit every design in the same way. Documentation can describe legitimate adaptation and interpretation without forcing exploratory or qualitative work into a confirmatory model.

Librarians can introduce these practices, teach them, collaborate in carrying them out, or provide specialist assessment. The right level depends on expertise, access, resources, and the agreed service. Knowing when a methods specialist or research software engineer is needed is part of competent support, but referral should not become the definition of librarianship.

## Resources to draw from

1. **TOP 2025, Center for Open Science.** Recent framework for distinguishing availability from verification. Borrow its distinctions in instructor notes and assessment wording; avoid turning this lesson into a journal policy course. https://www.cos.io/initiatives/top-guidelines

2. **UKRN primers and Open Qualitative Research Practices (announced January 2025).** Short introductions covering computational reproducibility, qualitative practices, version control, and professional support roles. The qualitative resource explicitly responds to the dominance of quantitative assumptions in open research. Useful for explaining why the appropriate evidence and checks differ across methods. The primer index specifies CC BY 3.0; verify individual items when adapting. https://www.ukrn.org/primers/ and https://www.ukrn.org/2025/01/17/new-resources-empower-qualitative-researchers-to-embrace-open-research-practices/

3. **The Turing Way: Research Compendia.** Use the connected research project as the object of support: data, methods, documentation, outputs, and computational conditions belong together. Borrow this relationship rather than teaching a succession of unrelated tools. Living reference, not presented here as a newly published 2026 framework. https://book.the-turing-way.org/reproducible-research/compendia/

4. **Social Science Data Editors' README template.** Practical reference for checking whether another person can navigate a project, obtain its inputs, understand software requirements, and follow execution instructions. The site distinguishes release candidates from official releases. Its stated license is CC BY-NC: link to it and use the underlying concepts for an original exercise; do not assume its text can simply be incorporated into a CC BY lesson. https://social-science-data-editors.github.io/template_README/

5. **BITSS ACRe Guide.** Especially useful for scoping a check to a claim or output and avoiding an all-or-nothing judgment about an entire paper. Borrow scoping, constructive communication, and documenting improvements. Full execution and robustness assessment belong in more advanced training. Its economics-oriented terminology should not silently replace this lesson's definitions. Established resource, not claimed as a recent revision. https://bitss.github.io/ACRE/intro.html

6. **QDR's current ATI preparation instructions.** A concrete account of linking claims with source excerpts and explanations of how evidence was generated and interpreted. The instructions now describe Anno-REP. This is a better operational pointer than relying exclusively on the older Active Citation guide, whose ACE instructions are explicitly obsolete. Use the conceptual method; no additional tool installation is needed in this lesson. https://qdr.syr.edu/node/20665 and https://qdr.syr.edu/content/guide-active-citation

7. **PRISMA-S / PRISMA-Search.** Published in 2021 and still provided on the official site, with a 16-item checklist. A familiar library example of making a method inspectable. Use one brief example of recording a search process; do not add an evidence-synthesis module. https://www.prisma-statement.org/prisma-search

8. **CESSDA Data Management Expert Guide.** Established practical teaching material spanning documentation, processing, protection, and sharing, with both quantitative and qualitative examples. Useful for developing scenarios and instructor answers. Its full lifecycle is too large to import into this lesson. https://dmeg.cessda.eu/Data-Management-Expert-Guide

9. **Rigor and reproducibility instruction in academic medical libraries (2022).** Concrete library teaching cases, including integration with disciplinary curricula and institutional collaborators. Useful evidence that librarians already contribute through searching, appraisal, data management, and computational instruction. It describes medical-library cases, not the prevalence of these services across all libraries. https://doi.org/10.5195/jmla.2022.1443

The earlier CuRe lessons remain useful conceptual material for reviewing files, documentation, and relationships, but should retain the draft-status caveat from the previous narrative review. Their full archive and assessment sequence is a specialist extension: https://curating4reproducibility.org/training/

## Implications for the current lesson

The previous consultation throughline can become more substantive: diagnose which connection is missing, choose a practice that restores it, and identify a proportionate check. Recognizing a need for a partner is one possible outcome, not the only outcome.

For Cool Access LA, one figure could anchor the exercise. Which survey version produced it? What does a coded value mean? What transformations were applied? Which script and environment were used? What would a successful rerun demonstrate, and what would it leave unanswered? For an interview-based claim, ask which approved excerpt and analytic explanation support it, without promising identical interpretation or unrestricted access.

Use a short project packet containing a README, a codebook excerpt, and a named output or claim. Learners identify a missing connection, propose a specific improvement, and state how someone could check that improvement. This makes documentation, versioning, environment capture, and qualitative annotation purposeful.

A suitable learning promise: given a research workflow, identify what another person would need to follow or check it, recommend a concrete improvement, and explain who could carry it out and assess it.

Prioritize TOP's distinction, The Turing Way's connected project, and UKRN's methodological breadth for instructor framing. Use the README and QDR resources for small concrete activities. Keep RT2, ACRe, and CuRe as deeper pathways. AI appears in RT2 2026, but that alone does not justify expanding this introductory lesson into an AI module.

## Evidence limits

Verified current official resource pages and selected guidance, not every linked slide deck or primer PDF. Recent changes are identified explicitly; older resources are included for continued usefulness rather than relabeled as new. This scan supports a curriculum recommendation, not a claim that one uniform library service model or cross-disciplinary consensus exists.
