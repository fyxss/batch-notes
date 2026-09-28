---
tags:
  - probability
  - probability-distributions
  - probabilistic-method
---

# Probability Models and Methods

[[05 Bayes Theorem and Naive Bayes|Previous]] · [[00 Probability|Dashboard]] · [[07 Probability Formula and Decision Sheet|Next]]

> [!abstract] Goal
> Work with unequal outcome probabilities, then use probability to prove existence and control algorithmic error.

## 1. Probability distributions

A finite probability distribution assigns a weight $p(s)$ to each outcome $s$ in a sample space $S$.

Two requirements:

$$
0\le p(s)\le1,\qquad \sum_{s\in S}p(s)=1.
$$

The sample space together with these probabilities forms a **probability space**.

For any event $E$:

$$
P(E)=\sum_{s\in E}p(s).
$$

You add the weights of the event's outcomes.

The notation $s\in E$ means “$s$ belongs to $E$,” and $\sum_{s\in E}$ means add once for every outcome in $E$. For $E=\{a,b,c\}$, the formula reads $P(E)=p(a)+p(b)+p(c)$. A **weight** here is just the assigned probability, not a physical mass.

### Worked example: a biased spinner

| Outcome | A | B | C |
|---|---:|---:|---:|
| Probability | 0.5 | 0.3 | 0.2 |

This is valid because the weights are non-negative and sum to 1. The probability of B or C is $0.3+0.2=0.5$, not $2/3$.

If we learn the spinner did not land on A, only B and C remain. Their original weights sum to 0.5, so divide by 0.5 to get the conditional probabilities:

$$
P(B\mid\text{not A})=\frac{0.3}{0.5}=0.6,
\qquad
P(C\mid\text{not A})=\frac{0.2}{0.5}=0.4.
$$

They now sum to 1, while keeping the original 3-to-2 relative weight.

### Uniform distribution

If there are $n$ equally likely outcomes, each receives weight $1/n$. Then

$$
P(E)=\lvert E\rvert\frac1n=\frac{\lvert E\rvert}{\lvert S\rvert}.
$$

So counting favourable outcomes is a special case of adding probability weights.

For three fair independent coin flips, the odd-tail event is $\{HHT,HTH,THH,TTT\}$. Its four outcomes each have weight $1/8$, so its probability is $1/2$.

> [!question] Easy
> Are the proposed weights $0.2,0.3,0.6$ a valid distribution?

> [!success]- Solution
> No: they sum to 1.1, not 1.

> [!question] Easy
> Outcomes A, B, and C have probabilities $0.2$, $x$, and $0.5$. Find $x$.

> [!success]- Solution
> All outcome probabilities must sum to 1:
> $$
> 0.2+x+0.5=1,
> $$
> so $x=0.3$.

> [!question] Medium
> Outcomes A, B, C, D have probabilities $0.1,0.2,0.3,0.4$. Given that the outcome is not A, find the probability it is C or D.

> [!success]- Solution
> The surviving probability mass is $0.9$. C and D carry mass $0.7$, so the conditional probability is $0.7/0.9=7/9$.

## 2. A small bridge: random variables

A **random variable** is a function assigning a number to each outcome. It lets us ask numerical questions about the experiment.

For two fair coin flips, let $X$ count heads:

| Outcome | HH | HT | TH | TT |
|---|---:|---:|---:|---:|
| $X$ | 2 | 1 | 1 | 0 |

The distribution of $X$ is:

$$
P(X=0)=\frac14,\qquad P(X=1)=\frac12,\qquad P(X=2)=\frac14.
$$

Two outcomes produce $X=1$, so their probabilities are added. The equally likely outcomes do not make the three head counts equally likely.

In [[04 Bernoulli Trials and Binomial Distribution]], $X$ counts successes across $n$ trials. The binomial formula describes its distribution.

> [!question] Easy
> For one fair die roll, define $X=1$ if the result is six and $X=0$ otherwise. Give the distribution of $X$.

> [!success]- Solution
> $P(X=1)=1/6$ and $P(X=0)=5/6$. This is a Bernoulli random variable.

## 3. The probabilistic method

To prove an object with a property exists:

1. Describe a random way to choose an object.
2. Show the probability of getting the desired property is positive.
3. Conclude at least one such object exists.

> [!note] Existence from positive probability
> $$
> P(\text{bad})<1
> \ \Longrightarrow\
> P(\text{good})>0
> \ \Longrightarrow\
> \text{at least one good object exists}.
> $$

### Lecture example: a missing bit string

You receive a list of 1,000 length-10 bit strings. There are $2^{10}=1024$ possible strings. Choose one uniformly:

$$
P(\text{on the list})\le\frac{1000}{1024}<1.
$$

Therefore some length-10 string is absent from the list.

The inequality allows repeated entries: 1,000 listed entries might contain fewer than 1,000 distinct strings.

We proved existence without finding the missing string. This resembles [[2. Counting/04 Pigeonhole Principles|pigeonhole proofs]], although the tools differ.

Why is positive probability enough? If no good object existed, the good event would be empty and would have probability zero. Finding $P(\text{good})>0$ rules that out. The method proves existence; it does not necessarily give an efficient way to construct the object.

> [!question] Easy
> A list contains 200 length-8 bit strings. Prove a length-8 string is missing.

> [!success]- Solution
> A uniformly selected string lies on the list with probability at most $200/256<1$. The probability of being absent is positive, so an absent string exists.

### Several bad events: the union bound

From the union rule,

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)\le P(A)+P(B),
$$

because an intersection probability cannot be negative. This upper estimate is the **union bound**. It does not need independence. For several bad events, add their probabilities to bound the chance that at least one happens. If that sum is less than 1, avoiding all bad events has positive probability.

An upper bound of 1 or more does **not** prove that a good object is impossible; the estimate is simply too weak to settle the question.

> [!question] Medium
> A random construction can fail through events A or B. Suppose $P(A)\le0.2$ and $P(B)\le0.3$. Prove a construction avoiding both failures exists, without assuming independence.

> [!success]- Solution
> The union rule gives $P(A\cup B)\le P(A)+P(B)\le0.5$. Thus success has probability at least 0.5, which is positive. At least one successful construction exists.
> This inequality is called the **union bound**.

## 4. Monte Carlo algorithms

A Monte Carlo algorithm uses randomness and returns an answer within its allotted computation, but the answer can have a bounded probability of error.

Randomness is useful when a fast answer with a controlled error risk is preferable to a much more expensive exact computation.

### Independent repetition

An **algorithm** is a step-by-step procedure. A prime is an integer greater than 1 whose only positive divisors are 1 and itself; a composite integer has other divisors. A primality test tries to distinguish the two.

In the lecture's primality-testing model, for a fixed composite input, a round incorrectly passes it with probability at most $1/4$. A composite number is accepted only if **every** round passes.

In this one-sided model, primes pass every round. A failure establishes that the number is composite; passing every round returns “probably prime.” Run the procedure with a fresh random choice each round and reject as soon as a round fails. A **one-sided error** means a composite may pass, but a prime is never rejected under this model.

With fresh independent randomness:

$$
P(\text{composite survives }k\text{ rounds})
\le\left(\frac14\right)^k.
$$

| Rounds | Error bound |
|---|---:|
| 1 | $1/4$ |
| 3 | $1/64$ |
| 5 | $1/1024$ |
| 10 | $1/1{,}048{,}576$ |
| 30 | Approximately $8.67\times10^{-19}$ |

The lecture connects randomized primality testing to finding large prime candidates for RSA.

RSA is a public-key cryptographic system that uses large primes. For this topic, the calculation to learn is the repetition bound, rather than the internal arithmetic of the test or RSA.

> [!warning] What repetition must mean
> Reusing the same random choices can repeat the same mistake. Also, the power bound applies here because an incorrect acceptance requires **all rounds** to err. A general two-sided Monte Carlo algorithm may require a majority vote and a different error analysis.

> [!important] Direction of the guarantee
> The bound is “chance this fixed composite passes the test,” not automatically “chance an accepted candidate is composite.” Reversing that conditional requires information about how candidates are selected.

> [!question] Easy
> Under this model, what is the false-acceptance bound after four independent rounds?

> [!success]- Solution
> $(1/4)^4=1/256$.

> [!question] Medium
> How many independent rounds suffice to make the bound at most $1/1000$?

> [!success]- Solution
> Four rounds give $1/256$, still too large. Five give $1/1024<1/1000$. Therefore five suffice.

The phrase **at most** is essential: $1/4$ is a bound, so $(1/4)^k$ is also a bound, not necessarily the actual error probability. To find the number of rounds without logarithms, keep multiplying the previous bound by $1/4$ until it is at or below the required tolerance. Check the previous round as well to find the smallest $k$ justified by this bound.

## Common mistakes

> [!warning]
> - Counting outcomes instead of adding their weights when the distribution is not uniform.
> - Forgetting to combine all outcomes that give the same random-variable value.
> - Claiming existence when the calculated success probability is only known to be at least zero rather than strictly positive.
> - Raising an error bound to the number of repetitions without fresh independent randomness.
> - Reversing “a bad input passes” into “a passed input is bad” without a Bayes calculation and a prior.

## Check before moving on

- [ ] I check that probabilities are non-negative and sum to 1.
- [ ] I add weights for events with unequal outcomes.
- [ ] I can explain how a random variable groups outcomes by a number.
- [ ] I can turn positive probability into an existence proof.
- [ ] I can state the assumptions behind an algorithm's error bound.

Source: [[Discrete Mathematics Lecture Notes - 33.pdf#page=9|Lecture 33, pp. 9–11]]. The random-variable bridge and union-bound exercise are supporting extensions.
