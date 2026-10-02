---
---

# Probability Mixed Practice

[[07 Probability Formula and Decision Sheet|← Prev: Probability Formula Sheet]]


> [!tip] Try before revealing
> For each question, name the event, choose a method, and write the expression. Then open the solution. All card questions use a standard 52-card deck; all stated fair dice and coins are rolled or tossed independently unless specified otherwise.

## Round 1 — sample spaces and rules

> [!question] 1 · Easy
> Roll two fair dice. Find the probability of a sum of 8.

> [!success]- Solution
> The five pairs are $(2,6),(3,5),(4,4),(5,3),(6,2)$. Probability: $5/36$.

> [!question] 2 · Easy
> Toss a fair coin four times. Find the probability of at least one tail.

> [!success]- Solution
> Subtract all heads: $1-(1/2)^4=15/16$.

> [!question] 3 · Medium
> Draw one card. Find the probability it is a queen or a spade.

> [!success]- Solution
> Subtract the queen-of-spades overlap: $(4+13-1)/52=4/13$.

> [!question] 4 · Medium
> A bag has 4 red and 3 blue balls. Draw twice without replacement. Find the probability of exactly one red.

> [!success]- Solution
> Red-blue or blue-red:
> $(4/7)(3/6)+(3/7)(4/6)=4/7$.

## Round 2 — conditioning and independence

> [!question] 5 · Easy
> A die result is known to be odd. What is the probability it exceeds 3?

> [!success]- Solution
> The surviving outcomes are 1, 3, 5. Only 5 exceeds 3: $1/3$.

> [!question] 6 · Medium
> Two fair dice have a sum of 8. What is the probability at least one shows 6?

> [!success]- Solution
> Of the five sum-8 pairs, $(2,6)$ and $(6,2)$ qualify: $2/5$.

> [!question] 7 · Medium
> Suppose $P(A)=0.4$, $P(B)=0.5$, and $P(A\cap B)=0.1$. Are they independent? Find $P(A\mid B)$.

> [!success]- Solution
> No: $0.1\ne0.4(0.5)$. The conditional probability is $0.1/0.5=0.2$.

> [!question] 8 · Easy
> Independent components work with probabilities $0.8$ and $0.9$. The system works if at least one works. Find its success probability.

> [!success]- Solution
> The system fails only if both fail: $1-(0.2)(0.1)=0.98$.

## Round 3 — binomial

> [!question] 9 · Easy
> In five fair coin flips, find the probability of exactly three heads.

> [!success]- Solution
> Choose the three head positions in $\binom53$ ways. Each complete five-flip sequence has probability $(1/2)^5$:
> $\binom53/2^5=10/32=5/16$.

> [!question] 10 · Medium
> Six independent items each have defect probability $0.1$. Find the probability exactly one is defective.

> [!success]- Solution
> Let a defective item count as success. There are six possible positions for the one defect; the remaining five items must all be good:
> $\binom61(0.1)(0.9)^5=0.354294$.

> [!question] 11 · Medium
> Four independent attempts each succeed with probability $0.7$. Find the probability at least three succeed.

> [!success]- Solution
> Add exactly three and exactly four:
> $\binom43(0.7)^3(0.3)+(0.7)^4=0.6517$.

> [!question] 12 · Medium
> Draw two cards without replacement. Find the probability exactly one is an ace. Explain why a binomial model is unsuitable.

> [!success]- Solution
> The draws change the pool, so a fixed independent success probability does not apply.
> Choose one of the 4 aces and one of the 48 non-aces, then divide by all unordered two-card hands:
> $$
> \frac{\binom41\binom{48}{1}}{\binom{52}{2}}
> =\frac{192}{1326}=\frac{32}{221}.
> $$

## Round 4 — Bayes

> [!question] 13 · Easy
> Sources A and B are equally likely. An observed signal has probability $0.8$ from A and $0.2$ from B. Given the signal, find the probability of A.

> [!success]- Solution
> The A-and-signal route has weight $0.5(0.8)=0.4$; the B-and-signal route has weight $0.5(0.2)=0.1$. Among all signals, take A's fraction:
> $\frac{(0.8)(0.5)}{(0.8)(0.5)+(0.2)(0.5)}=0.8$.

> [!question] 14 · Medium
> A factory gets 75% of parts from A and 25% from B. Their defect rates are 2% and 6%. Given a defect, find the probability of B.

> [!success]- Solution
> Contributions are $0.75(0.02)=0.015$ and $0.25(0.06)=0.015$.
> B's posterior is $0.015/0.030=1/2$.

> [!question] 15 · Medium
> A filter's spam prior is 0.1. A word appears in 60% of spam and 10% of non-spam. Find the spam posterior for a message containing that word.

> [!success]- Solution
> $\frac{0.1(0.6)}{0.1(0.6)+0.9(0.1)}=0.4$.
> The likelihood $0.6$ is not the requested posterior.

> [!question] 16 · Medium
> Under naive Bayes, two features have likelihoods $0.4,0.5$ in spam and $0.2,0.1$ in non-spam. With equal priors, find the spam posterior if both occur.

> [!success]- Solution
> Within-class products are $0.2$ and $0.02$. Equal priors cancel:
> $0.2/(0.2+0.02)=10/11\approx0.9091$.

## Round 5 — models and reasoning

> [!question] 17 · Easy
> Outcomes A, B, C have probabilities $t,2t,3t$. Find $t$ and the probability of B or C.

> [!success]- Solution
> $6t=1$, so $t=1/6$. The event has probability $2t+3t=5/6$.

> [!question] 18 · Medium
> A list contains 900 strings of length 10. Each position is a bit. Prove at least one possible string is missing, using probability.

> [!success]- Solution
> Choose uniformly from 1024 strings. The probability of being on the list is at most $900/1024<1$. Being absent has positive probability, so an absent string exists.

> [!question] 19 · Medium
> For a fixed bad input, each test round falsely passes with probability at most $1/3$. Rounds are independent and acceptance requires every round to pass. How many rounds make false acceptance at most $1/100$?

> [!success]- Solution
> Four rounds give $1/81>1/100$; five give $1/243<1/100$. Five rounds suffice.

> [!question] 20 · Medium
> Compare these questions in the independent uniform 365-day birthday model:
> 1. Some pair in a group of 23 shares a birthday.
> 2. At least one of 22 other people shares your birthday.

> [!success]- Solution
> 1. $1-\prod_{j=0}^{22}\frac{365-j}{365}\approx0.5073$.
> 2. $1-(364/365)^{22}\approx0.0586$.
> The first allows a match between any pair. The second requires a match to one specified birthday.

## Round 6 — explain the model

> [!question] 21 · Easy
> Under the standard Monty Hall rules, you choose door 1 and the host opens an unchosen goat door. What event makes switching win, and what is its probability?

> [!success]- Solution
> Switching wins exactly when the first choice was a goat. The first choice is wrong with probability $2/3$, so switching wins with probability $2/3$. The host’s informed action does not create two equally likely remaining doors.

> [!question] 22 · Medium
> For the non-transitive dice in [[02 Probability Rules and Puzzles]], an opponent chooses C. Which die should you choose, and why?

> [!success]- Solution
> Choose B because $P(B>C)=5/9$. Against C’s values 3, 4, and 8, B’s values 1, 5, and 9 win 0, 2, and 3 comparisons respectively, for 5 wins among 9 equally likely pairs.

> [!question] 23 · Easy
> A spinner lands on A, B, and C with probabilities $0.5$, $0.3$, and $0.2$. Define $X=0$ for A and $X=1$ for B or C. Give the distribution of $X$.

> [!success]- Solution
> $P(X=0)=0.5$. Two outcomes produce $X=1$, so add their weights: $P(X=1)=0.3+0.2=0.5$.

> [!question] 24 · Medium
> Three machines produce 50%, 30%, and 20% of all items. Their defect rates are 1%, 2%, and 4%. Find the overall probability that a randomly chosen item is defective.

> [!success]- Solution
> Add the three mutually exclusive production routes:
> $$
> P(D)=0.50(0.01)+0.30(0.02)+0.20(0.04)=0.019.
> $$

## Mastery tracker

Use this return route after a mistake, then close the solution and retry:

| Questions | Lesson to revisit |
|---|---|
| 1–4 | [[01 Probability Foundations]] and [[02 Probability Rules and Puzzles]] |
| 5–8 | [[03 Conditional Probability and Independence]] |
| 9–12 | [[04 Bernoulli Trials and Binomial Distribution]]; question 12 also uses combinations |
| 13–16, 24 | [[05 Bayes Theorem and Naive Bayes]] |
| 17–19, 23 | [[06 Probability Models and Methods]] |
| 20–22 | [[02 Probability Rules and Puzzles]] |

- [ ] Questions 1–4: sample spaces and rules.
- [ ] Questions 5–8: conditioning and independence.
- [ ] Questions 9–12: binomial versus changing-pool experiments.
- [ ] Questions 13–16: Bayesian updating.
- [ ] Questions 17–20: models and reasoning.
- [ ] Questions 21–24: puzzles, random variables, and total probability.
- [ ] I have redone every missed question without viewing its solution.
