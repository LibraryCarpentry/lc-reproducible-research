# Validation request: a cross-episode narrative scenario for a Library Carpentry lesson

## What this is

I maintain a Carpentries Workbench lesson called **"Reproducible Research Workflows"** (Library Carpentry, life cycle: alpha). It teaches library and research-support staff (not researchers themselves) what reproducibility means and how they can support it. It has no programming or statistics prerequisite. The lesson has five episodes, taught in this order:

1. **Introduction** (15 min teaching / 8 min exercises) — frames the lesson, distinguishes reproducibility from open science.
2. **What is Reproducible Research?** (20/20) — defines reproducibility vs. replicability vs. generalization, covers the "reproducibility crisis" debate.
3. **Benefits and Challenges of Reproducibility** (10/10) — benefits to science and to individual researchers; common obstacles (time, skills, legal/ethical restrictions, technical barriers) and how library support addresses each.
4. **Tools for Reproducible Research Workflows** (25/15) — a tour of ~17 tools mapped onto three workflow stages (data collection/processing, analysis, writing/reporting).
5. **The Role of Libraries in Supporting Reproducibility** (15/8) — what library staff can realistically offer, scoped deliberately so it doesn't read as "one librarian does everything."

Two learner profiles define the target audience:

> **Priya, Research Data Librarian** — two years' experience, fields DMP questions from grad students/faculty, comfortable with data management concepts and basic Git, **no background in research methodology or statistics**, has not previously encountered terms like "active citation" or "code capsule." Wants confident conversations about *why* reproducibility matters, not just tool pointers.

> **Marcus, Liaison Librarian** — supports humanities/social science departments at a mid-sized university, has taught a few Software Carpentry workshops but hasn't worked directly with quantitative researchers on reproducibility, is scoping a possible "open and reproducible research" workshop series at his own library, wants to know realistically what his library could and couldn't offer without hiring new staff.

## The problem

A community pilot (UMass Amherst, June 2026) generated real instructor observation notes. Two comments are driving this request:

> "Could add reviews of different tools rather than training attendees on how to use the tools."

> [From the observer, on Episode 4] "Amount of time used to teach each section... Tools for Reproducible Research Workflows: 15 M (10:23am-10:38am); 6M (9M on discussion)" — i.e. the tools episode ran fast and thin relative to how dense its content is on the page.

A separate automated pedagogy review (an LLM-based checker I run against this lesson) independently flagged the same episode:

> "The episode is essentially an undigested list of roughly seventeen tools in 20 minutes of teaching. That is well over a tool a minute, with no worked example of any of them... Learners are then asked in Exercise 1 to advise someone on completing a README they have never been walked through."

My own read: episode 4 (Tools) is currently a reference list with small bolted-on exercises (a sorting task, a "which tool would you reach for" multiple-choice item) rather than anything that has learners *use* multiple tools together on one continuum. I think the fix is a single small fictional research scenario/case study that threads across episodes 2-5, so that by the time learners reach the Tools episode they're not meeting a bare tool inventory — they're picking tools **for a project they already know the shape of**, and the Library Carpentry episode can close the loop by asking what library support that same fictional project would need.

## Current tool inventory (Episode 4, verbatim)

```
### 1. Data Collection and Processing
- README files – describes datasets and folder structure
- Codebooks – define variables, labels, and units
- Electronic Lab Notebooks (ELNs) – digital logs for lab work (Jupyter as notebook interface, or LabArchives)

### 2. Data Analysis
#### Quantitative
- R, Python, SPSS Syntax – scripting and transparency
- Git – version control
- Code quality tools (The Turing Way link)
- Environment management – renv (R-specific dependency lockfile) or full containers (Docker)
- Code Ocean – "code capsules" (code + data + environment bundled)

#### Qualitative
- Annotations – NVivo or ATI
- Active Citation – claims link directly to supporting source passages

### 3. Writing and Reporting
- R Markdown, Quarto, Jupyter Notebooks, HackMD, Overleaf
```

Episode 4's current objectives are: identify key workflow stages; list at least four tools that support reproducibility; describe, for a documentation tool and a version-control tool, one specific task it would be used for.

Episode 2 already has a running example: a researcher tossing a coin 100 times to test fairness, used to teach reproduced/replicated/generalized. It is *not* currently reused in later episodes.

## What's already decided — do not relitigate

- The audience stays library/research-support staff, not researchers or programmers. Any scenario must be usable by someone with Marcus's or Priya's background — no scenario requiring the learner to already know a stats test, a specific language, or Git internals.
- Each episode's existing questions/objectives (listed above) are fixed for this round; the scenario should serve them, not replace them.
- The Tools episode's "no one librarian is expected to do everything" framing in Episode 5 is a deliberate, pilot-driven scope correction — a new scenario must not reintroduce "the librarian personally runs/reproduces the analysis" as an implied expectation.
- Episode length is already a concern (Episode 4 alone is 25 min teaching / 15 min exercises after recent edits); whatever is proposed should identify what it would let us **cut** from the current 17-tool list, not just add on top.

## What I want challenged, not just answered

1. **Is a single continuous narrative across 4 episodes even the right call**, versus a fresh short vignette per episode, or reusing the Episode 2 coin-toss example instead of inventing a new one? What's the failure mode of each approach for a mixed-experience adult audience in a single workshop day?
2. **What research domain/discipline should the scenario use** so it reads as realistic to both a humanities/social-science liaison (Marcus) and a general research-data librarian (Priya), without requiring stats or programming background to follow, and without being so generic it can't motivate concrete tool choices (e.g., something has to be quantitative enough to make Git/renv/codebooks relevant, and something has to leave room for a qualitative angle given the lesson explicitly covers qualitative tools)?
3. **Concretely draft the scenario**: a short paragraph describing the fictional researcher/project, then for each of episodes 2-5, one short beat showing how the same project surfaces that episode's concept (definitions in ep. 2, a benefit/challenge in ep. 3, 2-3 tool choices with justification in ep. 4, one library-support ask in ep. 5). Keep total added reading across all four episodes under ~250 words plus 1-2 short exercise prompts per episode.
4. **What's the cognitive-load risk** of asking learners to track one fictional project across 90+ minutes of a workshop that also covers unrelated conceptual material (the reproducibility-crisis debate, benefit/challenge lists)? Would you scope the narrative down to just episodes 4-5 instead of 2-5, and why?
5. **Given the current tool list, what would you cut** to make room for scenario-driven practice, and what's your reasoning for what stays vs. goes (e.g., is SPSS Syntax, HackMD, or ATI more or less essential to keep than Git, README files, or a codebook)?
6. Rate your confidence in the recommended approach (narrative scope, domain choice, what to cut) on a 1-5 scale, and flag anything here you think is a bad premise rather than answering it as asked.
