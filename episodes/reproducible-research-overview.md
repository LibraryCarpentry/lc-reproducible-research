---
title: 'What is Reproducible Research?'
teaching: 10
exercises: 1
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

**Reproducibility** means obtaining the same results with the same data

**Replicability** means obtaining similar results with new data

Research is **reproduced** when results are consistent when following the same method and analysis steps with the same input data

Research is **replicated** when results are consistent across studies that answer the same research question, each of which has obtained its own data

Research results are **generalized** when results apply in other contexts or populations that differ from the original one

[Source](https://www.nap.edu/catalog/25303)

![Based on: [https://the-turing-way.netlify.app/reproducible-research/overview/overview-definitions.html](https://the-turing-way.netlify.app/reproducible-research/overview/overview-definitions.html)](fig/epi1.png)

::: challenge

## Based on what we went through, we can say that a study has been reproduced when:

1. Researchers apply similar methods to the original study in a new study
1. Researchers re-analyze data from the original study and observe the same results
1. Researchers reuse data from the original study for a new purpose


::: solution

2. Researchers re-analyze data from the original study and observe the same results

:::

:::

## Reproducibility: Some Examples

Let’s consider an example: a researcher is tossing a coin 100 times to check if the coin is fair. They register if they have observed heads or tails after each toss when the coin falls on the floor. Heads are registered as 0 and tails as 1. The sample size of this study is N = 100 (since they are tossing the coin 100 times). 

Hypothesis: The coin is fair (i.e. not biased)\
Sample size: N = 100\
Heads = 0\
Tails = 1\
Analysis method = Student t-test\

After all data is collected (i.e. the researcher is done with the tossing) they start data analysis. They run a simple statistical test in the SPSS program - a Student t-test - to compare the number of observed tails outcomes against the chance level (which is 0.5 since the coin has to sides and if it’s fair, there should be a 50% chance of getting tails). The researcher observes that the number of tails they got is no different from chance - and so they found a support for their original hypothesis. They make the full data table from the study openly available together with the information about the methods and analysis they conducted.

Another researcher downloads the data table and re-runs the exact same analysis in a different software using R programming language. They also observe that the number of tails is no different from chance. **They have reproduced the study!**

A third researcher reads about the reproduced study and decides to conduct a new data analysis on a different coin. They apply the exact same methods (i.e. they toss a coin 100 times and register the outcome every time the coin falls on the floor). Just as in the original study, they mark heads as 0 and tails as 1. They also run a Student t-test on the data and they observe that the number is tails is no different from chance. **They have replicated the study!** 

Note, however, that in many different disciplines the word “reproduced” could be used in both the second and the third researcher case, that is to mean both reproducing and replicating the study.


::: discussion

Could you come up with more examples of reproducible studies in different disciplines or different types of research? What would it take for these studies to be reproduced? 

:::

## Reproducibility Across Methodologies and Research Disciplines

**Quantitative Studies: Computational Reproducibility**

It is defined as “obtaining consistent computational results using the same input data, computational steps, methods, code, and conditions of analysis” ([https://www.nap.edu/catalog/25303](https://www.nap.edu/catalog/25303)). What it means is basically re-running analyses/code with the same data.

**Qualitative Studies: Process Transparency**

Here we mean arriving at a similar (consistent) interpretation by following the same analysis process. This could be obtained by following the step-by-step reasoning and interpretation process of the researcher(s).


::: discussion

Discuss in pairs: Should we use the term “reproducibility” across different disciplines and research methodologies even though it might mean different things?

:::

## Reproducibility and Open Research
**Reproducibility is strongly associated with transparency. **
In order to reproduce others’ studies we need to have access to the methods, data, and analyses that have been conducted. So making data, tools and analyses available is essential for reproducibility. 

**Reproducible does not (have to) mean fully open.**
However, a reproducible project does not have to be fully open. For example, due to privacy or copyright restrictions on methods, data, or analyses, researchers might need to keep parts of the research outputs under controlled access (e.g. available only to other researchers and not publicly available). This should not prevent then, though, from making the project fully reproducible (e.g. internally within their research team). 

**Open does not mean reproducible.**
On the other hand, it is entirely possible to practice open science without following reproducibility principles. Materials, data, tools and code can be made openly available but if they don’t have necessary documentation, instruction on how to use them, error checks, proper versioning and organization - they are most probably not usable, and the project might not be reproducible.

![](fig/image1.png)

## Reproducibility Crisis

Problems with reproducibility of research have been noticed by many researchers, advisors and policy makers in the past several years and led to some even claim that there is a [“Reproducibility crisis”](https://www.nature.com/articles/533452a).
However, not everyone agrees.

[https://www.pnas.org/doi/full/10.1073/pnas.1708272114](https://www.pnas.org/doi/full/10.1073/pnas.1708272114)
[https://bmcresnotes.biomedcentral.com/articles/10.1186/s13104-022-05942-3](https://bmcresnotes.biomedcentral.com/articles/10.1186/s13104-022-05942-3)

**Reasons for Irreproducibility**

- Unavailability of materials, data and/or analyses
- Poor data management
- Unclear analysis specification
- Lack of documentation
- Errors in reporting numbers
- Lack of quality checking procedures
- Insufficient peer review

::: discussion

Do you agree that there is a reproducibility crisis in academic research?\
How many studies would have to reproduce successfully for the “crisis” to be over?\
What could librarians do to help researchers fight the “reproducibility crisis”?\

:::


::: keypoints

- Reproducibility usually means obtaining the same results with the same data.
- Across different disciplines and methodologies, the understanding of what reproducibility means can be very different.
- Reproducible research is not the same as open research - it is important to share research outputs to be able to reproduce others’ studies, but research can be made fully reproducible even if it cannot be made fully open. 
- Recent studies point to many issues with reproducibility across different disciplines, something that has been termed “reproducibility crisis”

:::
