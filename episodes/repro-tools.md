---
title: 'Tools for Reproducible Research Workflows'
teaching: 30
exercises: 20
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

## Sort the stages (~3 min)

Before reading further, try sorting these tasks into the three workflow stages above (data collection and processing / data analysis / writing and reporting): describing what each survey column means, calculating a result from the data, writing up the findings, and keeping a record of changes to a script.

::: solution

- **Data collection and processing**: describing what each survey column means (this is what a codebook does)
- **Data analysis**: calculating a result, keeping a record of changes to a script (version control is most often introduced once code exists to track, so it spans analysis and reporting)
- **Writing and reporting results**: writing up the findings

:::

:::

## Tools by Research Stage

Different tools support different parts of the workflow. Below are examples by stage.

### 1. Data Collection and Processing

Good documentation makes data collection methods clear and reusable.

- **README files** – A plain-text file stored alongside a dataset or project that describes its contents, structure, provenance, and terms of use, so someone else can navigate it without asking you: [Cornell template](https://data.research.cornell.edu/data-management/sharing/readme/)
- **Codebooks** – A document that records, for each variable in a dataset, its name, meaning, permitted values, units, and how missing data is coded
- **Electronic Lab Notebooks (ELNs)** – A digital replacement for a paper lab notebook, used to record experimental procedures, observations, and results in a searchable, shareable form (e.g. Jupyter as a notebook interface, or a dedicated ELN platform like LabArchives)

### 2. Data Analysis

Tools vary based on the type of research (quantitative vs qualitative).

#### Quantitative Analysis

- **R**, **Python** – Programming languages commonly used for data analysis; both let you save your analysis as a **script** (saved computer instructions that can be re-run to repeat a task), so the steps are transparent and repeatable
- **SPSS Syntax** – A saved set of commands that repeats an analysis in the SPSS statistical software package, playing the same transparency role as an R or Python script
- **Git** – A version control system that records successive changes to code, text, or data files over time, so any earlier state can be recovered and the history of who changed what is preserved
- **Code quality tools** – Tools and practices for checking that a calculation behaves as expected, e.g. through automated tests: [The Turing Way: Code Quality](https://the-turing-way.netlify.app/reproducible-research/code-quality.html)
- **Environment management** – Tools that record the exact software versions and **dependencies** (additional software a project's code needs to run) a project used, so it can be re-run the same way later or on another machine. This is often done with lightweight, language-specific tools such as [renv](https://the-turing-way.netlify.app/reproducible-research/renv/renv-options.html) for R, which records and helps restore the exact versions of R **packages** (reusable, shareable bundles of software code) a project used - or with full containers (e.g. Docker) that package the entire operating environment. renv is not itself a container; it produces something closer to a **lockfile** (a record of the exact dependency versions needed to recreate an environment later).
- **Code Ocean** – Share "code capsules" (a code capsule bundles your code, data, and computing environment together so someone else can run it without recreating your setup): [https://codeocean.com](https://codeocean.com)

#### Qualitative Analysis

- **Coding and annotation** – Free, open-source qualitative analysis software such as **QualCoder** or **Taguette**, used for **coding** qualitative source material: attaching descriptive labels (a **coding scheme**) to passages of text to organize and interpret them - distinct from writing program code. This makes an analysis **auditable**: another person can trace the evidence and reasoning behind a conclusion, even if they don't reach the same interpretation themselves. Both tools have their own dedicated Library Carpentry lessons if you want to go deeper: [Open Qualitative Research with QualCoder](https://librarycarpentry.github.io/lc-qualitative-qualcoder/) and [Open Qualitative Research with Taguette](https://ucla-imls-open-sci.info/lessons/open-qualitative-research-taguette/)
- **Active Citation** – a practice for qualitative research where claims in a paper link directly to the specific passage of source material that supports them, along with a brief explanation of why that passage supports the claim - not just a hyperlink - so a reader can check the evidence without re-doing the whole analysis. For example: linking a claim about a resident's stated barrier directly to the relevant, de-identified excerpt of their interview transcript, with a sentence on why that excerpt supports the claim, rather than just a generic citation to "interview #14." [Active Citation example](https://www.princeton.edu/~amoravcs/library/ps.pdf). A more tooled-up descendant of this idea, ATI (Annotation for Transparent Inquiry), comes from the Qualitative Data Repository (QDR) at Syracuse - whose director, Sebastian Karcher, co-taught the pilot workshop for this lesson series' own [Taguette lesson](https://ucla-imls-open-sci.info/lessons/open-qualitative-research-taguette/) above

### 3. Writing and Reporting

Tools for integrating code, results, and narrative.

- **R Markdown** – Combines R code with text, both built on **Markdown**, a lightweight plain-text formatting syntax that converts to HTML, PDF, and other formats
- **Quarto** – Supports multiple languages; also markdown-based
- **Jupyter Notebooks** – The same Jupyter environment listed as an ELN above, used here for its other common purpose: combining live Python code with results and narrative for a written report
- **HackMD** – Collaborative markdown editor for co-writing
- **Overleaf** – An online editor for **LaTeX** (a document-preparation system commonly used for polished, technical documents)

## Cool Access LA in Practice

Recall Dr. Torres's team from the previous two episodes: a household survey and facility data, a handful of restricted resident interviews, and a shared analysis. Here is how the tools above map onto their actual workflow:

- A **README and codebook** explain what each survey column means and note which files (the interview recordings) are restricted and why. For example, one codebook entry might read: `q1a = days in the past 7 days when the respondent could not reach a cooling space; allowed values 0-7; 99 = no answer`. (This is invented teaching data, not a real survey.)
- **Git** tracks changes to the analysis scripts as the team revises them, so an earlier version can always be recovered
- **Environment management** (renv) records the exact R package versions used, helping the team recreate the same computing environment for a later rerun
- The team codes interview transcripts in **QualCoder** or **Taguette**, then uses **Active Citation**-style annotation - each excerpt paired with a sentence on why it supports the claim - to link specific claims in the final report back to de-identified excerpts, without exposing the full restricted recordings
- **Quarto** combines the quantitative survey results and the qualitative interview findings into one report - though assembling the writeup this way doesn't by itself reproduce the reasoning behind the qualitative findings; that traceability comes from the coding scheme and annotations above, not from the writing tool

::: challenge

## What would go wrong here? (~2 min)

Looking at the codebook entry above (`99 = no answer`), what would happen if someone analyzing this data treated `99` as if it were a real count of days, rather than a missing-data code?

::: solution

It would badly distort any calculation involving that column - averages, totals, or comparisons would be skewed upward by treating "no answer" as "99 days," which isn't a real possible value (there are only 7 days in a week). This is exactly the kind of error a codebook prevents: without it, a second analyst has no way to know 99 is a special code rather than real data.

:::

:::

::: challenge

## A version-control scenario (~4 min)

Dr. Torres's research assistant changed a figure in the report after editing the analysis script yesterday. A collaborator asks what changed and whether the earlier figure can be recovered. Which tool from this episode would you reach for, and what would you do with it?

::: solution

Git. You would compare the current version of the script against yesterday's version to see exactly what changed, and you could recover the earlier version of the script (and re-generate the earlier figure) if needed. This doesn't tell you which figure is scientifically correct - only documentation and re-analysis can establish that - but it does let you inspect and recover the change itself.

:::

:::

::: challenge

## Which tool would you reach for? (~2 min)

Dr. Torres's research assistant has a folder of survey data with cryptically-named columns (`q1a`, `q1b`, `q2_rev`, ...) and wants to hand it off to a new team member. Which tool from this episode would you point them to first?

::: solution

A codebook. It documents what each column means, its permitted values, and how missing data is coded, which is exactly the gap here. A README would help too (for the folder as a whole), but the immediate problem is the undocumented variables, which a codebook addresses directly.

:::

:::

:::::::: discussion

## Exercises

1. (~6 min) Visit this [README template](https://data.research.cornell.edu/data-management/sharing/readme/) and imagine filling it out for Dr. Torres's survey dataset.  
   - How could you support a researcher in completing it?  
   - Which sections would benefit most from library support?

**Possible answer**: sections describing file naming conventions and variable definitions are often the hardest for researchers to fill in on their own, since it requires stepping back from work they already understand intuitively. Library support (e.g. a documentation consultation) can help translate that tacit knowledge into text a stranger could follow.

2. (~5 min) Dr. Torres's team wants to make their interview analysis auditable without exposing the restricted recordings. What tools or practices from this episode could help?  
   - If these tools are not available, what alternatives might work using familiar tools?

**Possible answer**: QualCoder or Taguette for coding (both free and open source, and both covered in their own Library Carpentry lessons linked above), or Active Citation practices to link report claims to de-identified excerpts. Without access to specialized software, a documented coding scheme in a shared spreadsheet, plus a written record of the analytic decisions made (why a passage was coded a certain way), can substitute for at least part of what dedicated qualitative tools provide.

:::::::::::::

::: challenge

## Before you go: name four (~2 min)

Name four tools or documentation artifacts from this episode, and the specific gap each one addresses. (README files and codebooks count as tools in this lesson's broad sense, not just named software.)

::: solution

Example answer: a codebook (documents what each variable means), Git (recovers and tracks changes to code), renv (records exact package versions for a later rerun), and Active Citation (links claims to specific evidence). Any four with a correct gap each are fine.

:::

:::

:::::::: keypoints

- Research workflows include data collection, analysis, and reporting; each stage offers opportunities to improve reproducibility
- Many tools exist to support documentation, versioning, and sharing; match the tool to the specific gap (e.g. a codebook for undocumented variables, version control for changing code)
- Use documentation (README, codebook) to explain what your data and steps mean, and version control (Git) to inspect and recover changes to your code over time

::::::::::: 
