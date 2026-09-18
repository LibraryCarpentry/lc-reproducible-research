---
title: 'Understanding Reproducibility'
teaching: 14
exercises: 12
---

:::::::::::::::::::::::::::::::::::::: questions

- What do we mean by reproducibility?
- Does reproducibility mean different things in different disciplines?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what research reproducibility is, and distinguish it from replicability and generalization
- Contrast computational reproducibility with transparency of qualitative analysis

::::::::::::::::::::::::::::::::::::::::::::::::

This episode asks a single question: how would you know whether a result can be checked, and what counts as evidence that it has been? The next episode applies that question to openness and a running case; here, we build the vocabulary.

## Reproducibility: Some Definitions

**Reproducibility**: Obtaining the same results using the same data and the same analysis steps.

**Replicability**: Achieving similar results with new data, using the same analysis steps to answer the same question.

Research is **reproduced** when results are consistent when following the same method and analysis steps with the same input data

Research is **replicated** when results are consistent across studies that answer the same research question, each of which has obtained its own data

Research results are **generalized** when results apply in other contexts or populations that differ from the original one

[Source](https://www.nap.edu/catalog/25303)

![2x2 matrix of reproduced, replicated, robust, and generalized results](fig/epi1.png){alt="A 2x2 matrix crossing whether the data is the same or different (columns) with whether the analysis is the same or different (rows). Same data and same analysis is labeled Reproduced. Different data and same analysis is labeled Replicated. Same data and different analysis is labeled Robust. Different data and different analysis is labeled Generalized."}

**Robust** means a finding persists when reasonable, defensible changes are made to the analysis - a different but equally valid statistical test, for example. This matrix is a simplified organizing aid, not an exhaustive definition: generalization in particular is really about how far a finding's applicability extends, not just about changing both the data and the analysis at once.

Based on: [The Turing Way: Overview of reproducibility definitions](https://the-turing-way.netlify.app/reproducible-research/overview/overview-definitions.html)

::: challenge

## Which of these describes a reproduced study? (optional, ~3 min)

1. Researchers apply similar methods to the original study in a new study
1. Researchers re-analyze data from the original study, using the original analysis steps, and observe the same results
1. Researchers reuse data from the original study for a new purpose

Explain your answer in one sentence: what specifically stayed the same?

::: solution

2. Researchers re-analyze data from the original study and observe the same results. What stayed the same: the original data and the original analysis method - only the fact that someone else redid the analysis is new.

:::

:::

## Reproducibility: Some Examples

Let us consider an example: a researcher is tossing a coin 100 times to check how often it lands on tails. They register heads or tails after each toss. Heads are registered as 0 and tails as 1. The sample size of this study is N = 100 (since they are tossing the coin 100 times).

```
Sample size: N = 100
Heads = 0
Tails = 1
Analysis method = Count of tails, divided by total tosses
```

After all data is collected, the researcher calculates the proportion of tails: 53 tails out of 100 tosses, or 53%. The researcher makes the complete data table and detailed methods available to the public.

Another researcher downloads the data table and re-runs the exact same calculation in a different software, using the R programming language. They also get 53%. **They have reproduced the study** - same data, same calculation, same result.

A third researcher reads about the reproduced study and decides to investigate the same question with the same coin. They apply the exact same method: toss the coin 100 more times, register heads as 0 and tails as 1, and calculate the proportion of tails. This time they get 49 tails out of 100, or 49%. **This is a replication attempt** - new data, same method, same question. Whether 49% "counts" as corroborating the first result is a judgment call, not an automatic yes or no; replication attempts do not always land on an identical number, and that is expected.

Note, however, that in many different disciplines the word "reproduced" could be used in both the second and the third researcher case, that is to mean both reproducing and replicating the study.

Matching calculations demonstrate reproducibility; they do not by themselves establish that the study's methods or conclusions are sound.

::: challenge

## Reproduced, replicated, or generalized? (~5 min)

For each scenario below, decide whether it describes reproducing, replicating, or generalizing a result. For each, name what stayed the same and what changed.

1. A team re-runs a colleague's published analysis script on the exact same dataset and gets the same numbers.
2. A team collects new survey data using the same questionnaire and analysis method, and finds a similar pattern of responses.
3. A team that found an effect in a lab study finds the same effect holds in a real-world field setting with a different population.

::: solution

1. Reproduced - same data, same method; nothing changed except who ran it.
2. Replicated - same method and question, but new data.
3. Generalized - the result was shown to extend to a different context/population, using a different setting rather than the original lab conditions.

:::

:::

::: discussion

(optional, ~5 min)

Can you provide additional examples of reproducible studies from various disciplines or research types?

:::

## Reproducibility Across Methodologies and Research Disciplines

**Quantitative** research analyzes numerical measurements; **qualitative** research analyzes meaning in non-numerical material such as interviews or documents; **computational** means carried out by a computer.

### Quantitative Studies: Computational Reproducibility

It is defined as "obtaining consistent computational results using the same input data, computational steps, methods, code, and conditions of analysis" ([https://www.nap.edu/catalog/25303](https://www.nap.edu/catalog/25303)). What it means is basically re-running analyses/code with the same data.

### Qualitative Studies: Process Transparency

For this lesson, qualitative transparency means documenting how material was selected, coded, and interpreted so another researcher can trace and critically assess the reasoning - not that they necessarily arrive at the same **interpretation** (the researcher's explanation of what the evidence means). Two researchers can trace the same evidence and reasonably interpret it differently; what matters is that the path to the interpretation is visible and can be scrutinized.

::: discussion

(~5 min)

What would you inspect to check a quantitative result, like a survey calculation? What would you inspect to trace a qualitative interpretation, like an analysis of interview transcripts? Discuss in pairs how these two kinds of checking differ.

:::

::: keypoints

- Reproducibility usually means obtaining the same results with the same data and the same analysis steps.
- Across different disciplines and methodologies, the understanding of what reproducibility means can be very different.

:::
