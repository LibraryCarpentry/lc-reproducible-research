# Validation request: Reproducible Research Workflows lesson revision — effectiveness and CLDT alignment

## Context

This is a Library Carpentry lesson, "Reproducible Research Workflows," part of a UCLA-run IMLS-funded "Open Science" lesson series aimed at librarians and research-support staff with no assumed programming background. It's in `alpha` life-cycle stage: authored, internally reviewed, and now being revised based on its first external pilot. It follows The Carpentries' standard Workbench format (episodes with `questions`/`objectives`/`keypoints` blocks, `challenge`/`solution`/`discussion` divs, front-matter `teaching`/`exercises` minute estimates) and is expected to follow The Carpentries' Collaborative Lesson Development Training (CLDT) guidance, summarized below since you won't have it memorized.

**CLDT principles to check against** (as understood by this project, not verbatim from the source):
- Learning objectives should be SMART (specific, measurable) and each one should have a corresponding formative-assessment checkpoint (a challenge, discussion, or exercise that actually exercises it) - an objective with nothing checking it is a gap.
- Episodes are recommended to run 20-60 minutes (teaching + exercises combined); much shorter or longer is "worth a second look for scope," though not a hard rule.
- Lessons should include a feedback-collection plan for pilots (observer notes, minute cards, end-of-session surveys) - not itself something to check in the text, but relevant background for why this revision exists.
- Jargon and discipline-specific terms should be defined on first use for a general audience, not assumed.

## What happened before this revision

A community pilot ran this lesson in June 2026 (UMass Amherst library staff, ~50 minutes actual runtime against a 20-minute estimate for the worst-hit episode). Real problems that pilot surfaced, now supposedly fixed in the current text:

1. Jargon used without definition: "Student t-test," "active citation," "code capsule," and inconsistent use of "data report" vs. "manuscript" vs. "data paper"
2. Two bare citation links dropped into the "Reproducibility Crisis" section with zero framing
3. An awkwardly-phrased challenge question ("Based on what we went through, we can say...")
4. No time estimates on in-episode discussions, contributing to the pacing blowout
5. The "Role of the Libraries" episode read as though a single librarian should personally do everything on its list; pilot instructors explicitly rejected this framing and one bullet said as much

Separately, an AI-assisted review pass (a different tool, already adjudicated once) found: a factual error (renv was mislabeled as a "container" when it's closer to a dependency lockfile - now corrected), missing solution blocks on some challenges, a broken README link, ~19 missing glossary terms, and a pre-existing accessibility bug where images used markdown bracket alt text instead of the Pandoc `{alt="..."}` syntax Workbench actually needs for `validate_lesson()` to pass (also now corrected).

**Also added in this revision**: a running fictional-but-real-research-grounded case study, "Cool Access LA" (a composite librarian scenario about a researcher studying cooling-center access during heat waves, inspired by real UCLA Heat Lab research but explicitly labeled as not real), threaded across Episodes 2, 3, 4, and 5 to give the abstract reproducibility/replicability/openness distinctions a concrete throughline.

## Already decided - do not relitigate

- Cool Access LA's domain (urban heat-equity research) and its "light spine" scope (substantial use in Episodes 2 and 4, brief one-to-two-sentence touches in 3 and 5) were deliberately chosen after a prior validation round. Critique how well it's *executed*, not whether a different domain or heavier/lighter use would be better.
- "ATI" (Annotation for Transparent Inquiry) is confirmed to be a real QDR/Syracuse initiative, verified directly against qdr.syr.edu/ati, not a mix-up with the ATLAS.ti software package - already checked once, don't re-flag this as a possible confusion.
- Whether to trim the Episode 4 tool list (ELNs, Code Ocean, Docker-as-primary-example, HackMD, Overleaf, code-quality tools) down to fewer, deeper entries is a known open question the project owner has deferred ("keep as-is for now") - you can note if the list still feels like a scope risk, but don't spend your critique budget re-arguing a decision that's already been made for now.
- The mechanical Workbench fixes (config.yaml contact field, missing questions/objectives/keypoints blocks, front-matter `exercises:` values, alt-text syntax) are done and passing `carpentries-workbench-checker` (0 errors, 0 warnings) and `sandpaper::validate_lesson()`/`build_lesson()` - don't re-audit these for compliance, they're confirmed clean. Focus your review on pedagogy and content quality, not the mechanical checklist.

## The current text

### `episodes/introduction.md`

```markdown
---
title: 'Introduction'
teaching: 15
exercises: 8
---

:::::::::::::::::::::::::::::::::::::: questions

- Why does reproducibility matter for research integrity?
- What does this lesson cover, and who is it for?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain why reproducibility matters to research quality and trust
- Describe how this lesson connects to broader open science practices

::::::::::::::::::::::::::::::::::::::::::::::::

## Who this lesson is for, and what it covers

This lesson is written for library and research-support staff (data services librarians, research computing consultants, and similar roles) who want to help researchers make their work reproducible. No programming background is assumed.

Over the next four episodes, you will move from concepts to practice: what reproducibility means and how it differs from replicability (episode 2), the benefits and challenges researchers face (episode 3), concrete tools mapped onto each stage of a research workflow (episode 4), and where library services fit into supporting all of this (episode 5).

## Why does this matter?

Reproducibility is a key part of research integrity. When research is reproducible, others can check your work, build on it, and reuse it with confidence.

For example: a researcher who deposits their raw data, analysis code, and a README explaining how to run it has made their work reproducible. A colleague can download that package, rerun the same script, and get the same numbers back, without emailing the original researcher to ask what "clean_data_v3_final.csv" actually contains.

Making research reproducible helps:

- Improve the quality and reliability of results
- Respond to concerns about irreproducible studies in many fields, sometimes referred to as a "reproducibility crisis" (see episode 2 for more on this framing)
- Support broader changes in research, including global efforts to make science more open
- Align with funder, journal, and institutional expectations for transparency and rigor

In short, reproducible research strengthens science, supports collaboration, and helps researchers meet growing expectations for responsible research conduct.

## Reproducibility and open science

Reproducibility overlaps with, but is not the same as, **open science**: the broader practice of making research outputs such as data, code, methods, and publications openly available so others can inspect, reuse, and build on them. Open science is one route to reproducibility (it is hard to reproduce a study you cannot access), but the two are not interchangeable. A dataset can be posted publicly with no documentation or version history, which makes it open but not reproducible. A research team can also make their full workflow reproducible for internal use while keeping the data itself restricted for privacy or licensing reasons, which makes it reproducible but not fully open. Episode 3 returns to this distinction with worked examples.

::: challenge

## Reproducibility or replicability?

A colleague reruns your analysis scripts on your deposited data and gets identical figures back. Which of these has been demonstrated?

1. Reproducibility
2. Replicability
3. Generalization
4. Verification

::: solution

1. Reproducibility. The colleague used your original data and your original method and got the same result. Replicability would involve new data collected under the same design; generalization would involve applying the result to a different context or population; verification is a broader check that findings are accurate, not specifically about rerunning the same analysis.

:::

:::

::: discussion

(~3 min)

Before we go further: in your own words, why might a funder or journal care whether a study is reproducible?

**Possible answers**: reproducibility lets funders and journals verify that public or grant money produced results that hold up under scrutiny; it protects institutional and publication reputations against retractions; and it lets other researchers build on the work with confidence instead of re-doing it from scratch.

:::

::: keypoints

- Reproducibility is central to research integrity and helps others check, build on, and reuse research
- Reproducibility and open science overlap but are not the same thing: openness helps enable reproducibility but does not guarantee it
- This lesson moves from concepts (reproducibility vs. replicability), to benefits and challenges, to tools, to the library's role in supporting all of it

:::
```

### `episodes/reproducible-research-overview.md`

```markdown
---
title: 'What is Reproducible Research?'
teaching: 22
exercises: 24
---

:::::::::::::::::::::::::::::::::::::: questions 

- What do we mean by reproducibility?
- When is research reproducible?
- Does reproducibility mean different things in different disciplines?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what research reproducibility is
- Provide examples where reproducibility is not the same as open science (or: does not overlap with)
- Explain how different disciplines define reproducibility differently

::::::::::::::::::::::::::::::::::::::::::::::::

## Reproducibility: Some Definitions

**Reproducibility**: Obtaining the same results using the same data.

**Replicability**: Achieving similar results with new data.

Research is **reproduced** when results are consistent when following the same method and analysis steps with the same input data

Research is **replicated** when results are consistent across studies that answer the same research question, each of which has obtained its own data

Research results are **generalized** when results apply in other contexts or populations that differ from the original one

[Source](https://www.nap.edu/catalog/25303)

![2x2 matrix of reproduced, replicated, robust, and generalized results](fig/epi1.png){alt="A 2x2 matrix crossing whether the data is the same or different (columns) with whether the analysis is the same or different (rows). Same data and same analysis is labeled Reproduced. Different data and same analysis is labeled Replicated. Same data and different analysis is labeled Robust. Different data and different analysis is labeled Generalized."}

Based on: [The Turing Way: Overview of reproducibility definitions](https://the-turing-way.netlify.app/reproducible-research/overview/overview-definitions.html)

::: challenge

## Which of these describes a reproduced study?

1. Researchers apply similar methods to the original study in a new study
1. Researchers re-analyze data from the original study and observe the same results
1. Researchers reuse data from the original study for a new purpose

::: solution

2. Researchers re-analyze data from the original study and observe the same results

:::

:::

## Reproducibility: Some Examples

Let's consider an example: a researcher is tossing a coin 100 times to check if the coin is fair. They register if they have observed heads or tails after each toss when the coin falls on the floor. Heads are registered as 0 and tails as 1. The sample size of this study is N = 100 (since they are tossing the coin 100 times).

```
Hypothesis: The coin is fair (i.e. not biased)
Sample size: N = 100
Heads = 0
Tails = 1
Analysis method = Student t-test
```

After all data is collected (i.e. the researcher is done with the tossing) they start data analysis. They run a simple statistical test in the SPSS program - a **Student t-test** (a common statistical test for comparing an observed average against an expected value) - to compare the number of observed tails outcomes against the chance level (which is 0.5 since the coin has two sides, and if it's fair, there should be a 50% chance of getting tails). The researcher observes that the number of tails they got is no different from chance - and so they found a support for their original hypothesis. The researcher makes the complete data table and detailed methods and analysis from the study available to the public.

Another researcher downloads the data table and re-runs the exact same analysis in a different software using R programming language. They also observe that the number of tails is no different from chance. **They have reproduced the study!**

A third researcher reads about the reproduced study and decides to conduct a new data analysis on a different coin. They apply the exact same methods (i.e. they toss a coin 100 times and register the outcome every time the coin falls on the floor). Just as in the original study, they mark heads as 0 and tails as 1. They also run a Student t-test on the data and they observe that the number is tails is no different from chance. **They have replicated the study!**

Note, however, that in many different disciplines the word "reproduced" could be used in both the second and the third researcher case, that is to mean both reproducing and replicating the study.

::: challenge

## Reproduced, replicated, or generalized? (~5 min)

For each scenario below, decide whether it describes reproducing, replicating, or generalizing a result.

1. A team re-runs a colleague's published analysis script on the exact same dataset and gets the same numbers.
2. A team collects new survey data using the same questionnaire and finds a similar pattern of responses.
3. A team that found an effect in a lab study finds the same effect holds in a real-world field setting with a different population.

::: solution

1. Reproduced (same data, same method)
2. Replicated (new data, same method, same question)
3. Generalized (result extends to a different context/population)

:::

:::

::: discussion

(~5 min)

Can you provide additional examples of reproducible studies from various disciplines or research types?

:::

## Reproducibility Across Methodologies and Research Disciplines

### Quantitative Studies: Computational Reproducibility

It is defined as "obtaining consistent computational results using the same input data, computational steps, methods, code, and conditions of analysis" ([https://www.nap.edu/catalog/25303](https://www.nap.edu/catalog/25303)). What it means is basically re-running analyses/code with the same data.

### Qualitative Studies: Process Transparency

Here we mean arriving at a similar (consistent) interpretation by following the same analysis process. This could be obtained by following the step-by-step reasoning and interpretation process of the researcher(s).

::: discussion

(~5 min)

Discuss in pairs: Should we use the term "reproducibility" across different disciplines and research methodologies even though it might mean different things?

:::

## Reproducibility and Open Research

### Reproducibility is closely associated with transparency.
In order to reproduce others' studies we need to have access to the methods, data, and analyses that have been conducted. So making data, tools and analyses available is essential for reproducibility.

### Reproducible does not (have to) mean fully open.
However, a reproducible project does not have to be fully open. For example, due to privacy or copyright restrictions on methods, data, or analyses, researchers might need to keep parts of the research outputs under controlled access (e.g. available only to other researchers and not publicly available). This should not prevent then, though, from making the project fully reproducible (e.g. internally within their research team).

### Open does not mean reproducible.
On the other hand, it is entirely possible to practice open science without following reproducibility principles. Materials, data, tools and code can be made openly available but if they don't have necessary documentation, instruction on how to use them, error checks, proper versioning and organization - they are most probably not usable, and the project might not be reproducible.

![Venn diagram: open and reproducible research overlap but are distinct](fig/image1.png){alt="Venn diagram showing that open and reproducible are overlapping but distinct categories of research practice"}

## A Recurring Example: Cool Access LA

::: callout
Starting here, this lesson returns a few times to a short fictional composite case, **Cool Access LA**. It is inspired by real UCLA heat-equity research, including the Heat Lab's [Red Hot LA: Mapping Energy Inequality](https://heatlab.humspace.ucla.edu/projects/red-hot-la-mapping-energy-inequality/) and a UCLA study on how [Los Angeles County residents use cooling centers during extreme heat](https://newsroom.ucla.edu/releases/cooling-centers-los-angeles-county-extreme-heat). Cool Access LA is not a real UCLA project, and nothing below describes any real research team's actual workflow, tools, or data. It is a teaching composite, built to be realistic without being real.
:::

**Cool Access LA**: Dr. Maya Torres, an urban studies researcher, is studying whether residents of a Los Angeles neighborhood can reach and use public cooling spaces, including public libraries, during extreme heat. Her team combines city temperature and facility-location data with a short household survey and a handful of resident interviews about barriers to using cooling centers. The survey data can be shared once identifying details are removed; the interview recordings must stay restricted to protect participants.

::: challenge

## Reproduced, replicated, or just open?

1. A second analyst reruns Dr. Torres's original scripts on the same survey data and gets the same results.
2. A team in a different city collects its own survey and interview data using the same questions and finds a similar pattern.
3. Dr. Torres shares her survey dataset and analysis code, but keeps the interview recordings restricted to protect participants.

Which of these is reproduction? Which is replication? Does restricting the interview recordings stop the project from being reproducible?

::: solution

1. Reproduction - same data, same method.
2. Replication - new data, same method, same question, different place.
3. This isn't reproduction or replication, it's about **openness**. Restricting the interviews limits how open the project is, but the survey data and code can still be fully documented and reproducible on their own terms - reproducibility and openness are related but separate, as the sections above cover.

:::

:::

## Reproducibility Crisis

Problems with reproducibility of research have been noticed by many researchers, advisors and policy makers in the past several years and led to some even claim that there is a ["Reproducibility crisis"](https://www.nature.com/articles/533452a).
However, not everyone agrees the "crisis" framing is the right one. Two examples that push back on it, from different angles:

- [Is science really facing a reproducibility crisis, and do we need it to?](https://www.pnas.org/doi/full/10.1073/pnas.1708272114) (Fanelli, 2018) - questions whether the evidence supports "crisis" as an accurate description of the problem
- [The reproducibility debate is an opportunity, not a crisis](https://bmcresnotes.biomedcentral.com/articles/10.1186/s13104-022-05942-3) (Munafò et al., 2022) - argues the current attention on reproducibility is better framed as a chance to improve research practice than as a crisis to be alarmed about

### Reasons for Irreproducibility

- Unavailability of materials, data and/or analyses
- Poor data management
- Unclear analysis specification
- Lack of documentation
- Errors in reporting numbers
- Lack of quality checking procedures
- Insufficient peer review

::: discussion

(~10 min)

Do you agree that there is a reproducibility crisis in academic research?
How many studies would have to reproduce successfully for the "crisis" to be over?
What could librarians do to help researchers fight the "reproducibility crisis"?

:::

::: keypoints

- Reproducibility usually means obtaining the same results with the same data.
- Across different disciplines and methodologies, the understanding of what reproducibility means can be very different.
- Reproducible research is not the same as open research - it is important to share research outputs to be able to reproduce others' studies, but research can be made fully reproducible even if it cannot be made fully open.
- Recent studies point to many issues with reproducibility across different disciplines, something that has been termed "reproducibility crisis"

:::
```

### `episodes/repro-challenges.md`

```markdown
---
title: 'Benefits and Challenges of Reproducibility'
teaching: 10
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can science benefit from reproducible research?
- How can researchers benefit personally from reproducibility?
- What are the main challenges in making research reproducible?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Identify at least four benefits of reproducible research
- Explain how reproducibility supports research integrity
- List at least four challenges researchers face
- Give one example of how support services can address a challenge

::::::::::::::::::::::::::::::::::::::::::::::::

## Benefits for Science

Reproducibility strengthens research by making it:

- Easier to **verify**, helping others detect errors
- More likely to be **accurate**, since processes are transparent
- Easier to **understand** and **reuse**, through documentation
- Simpler to **share**, when licensing or privacy allow

## Benefits for Researchers

Reproducibility also helps individual researchers:

- Become more **efficient**: while setup takes time, it saves time later
- Feel more **confident**, knowing their work can be checked and reused
- Gain **recognition**: reproducible outputs are valued in grant reviews and assessments

::: discussion

Name one benefit of reproducibility for science and one for individual researchers. Why are these important?

:::

## Common Challenges

Despite the benefits, reproducibility can be hard to achieve. Some common obstacles:

- It takes **time** to adopt new workflows or improve documentation
- It requires **skills** in tools, formats, and platforms
- **Legal or ethical restrictions** may limit what can be shared
- **Technical barriers** can arise from software changes or compatibility issues

## How to Support Reproducibility

These challenges can be addressed with the right support:

- **Time**: Institutions and funders can recognize reproducible outputs and allow time for preparation
- **Skills**: Training and support staff can help researchers learn best practices
- **Restrictions**: Secure platforms and internal review can enable controlled sharing
- **Technical issues**: Guidance on software documentation and environment capture can help others reproduce results

::: callout
**Back to Cool Access LA** (introduced in the previous episode): Dr. Torres's team is not short on motivation, documentation lets a new research assistant pick up the project and answer a peer reviewer's questions months later. Their real obstacle is that the interview recordings can't leave a secure, IRB-approved storage system - a legal/ethical restriction, not a technical one.
:::

::: discussion

Pick one challenge researchers face when making their work reproducible - Dr. Torres's interview-recording restriction above, or one of your own.
Talk with a partner about how you, as a librarian or support staff member, could help address that challenge.

:::

::: keypoints

- Reproducibility improves research quality and benefits both science and individual researchers
- It can be difficult due to time, skills, legal, and technical challenges
- Support services like training, infrastructure, and guidance are key to helping researchers succeed

:::
```

### `episodes/repro-tools.md`

```markdown
---
title: 'Tools for Reproducible Research Workflows'
teaching: 27
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions 

- What are reproducible research workflows?
- Which stages of the research process can be made more reproducible?
- What tools can help improve reproducibility?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Identify key stages in a research workflow
- List at least four tools that support reproducibility
- Describe, for a documentation tool and a version-control tool, one specific task it would be used for in a research project

::::::::::::::::::::::::::::::::::::::::::::::::

## What is a Reproducible Research Workflow?

A research workflow is the sequence of steps a researcher takes to produce outputs like a dataset, an analysis, or a publication.

Reproducibility can be improved in three key areas:

1. **Data collection and processing**
2. **Data analysis**
3. **Writing and reporting results**

The illustration below lists six concrete practices that cut across those three stages, from organizing files at the start of a project through automating the final computations:

![Illustration: Reproducible Research, 6 helpful steps. Credit: Heidi Seibold, CC-BY 4.0.](fig/image2copy.png){alt="Illustration titled Reproducible Research: 6 helpful steps, showing six numbered practices: 1. get your files and folders in order, 2. use good names for files, folders, and functions, 3. document with care using README files, metadata, and code comments, 4. version control code and text, 5. stabilize the computing environment and software, 6. automate computations. Credit: Heidi Seibold, CC-BY 4.0."}

:::: callout
Using the right tools helps researchers automate tasks, track changes, and make their work easier to reproduce and reuse. Tools alone will not fix an undocumented, disorganized project, but without them, even well-intentioned practices are hard to sustain over the life of a project.
::::

::: challenge

## Sort the stages

Before reading further, try sorting these tasks into the three workflow stages above (data collection and processing / data analysis / writing and reporting): writing a codebook, running a statistical test, drafting a manuscript in Overleaf, setting up version control for a script.

::: solution

- **Data collection and processing**: writing a codebook
- **Data analysis**: running a statistical test, setting up version control for a script (version control is most often introduced once code exists to track, so it spans analysis and reporting)
- **Writing and reporting results**: drafting a manuscript in Overleaf

:::

:::

## Tools by Research Stage

Different tools support different parts of the workflow. Below are examples by stage.

### 1. Data Collection and Processing

Good documentation makes data collection methods clear and reusable.

- **README files** - A plain-text file stored alongside a dataset or project that describes its contents, structure, provenance, and terms of use, so someone else can navigate it without asking you: [Cornell template](https://data.research.cornell.edu/data-management/sharing/readme/)
- **Codebooks** - A document that records, for each variable in a dataset, its name, meaning, permitted values, units, and how missing data is coded
- **Electronic Lab Notebooks (ELNs)** - A digital replacement for a paper lab notebook, used to record experimental procedures, observations, and results in a searchable, shareable form (e.g. Jupyter as a notebook interface, or a dedicated ELN platform like LabArchives)

### 2. Data Analysis

Tools vary based on the type of research (quantitative vs qualitative).

#### Quantitative Analysis

- **R**, **Python**, **SPSS Syntax** - For scripting and transparency
- **Git** - A version control system that records successive changes to code, text, or data files over time, so any earlier state can be recovered and the history of who changed what is preserved
- **Code quality tools** - [The Turing Way: Code Quality](https://the-turing-way.netlify.app/reproducible-research/code-quality.html)
- **Environment management** - Tools that record the exact software versions and dependencies a project used, so it can be re-run the same way later or on another machine. This is often done with lightweight, language-specific tools such as [renv](https://the-turing-way.netlify.app/reproducible-research/renv/renv-options.html) for R, or with full containers (e.g. Docker) that package the entire operating environment. renv is not itself a container; it is closer to a dependency lockfile.
- **Code Ocean** - Share "code capsules" (a code capsule bundles your code, data, and computing environment together so someone else can run it without recreating your setup): [https://codeocean.com](https://codeocean.com)

#### Qualitative Analysis

- **Coding and annotation** - Free, open-source qualitative analysis software such as **QualCoder** or **Taguette**, for coding and tagging qualitative source material. Both have their own dedicated Library Carpentry lessons if you want to go deeper: [Open Qualitative Research with QualCoder](https://librarycarpentry.github.io/lc-qualitative-qualcoder/) and [Open Qualitative Research with Taguette](https://ucla-imls-open-sci.info/lessons/open-qualitative-research-taguette/)
- **Active Citation** - a practice for qualitative research where claims in a paper link directly to the specific passage of source material that supports them, so a reader can check the evidence without re-doing the whole analysis. For example: linking a claim about a resident's stated barrier directly to the relevant, de-identified excerpt of their interview transcript, rather than just a generic citation to "interview #14." [Active Citation example](https://www.princeton.edu/~amoravcs/library/ps.pdf). A more tooled-up descendant of this idea, ATI (Annotation for Transparent Inquiry), comes from the Qualitative Data Repository (QDR) at Syracuse - whose director, Sebastian Karcher, co-taught the pilot workshop for this lesson series' own [Taguette lesson](https://ucla-imls-open-sci.info/lessons/open-qualitative-research-taguette/) above

### 3. Writing and Reporting

Tools for integrating code, results, and narrative.

- **R Markdown** - Combines R code with text, both built on **Markdown**, a lightweight plain-text formatting syntax that converts to HTML, PDF, and other formats
- **Quarto** - Supports multiple languages; also markdown-based
- **Jupyter Notebooks** - The same Jupyter environment listed as an ELN above, used here for its other common purpose: combining live Python code with results and narrative for a written report
- **HackMD** - Collaborative markdown editor for co-writing
- **Overleaf** - Online LaTeX for polished documents

## Cool Access LA in Practice

Recall Dr. Torres's team from the previous two episodes: a household survey and facility data, a handful of restricted resident interviews, and a shared analysis. Here is how the tools above map onto their actual workflow:

- A **README and codebook** explain what each survey column means and note which files (the interview recordings) are restricted and why
- **Git** tracks changes to the analysis scripts as the team revises them, so an earlier version can always be recovered
- **Environment management** (renv) records the exact R package versions used, so the analysis still runs the same way next year
- The team codes interview transcripts in **QualCoder** or **Taguette**, then uses **Active Citation**-style annotation to link specific claims in the final report back to de-identified excerpts, without exposing the full restricted recordings
- **Quarto** combines the quantitative survey results and the qualitative interview findings into one reproducible report

::: challenge

## Which tool would you reach for?

Dr. Torres's research assistant has a folder of survey data with cryptically-named columns (`q1a`, `q1b`, `q2_rev`, ...) and wants to hand it off to a new team member. Which tool from this episode would you point them to first?

::: solution

A codebook. It documents what each column means, its permitted values, and how missing data is coded, which is exactly the gap here. A README would help too (for the folder as a whole), but the immediate problem is the undocumented variables, which a codebook addresses directly.

:::

:::

:::::::: discussion

## Exercises

1. Visit this [README template](https://data.research.cornell.edu/data-management/sharing/readme/) and imagine filling it out for Dr. Torres's survey dataset.
   - How could you support a researcher in completing it?
   - Which sections would benefit most from library support?

**Possible answer**: sections describing file naming conventions and variable definitions are often the hardest for researchers to fill in on their own, since it requires stepping back from work they already understand intuitively. Library support (e.g. a documentation consultation) can help translate that tacit knowledge into text a stranger could follow.

2. Dr. Torres's team wants to make their interview analysis auditable without exposing the restricted recordings. What tools or practices from this episode could help?
   - If these tools are not available, what alternatives might work using familiar tools?

**Possible answer**: QualCoder or Taguette for coding (both free and open source, and both covered in their own Library Carpentry lessons linked above), or Active Citation practices to link report claims to de-identified excerpts. Without access to specialized software, a documented coding scheme in a shared spreadsheet, plus a written record of the analytic decisions made (why a passage was coded a certain way), can substitute for at least part of what dedicated qualitative tools provide.

::::::::::::::

:::::::: keypoints

- Research workflows include data collection, analysis, and reporting; each stage offers opportunities to improve reproducibility
- Many tools exist to support documentation, versioning, and sharing; match the tool to the specific gap (e.g. a codebook for undocumented variables, version control for changing code)
- A container and an environment-management tool like renv both stabilize a computing environment, but they are not the same thing: renv is not a container

:::::::::::
```

### `episodes/library-repro-role.md`

```markdown
---
title: 'The Role of Libraries in Supporting Reproducibility'
teaching: 15
exercises: 8
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is the role of libraries in supporting reproducible research?
- How can library staff support researchers in improving reproducibility?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Describe how libraries support reproducible research
- Given a description of a researcher's request, identify which library service would help most

::::::::::::::::::::::::::::::::::::::::::::::::

## Why Libraries?

Libraries are well positioned to support reproducible research: many library services that already exist (open access support, research data management, documentation guidance) map directly onto what reproducibility requires. For example, a funder now requiring a data management plan with a documented, shareable dataset is asking for exactly the kind of support research data services already provide for other reasons.

As funders and journals begin to expect not only open but also reproducible research, libraries can expand their support. Librarians work across disciplines and with researchers at all career stages. This makes them key partners in promoting transparency and improving research workflows.

## How Libraries Support Reproducibility

No single librarian is expected to do all of the following - different libraries build different combinations of this support depending on staffing, expertise, and institutional priorities. Roughly in order from lowest to highest specialization, library staff can help by:

- Raising awareness and offering training on reproducible research
- Supporting transparent research practices, including documenting methods, sharing data, and explaining analysis steps
- Helping researchers create clear, consistent documentation for all stages of a project
- Reviewing a project's documentation and workflow for clarity and completeness, so that the researcher's own team (not the librarian) can rerun it later
- Advising on version control tools to track changes in code, data, or manuscripts (this is a more specialized, higher-effort service: it assumes the advisor has hands-on familiarity with a tool like Git, not just awareness that version control exists)

::: challenge

## Which service applies?

Dr. Torres, from Cool Access LA in the previous two episodes, emails you: "My interview recordings have to stay in a secure, IRB-approved system for privacy reasons, but my funder is now asking for a reproducibility statement. I don't even know where to start."

Which of the services listed above would you reach for first?

::: solution

Start with documentation and workflow review: help Dr. Torres write down her data processing and analysis steps clearly enough that another approved member of her own team could follow them. Note that "reproducible" does not require the interview recordings to leave the secure system or become public - that's an openness question, not a reproducibility one. Version control advice might come next if her analysis code changes over time, but documentation is the more urgent, lower-barrier need here.

:::

:::

::: discussion

## Reflection

What is one area where you think libraries can make the biggest difference in supporting reproducible research? Given your own library's staffing and expertise, which of the areas above feel realistic to take on, and which would need new skills or partners?

**Possible answers**: awareness-raising and documentation support are realistic starting points for most libraries since they build on existing reference and instruction skills; version control advising is more often a stretch that requires either staff training or a partnership with a research computing group.

:::

::: keypoints

- Libraries are natural partners in supporting open and reproducible research, because much of the required support already exists as library services under other names
- Library support for reproducibility ranges from low-effort (awareness, documentation) to more specialized (version control advising), and no one librarian is expected to cover all of it
- Reproducibility support builds on existing library expertise in research data and scholarly communication

:::
```

### `instructors/instructor-notes.md` (full)

```markdown
---
title: 'Instructor Notes'
---

## Pacing

The Introduction and What is Reproducible Research? episodes carry most of the conceptual weight. In a community pilot (UMass Amherst, June 2026), the first discussion in What is Reproducible Research? was budgeted 5 minutes but ran closer to 15, and the whole episode ran about 50 minutes against a 20-minute teaching estimate. Budget extra time for discussion, or be ready to time-box firmly.

## Terms that trip learners up

Several terms in this lesson assume background knowledge that a general library audience may not have. Define these explicitly rather than assuming familiarity:

- **Student t-test** (used as an example statistical test in the coin-toss exercise) - it's fine if learners don't know the details, but say plainly that it's a common test for comparing an observed result to an expected one
- **Active citation** and **code capsule** (Tools for Reproducible Research Workflows) - both are now defined inline in the episode, but be ready for follow-up questions since neither is a familiar term outside specific research communities
- **Data report** vs. **manuscript** vs. **data paper** - these are genuinely distinct publication types and pilot learners found them easy to conflate; be ready to draw the distinction if it comes up

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
```

### `learners/reference.md` glossary (full - just the term list, for jargon-completeness checking)

Reproducibility, Replicability, Generalization, Verification, Research Integrity, Open Science, Reproducibility Crisis, Transparency, Rigor, Responsible Research Conduct, Open Access, Open Data, Version Control, Scholarly Communication, Research Workflow, Documentation, Research Data Management, Codebook, README File, Container, Electronic Lab Notebook (ELN), Markdown

## What I want you to challenge

Read the lesson as if you were teaching it cold to a room of librarians with no stats/CS background, then answer these directly - don't just list impressions:

1. **CLDT objective-to-assessment mapping**: For each episode, does every stated learning objective have a challenge/discussion that actually exercises it, or are any objectives still just stated and never checked? Be specific about which objective, which episode.
2. **Timing realism**: Episode 2 (`reproducible-research-overview.md`) now declares `teaching: 22, exercises: 24` (46 min total) after the pilot ran it closer to 50 real minutes against a 20-minute original estimate. Does the current content plausibly fit in 46 minutes, or is this still an undercount given how much reading/discussion is packed in? Same question for Episode 4 (`repro-tools.md`, 27+15=42 min) given how many tools it now covers.
3. **Cool Access LA effectiveness**: Does the running case actually do cognitive work (helping learners apply the concepts to a concrete scenario), or does it read as decorative flavor text bolted onto pre-existing content? Is Episode 4's "Cool Access LA in Practice" section - which maps ~7 tools onto one scenario in a few bullets - doing too much at once to be a clear worked example?
4. **Jargon audit**: Scan all 5 episodes plus the glossary for any term used without definition that a librarian with no stats/research-methods background would stumble on. The pilot flagged "Student t-test," "active citation," "code capsule," and the data-report/manuscript/data-paper distinction as problems - are there other terms like this that were missed (e.g., "SPSS Syntax," "p-values" implicit in the t-test discussion, "IRB-approved")?
5. **"Role of the Libraries" reframe**: Did the added "no single librarian is expected to do all of the following" line and the specialization ordering actually resolve the pilot's core objection, or does it risk reading as hedging/vague rather than a clearer scope? Is the objective "given a description of a researcher's request, identify which library service would help most" adequately served by the one worked example (Dr. Torres's IRB restriction) plus one reflection question?
6. **Anything CLDT-flagged I haven't mentioned**: episode sequencing, keypoints that don't match objectives, discussion prompts with no time estimate I might have missed, or challenges that are actually closed-book trivia rather than genuine application.

For each finding, give me: the specific location (episode + line/section), why it's a problem against CLDT or plain pedagogical effectiveness, and a concrete fix (not just "consider revising"). End with a confidence score (1-10) on whether this lesson is ready to move from `alpha` to `beta` life-cycle stage as currently written, and what would need to change first if it's not.
