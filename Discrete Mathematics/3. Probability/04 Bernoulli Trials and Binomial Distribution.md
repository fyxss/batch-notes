---
tags:
  - probability
  - binomial-distribution
---

# Bernoulli Trials and Binomial Distribution

[[03 Conditional Probability and Independence|Previous]] · [[00 Probability|Dashboard]] · [[05 Bayes Theorem and Naive Bayes|Next]]

> [!abstract] Goal
> Find the probability of a specified number of successes in repeated trials.

## 1. Bernoulli trial

A Bernoulli trial has two outcome categories: **success** and **failure**.

These are labels, not judgments. “A packet is lost” can be called success if that is what we are counting.

$$
P(\text{success})=p,\qquad P(\text{failure})=q=1-p.
$$

A die roll can be treated as a Bernoulli trial when success means “roll a six” and failure means “anything else.” There are six elementary outcomes but just two categories.

> [!question] Easy
> Success means rolling an even number on a fair die. What are $p$ and $q$?

> [!success]- Solution
> Three of six faces are even: $p=1/2$, $q=1/2$.

## 2. When the binomial model fits

Check all four conditions:

1. A **fixed number** $n$ of trials.
2. Two categories per trial: success/failure.
3. Trials are **independent**.
4. The success probability $p$ is **the same** on every trial.

Let $X$ be the number of successes. We write $X\sim\operatorname{Bin}(n,p)$.

Here $X$ is a **random variable**: a number calculated from the outcome. For example, if success means heads, then HTH gives $X=2$. The notation $\sim\operatorname{Bin}(n,p)$ is read “has a binomial distribution with parameters $n$ and $p$.” The possible counts are $0,1,\ldots,n$, and $P(X=k)$ means “the probability that the count equals $k$.”

> [!tip] Translate the words before using a formula
> 1. Define exactly what counts as a success.
> 2. Record $n$, $p$, and the requested success count or range.
> 3. Check the four binomial conditions.
> 4. Decide whether to use one term, add several terms, or use a complement.

You may label either outcome as success. Choose the one that makes $X$ match the question. If success means “defective,” then $p$ is the defect probability; if success means “working,” then $p$ is the working probability.

> [!warning] A changing pool usually fails the test
> Drawing cards without replacement changes the chance of success **conditional on earlier draws**. Use combinations or conditional multiplication rather than automatically applying the binomial formula. Equal individual chances alone do not establish independence.

> [!question] Medium
> Are these binomial experiments?
> 1. Count sixes in 10 independent rolls of a fair die.
> 2. Count aces in five draws without replacement.
> 3. Flip a coin until the first head, counting flips.

> [!success]- Solution
> 1. Yes: fixed $n=10$, independent, constant $p=1/6$.
> 2. No: the pool and conditional success probabilities change.
> 3. No: the number of trials is not fixed beforehand.

## 3. Derive the formula

Find the probability of exactly two heads in five independent flips of a coin with heads probability $p$.

One particular sequence, HHTTT, has probability

$$
p^2(1-p)^3.
$$

Every sequence with two heads has this same probability. Choose the two head positions in $\binom52$ ways. Different sequences are mutually exclusive, so add their equal probabilities:

$$
P(X=2)=\binom52p^2(1-p)^3.
$$

> [!note] Binomial formula
> For $k=0,1,\ldots,n$,
> $$
> P(X=k)=\binom nkp^k(1-p)^{n-k}.
> $$
> **Choose the success positions × probability of one such sequence.**

The lecture also writes this as $b(k;n,p)$.

For $0<p<1$, use the formula directly. At the endpoints, reasoning is simpler: if $p=0$, then $X=0$ certainly; if $p=1$, then $X=n$ certainly. Counts outside $0,\ldots,n$ have probability zero.

The probabilities for $k=0,1,\ldots,n$ form a complete distribution. The symbol $\sum_{k=0}^{n}$ below means “add the term once for each $k$ from 0 through $n$”:

$$
\sum_{k=0}^{n}\binom nkp^k(1-p)^{n-k}
=(p+(1-p))^n=1
$$

This is the **binomial theorem** in action: expanding $(a+b)^n$ chooses either $a$ or $b$ from each of $n$ factors. Choosing $a$ from exactly $k$ factors can be done in $\binom nk$ ways, producing the term $\binom nk a^k b^{n-k}$. Here $a=p$ and $b=1-p$, so their sum is 1. Equivalently, one of the success counts must occur, so their probabilities must add to 1.

### Worked examples from the lecture

For exactly four heads in seven independent flips, with $p=2/3$:

$$
P(X=4)=\binom74\left(\frac23\right)^4\left(\frac13\right)^3
=\frac{560}{2187}\approx0.2561.
$$

For exactly eight zeros in ten independent bits, each zero having probability $0.9$:

$$
P(X=8)=\binom{10}{8}(0.9)^8(0.1)^2\approx0.1937.
$$

> [!question] Easy
> Find the probability of exactly two heads in four fair independent coin flips.

> [!success]- Solution
> $\binom42(1/2)^4=6/16=3/8$.

> [!question] Medium
> Each of five independent requests succeeds with probability $0.8$. What is the probability exactly four succeed?

> [!success]- Solution
> $\binom54(0.8)^4(0.2)=0.4096$. The factor 5 chooses which request fails.

## 4. Exactly, at most, and at least

| Wording | Event |
|---|---|
| Exactly $k$ | $X=k$ |
| At most $k$ | $X=0,1,\ldots,k$ |
| At least $k$ | $X=k,k+1,\ldots,n$ |
| More than $k$ | $X=k+1,\ldots,n$ |
| Fewer than $k$ | $X=0,1,\ldots,k-1$ |

Add the probabilities of the permitted values:

$$
P(X\le k)=\sum_{j=0}^{k}\binom njp^j(1-p)^{n-j}.
$$

For an upper tail, a complement may be shorter:

$$
P(X\ge k)=1-P(X\le k-1).
$$

In particular,

$$
P(X\ge1)=1-(1-p)^n.
$$

### Worked example: a complete small distribution

Make three independent attempts, each with success probability $0.6$. Then $X\sim\operatorname{Bin}(3,0.6)$:

| Count $k$ | Calculation | Probability |
|---|---|---:|
| 0 | $\binom30(0.6)^0(0.4)^3$ | 0.064 |
| 1 | $\binom31(0.6)^1(0.4)^2$ | 0.288 |
| 2 | $\binom32(0.6)^2(0.4)^1$ | 0.432 |
| 3 | $\binom33(0.6)^3(0.4)^0$ | 0.216 |

The four probabilities sum to 1. “At least two” includes 2 and 3 successes, so $P(X\ge2)=0.432+0.216=0.648$. The complement gives the same result: $1-(0.064+0.288)=0.648$.

> [!question] Medium · A range with a biased coin
> Flip a coin four times independently with heads probability $0.3$. Find the probability of fewer than two heads.

> [!success]- Solution
> Let $X$ count heads, with $n=4$ and $p=0.3$. “Fewer than two” means zero or one:
> $$
> P(X<2)=(0.7)^4+\binom41(0.3)(0.7)^3
> =0.2401+0.4116=0.6517.
> $$
> These two counts cannot occur together, so add their probabilities.

> [!question] Easy
> Each of three independent attempts succeeds with probability $0.6$. Find the probability of at least one success.

> [!success]- Solution
> $1-0.4^3=0.936$.

> [!question] Medium
> In five fair independent coin flips, find the probability of at most one head.

> [!success]- Solution
> Add zero heads and one head:
> $$
> \frac{\binom50+\binom51}{2^5}=\frac6{32}=\frac3{16}.
> $$

## 5. Why a perfect split is not very likely

In 100 fair independent flips:

$$
P(X=50)=\frac{\binom{100}{50}}{2^{100}}\approx0.07959.
$$

In 10 fair independent flips:

$$
P(X=5)=\frac{\binom{10}{5}}{2^{10}}\approx0.2461.
$$

Exactly half heads is the most likely **single head count** in each experiment, but there are many other counts. “Near half” includes many possibilities; “exactly half” includes only one count.

> [!question] Medium
> In four fair independent flips, compare exactly two heads with between one and three heads inclusive.

> [!success]- Solution
> Exactly two: $\binom42/16=6/16$.
> Between one and three: $(\binom41+\binom42+\binom43)/16=14/16$.
> A range of counts can be much more likely than one exact count.

## Common mistakes

> [!warning]
> - Forgetting $\binom nk$ and counting just one sequence.
> - Using the binomial formula without independence or constant $p$.
> - Confusing $p$ (one-trial chance) with $P(X=k)$ (a whole-experiment chance).
> - Treating “at least $k$” as “exactly $k$.”
> - Subtracting $P(X\le k)$ when you need $P(X\le k-1)$.

## Check before moving on

- [ ] I can define success and identify $n$, $p$, and $k$.
- [ ] I check all four binomial conditions before using the formula.
- [ ] I can explain the factor $\binom nk$.
- [ ] I translate “at most” and “at least” into a range of $X$ values.
- [ ] I choose a complement only when it shortens the calculation.

Source: [[Discrete Mathematics Lecture Notes - 30, 31, 32.pdf#page=12|Lectures 30–32, pp. 12–14]].
