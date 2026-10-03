---
title: 'Making Research Checkable'
teaching: 10
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions

- Is research that is open also reproducible, and is research that is reproducible also open?
- What would you need beyond a project's named materials - a script, a data file, a source excerpt - to actually check what they claim?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Distinguish reproduction, replication, and openness in a case involving restricted materials, and explain what evidence supports the distinction
- Given a reported result, identify what connects it to the materials and decisions that support it, and name a piece of missing information

::::::::::::::::::::::::::::::::::::::::::::::::

The previous episode defined reproducibility. This one applies it to a common point of confusion: whether something being public is the same as it being checkable, and works through a single case to build a habit of asking that question.

## Reproducibility and Open Research

### Reproducibility is closely associated with transparency.
In order to reproduce others’ studies we need to have access to the methods, data, and analyses that have been conducted. So making data, tools and analyses available is essential for reproducibility. 

### Reproducible does not (have to) mean fully open.
However, a reproducible project does not have to be fully open. For example, due to privacy or copyright restrictions on methods, data, or analyses, researchers might need to keep parts of the research outputs under controlled access (e.g. available only to other researchers and not publicly available). This should not prevent them, though, from making the project fully reproducible (e.g. internally within their research team). 

### Open does not mean reproducible.
On the other hand, it is entirely possible to practice open science without following reproducibility principles. Materials, data, tools and code can be made openly available but if they do not have necessary documentation, instruction on how to use them, error checks, proper versioning and organization - they are most probably not usable, and the project might not be reproducible.

![Venn diagram: open and reproducible research overlap but are distinct](fig/image1.png){alt="Venn diagram showing that open and reproducible are overlapping but distinct categories of research practice"}

## A Recurring Example: Cool Access LA

::: callout
Starting here, this lesson returns a few times to a short fictional composite case, **Cool Access LA**. It is inspired by real UCLA heat-equity research, including the Heat Lab's [Red Hot LA: Mapping Energy Inequality](https://heatlab.humspace.ucla.edu/projects/red-hot-la-mapping-energy-inequality/) and a UCLA study on how [Los Angeles County residents use cooling centers during extreme heat](https://newsroom.ucla.edu/releases/cooling-centers-los-angeles-county-extreme-heat). Cool Access LA is not a real UCLA project, and nothing below describes any real research team's actual workflow, tools, or data. It is a teaching composite, built to be realistic without being real.
:::

**Cool Access LA**: Dr. Maya Torres, an urban studies researcher, is studying whether residents of a Los Angeles neighborhood can reach and use public cooling spaces, including public libraries, during extreme heat. Her team combines city temperature and facility-location data with a short household survey and a handful of resident interviews about barriers to using cooling centers. For this teaching case, the team has permission to share a de-identified survey dataset (identifying details that could reveal who a participant is have been removed) and selected, participant-approved interview excerpts. Full interview recordings remain restricted to protect participants.

::: challenge

## Reproduced, replicated, or just open? (~5 min)

1. A second analyst reruns Dr. Torres's original scripts on the same survey data and gets the same results.
2. A team in a different city collects its own survey and interview data, using the same questions and the same analysis method, and finds a similar pattern.
3. Dr. Torres shares her survey dataset and analysis code, but keeps the interview recordings restricted to protect participants.

Which of these is reproduction? Which is replication? Does restricting the interview recordings stop the project from being reproducible?

::: solution

1. Reproduction - same data, same method.
2. Replication using new data. Because the setting also changes (a different city), this can additionally provide evidence about generalizability - one matching result in a new place does not prove the finding holds everywhere, but it is a data point toward that.
3. This is not reproduction or replication, it is about **openness**. The survey analysis can be reproduced if the documented workflow runs successfully for someone else - that is a reproducibility question. Whether the interview recordings are public is a separate, openness question. An authorized reviewer could still trace the interview analysis using Dr. Torres's coding records and decision notes, even without the recordings becoming public. Restricting some material does not automatically make the rest of the project unreproducible.

:::

:::

## The Cool Access LA project packet

The rest of this lesson refers back to a small, fictional packet from Dr. Torres's project (invented teaching material, not a real dataset):

- `survey.csv` - household survey responses. One codebook entry: `q1a = days in the past 7 days when the respondent could not reach a cooling space; allowed values 0-7; 99 = no answer`
- `analysis.R` - a script that is said to produce **Figure 2: Days without cooling access, by neighborhood** in the team's draft report, using `survey.csv`
- One interview claim in the draft report: "Several residents described walking to the library specifically to use air conditioning." One supporting excerpt is on file:

  > **Excerpt `INT-07`** (approved for release): "It gets so hot in my apartment I can't stay there in the afternoon, so I walk to the library - it's air conditioned and it's close enough to walk."
  >
  > **Analytic note**: Coded *access barrier (home cooling)* - the participant describes home conditions as unlivable and names the library specifically for its air conditioning, not as a general destination.

  (This excerpt and note are invented teaching material, not a real interview.)

::: challenge

## What connects to what? (~5 min)

Having the file names above is not the same as being able to check what they claim. Answer both:

1. What would someone need, beyond what's listed, to reproduce Figure 2 exactly?
2. The report claim says "several residents" walked to the library for air conditioning, but the packet only shows evidence - one excerpt and its analytic note - for a single participant. What's missing before that plural claim is supported? Name what you'd ask for, and what having it would let someone check.

Do not invent an answer (a specific software version, a specific file version, additional excerpts that aren't shown) - name what you would ask for instead.

::: solution

1. Which exact version of `survey.csv` `analysis.R` was run against (the file may have been edited since the figure was made), and what software/package versions `analysis.R` needs to run. Having the script and the data file named isn't sufficient by itself - the connection between "this script, run on this version of this file, with this software" is what actually has to be documented before someone can reproduce the figure.
2. At minimum, excerpts and analytic notes for the other residents the claim describes - one coded excerpt supports a claim about one participant, not "several." Two acceptable directions: ask for more excerpts showing the same pattern (to check whether "several" holds up), or ask that the claim be narrowed to match the one piece of evidence shown ("one resident described..."). A coding scheme - the rules for what counts as an "access barrier" - is necessary but not sufficient here: it tells you the criteria, but checking whether a *plural* claim holds also requires seeing the individual excerpts and applied codes across enough of the interviews, not just confirming the scheme itself is well-defined. (Whether multiple examples are required at all depends on the qualitative approach in use - some traditions treat one richly-analyzed case as sufficient evidence for a claim about that case, without claiming it generalizes. The gap here is specifically that the evidence shown doesn't match the claim's plural scope, not a universal rule that every qualitative claim needs several examples.)

Both answers point at the same kind of gap: a named artifact (a script, an excerpt) is not yet a documented *connection* between that artifact and the claim it supports. That gap - not the artifact's mere existence - is usually what a librarian can help close.

:::

:::

## Looking ahead

Before judging whether a result can be checked, you first need to know what would count as evidence. Carry this question into the next episode: **what would you ask a researcher for, before you could judge whether their work can be checked?** The Benefits and Challenges episode picks up exactly that question, from the researcher's side of the conversation.

::: callout
### Optional: the "reproducibility crisis" debate (~10 min if discussed)

The rest of this episode is background context, not required for the lesson's practical outcomes above. Use it if you have time and the group is interested; skip it otherwise.

Problems with reproducibility of research have been noticed by many researchers, advisors and policy makers in the past several years and led to some even claim that there is a [“Reproducibility crisis”](https://www.nature.com/articles/533452a).
However, not everyone agrees the "crisis" framing is the right one. Two examples that push back on it, from different angles:

- [Is science really facing a reproducibility crisis, and do we need it to?](https://www.pnas.org/doi/full/10.1073/pnas.1708272114) (Fanelli, 2018) - questions whether the evidence supports "crisis" as an accurate description of the problem
- [The reproducibility debate is an opportunity, not a crisis](https://bmcresnotes.biomedcentral.com/articles/10.1186/s13104-022-05942-3) (Munafò et al., 2022) - argues the current attention on reproducibility is better framed as a chance to improve research practice than as a crisis to be alarmed about

**Reasons for Irreproducibility**

- Unavailability of materials, data and/or analyses
- Poor data management
- Unclear analysis specification
- Lack of documentation
- Errors in reporting numbers
- Lack of quality checking procedures
- Insufficient peer review
:::

::: discussion

(optional, ~10 min)

Do you agree that “crisis” is the right framing, based on the two perspectives above? What evidence would help you judge how big the problem actually is? Looking at the list of reasons for irreproducibility above, which one do you think a library service is best positioned to address?

:::

::: keypoints

- Reproducible research is not the same as open research - it is important to share research outputs to be able to reproduce others’ studies, but research can be made fully reproducible even if it cannot be made fully open.
- Naming a project's materials (a script, a data file, a source excerpt) is not the same as documenting the connection between them and a specific claim - that connection is what makes a result checkable.
- Recent studies point to many issues with reproducibility across different disciplines, something that has been termed “reproducibility crisis” (optional background, not required for this lesson's practical outcomes)

:::
