---
aliases:
  - Probability
  - Probability Dashboard
tags:
  - discrete-mathematics
  - probability
  - exam-prep
---

# Probability

> [!quote] The central idea
> **Describe what can happen, assign each outcome its chance, then add the chances of the outcomes you want.**

Counting tells us how many possibilities exist. Probability tells us how likely an event is. When outcomes are equally likely, probability is one counting problem divided by another.

## Learning path

1. [[01 Probability Foundations]] — outcomes, events, and fair counting.
2. [[02 Probability Rules and Puzzles]] — complements, unions, trees, and classic puzzles.
3. [[03 Conditional Probability and Independence]] — what changes when you learn something.
4. [[04 Bernoulli Trials and Binomial Distribution]] — repeated success/failure experiments.
5. [[05 Bayes Theorem and Naive Bayes]] — reason backward from evidence.
6. [[06 Probability Models and Methods]] — unequal probabilities, existence proofs, and randomized algorithms.
7. [[07 Probability Formula and Decision Sheet]] — fast revision.
8. [[08 Probability Mixed Practice]] — solve without being told the rule.

~~~mermaid
flowchart TD
    A["Foundations"] --> B["Probability rules"]
    B --> C["Conditional probability and independence"]
    C --> D["Bernoulli trials and binomial distribution"]
    C --> E["Bayes and naive Bayes"]
    D --> F["Probability models and methods"]
    E --> F
    F --> G["Mixed practice"]
~~~

## Before you start

Refresh [[Counting/00 Counting|Counting]] if factorials, permutations, combinations, or inclusion–exclusion feel unfamiliar.

> [!tip] The five-question routine
> 1. What is one outcome?
> 2. Are those outcomes equally likely?
> 3. What event am I trying to find?
> 4. Has anything been given or observed?
> 5. Are the stages independent, or must later chances change?

## Notation

| Symbol | Meaning |
|---|---|
| $S$ | Sample space: all outcomes |
| $E,F$ | Events: sets of outcomes |
| $P(E)$ | Probability of event $E$ |
| $\overline E$ | Event $E$ does not occur |
| $E\cup F$ | $E$ or $F$ or both |
| $E\cap F$ | Both $E$ and $F$ |
| $P(E\mid F)$ | Probability of $E$, given $F$ occurred |
| $\binom nk$ | Number of ways to choose $k$ positions from $n$ |

The PDFs use lowercase $p(E)$; these notes use $P(E)$. They mean the same thing. In the Counting notes, $P(n,r)$ means a permutation count; its two numerical arguments distinguish it from event probability.

### Reading compact formulas

$\sum$ means **add**, while $\prod$ means **multiply**. The index below the symbol tells you where to start; the number above tells you where to stop:

$$
\sum_{i=1}^{3}a_i=a_1+a_2+a_3,
\qquad
\prod_{i=1}^{3}a_i=a_1a_2a_3.
$$

The index $i$ is just a counter. $\bigcap_{i=1}^{3}E_i=E_1\cap E_2\cap E_3$ means that all three events occur. $\approx$ means approximately equal; keep exact fractions or full calculator precision until the final rounding.

## How to study

Read one section, redo its worked example with the solution hidden, then try its practice questions. Click a collapsed **Solution** callout to check your reasoning. Use Obsidian Reading view for the cleanest presentation.

Work through lessons 01–06 in order, then use 07 to revise and 08 to check whether you can choose the method yourself. A successful solution should explain **what is counted or conditioned on**, **why the rule applies**, and **what the answer means**. If you get stuck, the return links in the mixed-practice mastery tracker point to the relevant lesson.

- [ ] I can build an equally likely sample space.
- [ ] I can select and combine probability rules.
- [ ] I can distinguish independence from disjointness.
- [ ] I can recognize a binomial experiment.
- [ ] I can calculate and explain a Bayesian update.
- [ ] I can explain a probabilistic existence proof and error reduction.
- [ ] I have completed the mixed practice.

## Sources and scope

- [[Discrete Mathematics Lecture Notes - 30, 31, 32.pdf]] — teaching sections, pp. 3–14.
- [[Discrete Mathematics Lecture Notes - 33.pdf]] — teaching sections, pp. 2–11.
- [[Study Roadmap - Discrete Mathematics]]
- [[Exam Topics - Discrete Mathematics]]

The explanations and additional exercises are written for this vault. The notes make assumptions explicit where the slides use a simplified model.

> [!note] About random variables
> Lecture 33 mentions random variables in its title but does not develop them in a dedicated section. Lesson 04 introduces the success-count variable when it is needed; [[06 Probability Models and Methods]] expands that idea to other numerical descriptions of outcomes. Expected value and variance are outside the supplied material.
