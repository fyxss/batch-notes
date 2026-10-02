---
tags:
  - probability
  - formula-sheet
  - exam-prep
---

# Probability Formula and Decision Sheet

[[06 Probability Models and Methods|← Prev: Probability Models & Methods]]


Use this sheet for recall after the lessons. Explanations and worked examples are in [[01 Probability Foundations|sample spaces]], [[02 Probability Rules and Puzzles|rules and trees]], [[03 Conditional Probability and Independence|conditioning]], [[04 Bernoulli Trials and Binomial Distribution|binomial trials]], [[05 Bayes Theorem and Naive Bayes|Bayes]], and [[06 Probability Models and Methods|distributions and algorithms]].

## Choose the method

| Wording or structure | First method to try |
|---|---|
| Equally likely possibilities | Count favourable / total |
| At least one | Complement: 1 − none |
| A or B | Union rule; subtract overlap |
| A and then B | Multiply conditional branch probabilities |
| Given B | Restrict to B; divide by $P(B)$ |
| Independent stages | Multiply unchanged probabilities |
| Exactly $k$ successes in fixed independent trials | Binomial, if success probability is constant |
| Cause given observed evidence | Bayes |
| Several possible sources of evidence | Total probability |
| Several class features | Naive Bayes, if conditional independence is assumed |
| Fair split of interrupted game stakes | Fictitious rounds tree; divide pot by victory probabilities |
| Unequally likely outcomes | Add outcome weights |
| Prove an object exists | Show positive probability |
| Repeated randomized test | Identify the error event and repetition assumptions |

## Core formulas

| Rule | Formula / condition |
|---|---|
| Equally likely outcomes | $P(E)=\lvert E\rvert/\lvert S\rvert$ |
| Complement | $P(\overline E)=1-P(E)$ |
| Union | $P(E\cup F)=P(E)+P(F)-P(E\cap F)$ |
| Disjoint union | $P(E\cup F)=P(E)+P(F)$ |
| Exactly one of two events | $P(E)+P(F)-2P(E\cap F)$ |
| Conditional | $P(E\mid F)=P(E\cap F)/P(F)$, $P(F)>0$ |
| General multiplication | $P(E\cap F)=P(E)P(F\mid E)$ |
| Independence | $P(E\cap F)=P(E)P(F)$ |
| Jointly independent events | $P(\bigcap_i E_i)=\prod_iP(E_i)$; joint independence must be given or established |
| Binomial | $P(X=k)=\binom nkp^k(1-p)^{n-k}$ |
| At least one success | $1-(1-p)^n$ for independent constant-$p$ trials |
| Bayes | $P(F\mid E)=P(E\mid F)P(F)/P(E)$ |
| Diagnostic metrics | $\text{Sensitivity}=P(+\mid D)$, $\text{Specificity}=P(-\mid\overline D)$, $\text{FPR}=1-\text{Spec}$ |
| Fair split (needs $r, s$ wins) | Fictitious rounds: at most $r+s-1$ trials; split by win probabilities |
| Total probability | $P(E)=\sum_iP(E\mid F_i)P(F_i)$ for a partition |
| General event probability | $P(E)=\sum_{s\in E}p(s)$ |
| Existence | $P(\text{good})>0\Rightarrow$ a good object exists |

Conditional expressions require positive-probability conditioning events.

The counting ratio requires a finite, nonempty, equally likely sample space. A partition means disjoint cases covering all possibilities. For binomial probabilities, $n$ is a non-negative integer, $0\le k\le n$, and $0\le p\le1$; the four model conditions are listed below. At $p=0$ or $p=1$, the success count is certain.

$\sum$ means add the terms; $\prod$ means multiply them; $\bigcap$ means all the indicated events occur. Joint independence requires the product equation for **every subcollection**, not only the full set of events.

## Formulas worth recognizing

Two-case Bayes:

$$
P(F\mid E)=
\frac{P(E\mid F)P(F)}
{P(E\mid F)P(F)+P(E\mid\overline F)P(\overline F)}.
$$

Generalized Bayes:

$$
P(F_j\mid E)=\frac{P(E\mid F_j)P(F_j)}
{\sum_iP(E\mid F_i)P(F_i)}.
$$

Birthday match, independent uniform 365-day model, $1\le n\le365$:

$$
1-\prod_{j=0}^{n-1}\frac{365-j}{365}.
$$

Naive Bayes, conditionally independent features:

$$
a=P(S)\prod_iP(E_i\mid S),\quad
b=P(\overline S)\prod_iP(E_i\mid\overline S),\quad
P(S\mid E_1\cap\cdots\cap E_k)=\frac a{a+b}.
$$

Here $a+b>0$ is required. The feature-independence assumption applies within both classes.

Union bound and the probabilistic method:

$$
P(A_1\cup\cdots\cup A_m)\le\sum_{i=1}^{m}P(A_i).
$$

If the $A_i$ are bad events and their probability sum is less than 1, an outcome avoiding them all exists. Independence is not required.

For a fixed bad input, if independent rounds each falsely pass with probability at most $q$, and acceptance requires **all** rounds to pass, the false-acceptance bound after $k$ rounds is $q^k$. This is not automatically the probability that an accepted input is bad.

## Four distinctions that prevent most mistakes

| These differ | Why |
|---|---|
| Independent and disjoint | Unchanged chances versus inability to occur together |
| Pairwise and joint independence | Every pair can be independent even when the whole collection is not |
| $P(A\mid B)$ and $P(B\mid A)$ | Different conditioning groups |
| Equally likely outcomes and equally likely totals | Several outcomes can produce one total |

## Binomial checklist

- [ ] Fixed number of trials.
- [ ] Two categories per trial.
- [ ] Independent trials.
- [ ] Same success probability each time.

## Final answer checklist

1. State the sample space or events.
2. State replacement and independence assumptions.
3. Write a symbolic expression before substituting numbers.
4. Include every route to the desired event.
5. Check that the answer lies between 0 and 1.
6. Convert decimals to percentages correctly: $0.002=0.2\%$, not $2\%$.
7. Round at the end.

---

[[08 Probability Mixed Practice|Next: 08. Probability Mixed Practice →]]
