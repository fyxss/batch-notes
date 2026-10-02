---
aliases:
  - Counting Formula Sheet
  - Counting Decision Sheet
tags:
  - discrete-mathematics
  - counting
  - formula-sheet
  - exam-prep
---

# Counting Formula and Decision Sheet

Navigation: [[04 Pigeonhole Principles|← Prev: Pigeonhole Principles]] · [[Discrete Mathematics/index|Table of Contents]] · [[06 Counting Mixed Practice|Next: 06. Counting Mixed Practice →]]

Use this sheet after the lessons. If a formula feels like a guess, revisit its explanation: [[01 Fundamental Counting Rules|stages, cases, and overcounting]], [[02 Permutations and Combinations|ordered versus unordered selections]], [[03 Generalized Counting|repetition and integer solutions]], or [[04 Pigeonhole Principles|guarantees]].

## Rule selector

| Clue in the problem | Use |
|---|---|
| Complete several stages | Product rule |
| Choose one among disjoint cases | Sum rule |
| Two alternatives overlap | Inclusion–exclusion |
| Count all, then remove unwanted outcomes | Complement counting |
| Every outcome has exactly $d$ descriptions | Division rule |
| Ordered selection without repetition | Permutation |
| Unordered selection without repetition | Combination |
| Ordered positions with repetition | $n^r$ |
| Unordered selection with repetition | Stars and bars |
| Arrange a fixed collection containing duplicates | Multiset permutation |
| Guarantee a repetition or concentration | Pigeonhole principle |

## Core formulas

| Topic | Formula |
|---|---|
| Product rule | $n_1n_2\cdots n_k$ |
| Subsets of an $n$-element set | $2^n$ including the empty set |
| Sum rule | $n_1+n_2+\cdots+n_k$ for disjoint cases |
| Two-set inclusion–exclusion | $\lvert A\cup B\rvert=\lvert A\rvert+\lvert B\rvert-\lvert A\cap B\rvert$ |
| Three-set inclusion–exclusion | $\lvert A\cup B\cup C\rvert=\sum\lvert A\rvert-\sum\lvert A\cap B\rvert+\lvert A\cap B\cap C\rvert$ |
| Complement counting | $\lvert A\rvert=\lvert S\rvert-\lvert\overline A\rvert$ |
| Division rule | $n/d$ when every outcome has exactly $d$ descriptions |
| Factorial | $n!=n(n-1)\cdots1$, and $0!=1$ |
| Full permutation | $n!$ |
| r-permutation | $P(n,r)=\dfrac{n!}{(n-r)!}$ |
| Circular permutation | $(n-1)!$ when rotations are identical |
| Necklace / Keychain | $\dfrac{(n-1)!}{2}$ when reflections are also identical |
| Combination | $\binom nr=\dfrac{n!}{r!(n-r)!}$ |
| Ordered repetition | $n^r$ |
| Unordered repetition | $\binom{n+r-1}{r}$ |
| Multiset permutation | $\dfrac{n!}{n_1!n_2!\cdots n_k!}$ |
| Grid walk $(0,0)\to(m,n)$ | $\binom{m+n}{m}=\dfrac{(m+n)!}{m!\,n!}$ |
| Generalized pigeonhole | Some box has at least $\left\lceil N/k\right\rceil$ objects |
| Minimum to guarantee $m$ in one of $k$ boxes | $k(m-1)+1$ |

In the complement formula, $S$ is the set of all allowed outcomes and $\overline A=S\setminus A$ consists of the outcomes outside $A$.

> [!important] Conditions belong to the formulas
> - Product rule: each stage has the same stated choice count for every valid earlier history.
> - Permutations/combinations without repetition: distinct objects, integers $0\le r\le n$.
> - Circular permutations: $n\ge1$ distinct objects, rotations identical, reflections different, no labelled-seat restrictions.
> - Stars and bars: $n\ge1$ named types/groups, $r\ge0$ identical units, no upper bounds.
> - Pigeonhole: $k\ge1$. The minimum formula assumes unrestricted placement; finite supplies must permit the worst-case distribution.

## Selection matrix

| | Repetition forbidden | Repetition allowed |
|---|---:|---:|
| **Order matters** | $P(n,r)$ | $n^r$ |
| **Order does not matter** | $\binom nr$ | $\binom{n+r-1}{r}$ |

## Integer-solution formulas

For $x_1+x_2+\cdots+x_n=r$:

| Restriction | Number of solutions |
|---|---:|
| $x_i\ge0$ | $\binom{n+r-1}{n-1}$ |
| $x_i\ge1$ | $\binom{r-1}{n-1}$ |
| $x_i\ge a_i$ | Set $y_i=x_i-a_i$, then count non-negative solutions |

For positive solutions, $r\ge n$ is required; otherwise the count is zero. With integer lower bounds, use the remaining total $R=r-\sum_i a_i$. If $R<0$, there are no solutions; otherwise there are $\binom{R+n-1}{n-1}$.

Here $\sum_i a_i=a_1+\cdots+a_n$: add all the required minimums. For an upper bound, count unrestricted solutions and remove forbidden ones; see [[03 Generalized Counting#A simple upper bound: subtract the forbidden solutions|the worked subtraction example]].

## Fast exam checklist

1. Define exactly what one outcome is.
2. Mark the words **and**, **or**, **ordered**, **distinct**, **at least**, and **guarantee**.
3. Ask whether order matters.
4. Ask whether repetition is allowed.
5. Check whether cases overlap.
6. Check whether identical objects create duplicate descriptions.
7. Write the symbolic count before calculating.
8. Test the result on a tiny version of the problem.

## Common translations

| Phrase | First idea to try |
|---|---|
| “and” | Product rule |
| “or” | Sum rule; check overlap |
| “at least one” | All minus none |
| “exactly $r$ selected, order matters” | $P(n,r)$ |
| “team / committee / subset / hand” | $\binom nr$ |
| “code / ranking / schedule / sequence” | Ordered count |
| “identical objects among named groups” | Stars and bars |
| “letters of a word with repeats” | Multiset permutation |
| “must”, “guarantee”, “at least two share” | Pigeonhole |

> [!warning] Final sanity checks
> - Does the answer exceed the count of all unrestricted outcomes?
> - Did you treat a code with leading zero differently from an integer?
> - If you divided, does every outcome really have the same number of descriptions?
> - If you added, are the cases disjoint?
> - If you used stars and bars, are the objects identical and are upper bounds absent?

---

Navigation: [[04 Pigeonhole Principles|← Prev: Pigeonhole Principles]] · [[Discrete Mathematics/index|Table of Contents]] · [[06 Counting Mixed Practice|Next: 06. Counting Mixed Practice →]]
