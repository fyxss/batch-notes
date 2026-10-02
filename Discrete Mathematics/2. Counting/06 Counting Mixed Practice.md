---
aliases:
  - Counting Mixed Practice
  - Counting Practice Set
tags:
  - discrete-mathematics
  - counting
  - practice
  - exam-prep
---

# Counting Mixed Practice

> [!tip] How to use this set
> Write the **rule and symbolic expression** before using a calculator. Open a solution only after committing to an answer.

Navigation: [[05 Counting Formula and Decision Sheet|← Prev: Counting Formula Sheet]] · [[Discrete Mathematics/index|Table of Contents]] · [[3. Probability/00 Probability|Next Folder: 3. Probability →]]

## Level 1 — foundations

> [!question] 1. Outfits
> A wardrobe has 5 shirts, 4 pairs of trousers, and 3 pairs of shoes. How many outfits contain one of each?

> [!success]- Solution
> Product rule:
> $$5\cdot4\cdot3=60.$$

> [!question] 2. Variable-length integers
> How many 4-digit or 5-digit integers are there? Repeated digits are allowed.

> [!success]- Solution
> The first digit cannot be zero. The length cases are disjoint:
> $$9\cdot10^3+9\cdot10^4=99{,}000.$$

> [!question] 3. Overlapping divisibility
> How many integers from 1 to 200 are divisible by 4 or 6?

> [!success]- Solution
> Use inclusion–exclusion. Divisible by both means divisible by $\operatorname{lcm}(4,6)=12$:
> $$\left\lfloor\frac{200}{4}\right\rfloor+
> \left\lfloor\frac{200}{6}\right\rfloor-
> \left\lfloor\frac{200}{12}\right\rfloor
> =50+33-16=67.$$

> [!question] 4. Book arrangements
> In how many orders can 8 distinct books be placed on a shelf?

> [!success]- Solution
> Eight distinct books fill eight positions, with 8 choices first, then 7, and so on:
> $$8!=40{,}320.$$

## Level 2 — selecting and arranging

> [!question] 5. Officer positions
> From 12 students, choose a president, vice-president, secretary, and treasurer. No student may hold two positions.

> [!success]- Solution
> The roles are distinct, so order matters:
> $$P(12,4)=12\cdot11\cdot10\cdot9=11{,}880.$$

> [!question] 6. Unranked group
> Choose 4 students from 11 for an unranked group.

> [!success]- Solution
> Swapping members does not change the group, so use a combination:
> $$\binom{11}{4}=330.$$

> [!question] 7. Committee composition
> A committee contains exactly 2 of 7 mathematics students and 3 of 8 computer-science students. The two student groups do not overlap. How many committees are possible?

> [!success]- Solution
> Choose each subgroup, then multiply:
> $$\binom72\binom83=21\cdot56=1176.$$

> [!question] 8. A block in a line
> Nine people stand in a line. How many arrangements keep A, B, and C together in any order?

> [!success]- Solution
> Treat A, B, and C as one block. The block plus the other six people gives seven objects. Arrange the block internally in $3!$ ways:
> $$7!\cdot3!=30{,}240.$$

## Level 3 — repetition and identical objects

> [!question] 9. Repeated letters
> How many distinct arrangements of `BANANAS` are possible?

> [!success]- Solution
> There are 7 letters, with A repeated 3 times and N repeated twice:
> $$\frac{7!}{3!2!}=420.$$

> [!question] 10. Non-negative solutions
> How many non-negative integer solutions satisfy $x_1+x_2+x_3=9$?

> [!success]- Solution
> Represent the nine units by stars and separate the three named variables with two bars. Choose the two bar positions among eleven symbols:
> $$\binom{3+9-1}{3-1}=\binom{11}{2}=55.$$

> [!question] 11. Positive solutions
> How many positive integer solutions satisfy $x_1+x_2+x_3+x_4+x_5=13$?

> [!success]- Solution
> Give each variable one unit, or use the positive-solution formula:
> $$\binom{13-1}{5-1}=\binom{12}{4}=495.$$

> [!question] 12. Required digit
> How many length-6 strings over uppercase letters and digits start with a letter and contain at least one digit?

> [!success]- Solution
> Choose the first letter in 26 ways. For the remaining five positions, subtract all-letter strings from all alphanumeric strings:
> $$26(36^5-26^5)=1{,}263{,}204{,}800.$$

## Level 4 — guarantees

> [!question] 13. Repeated grade
> A course uses 6 possible letter grades. What is the minimum class size that guarantees at least 8 students receive the same grade?

> [!success]- Solution
> At most 7 students can occupy each grade without reaching eight:
> $$6(8-1)+1=43.$$
> With 42 students, a $7,7,7,7,7,7$ split is possible, so 43 is minimal.

> [!question] 14. Socks in the dark
> A drawer contains plenty of black, white, and blue socks. How many socks must be selected blindly to guarantee 5 socks of one colour?

> [!success]- Solution
> At most 4 of each of the 3 colours can be drawn without reaching five:
> $$3(5-1)+1=13.$$
> Twelve can fail with four socks of each colour, proving that 13 is the minimum.

> [!question] 15. A specified suit
> How many cards from a standard deck guarantee at least 5 hearts?

> [!success]- Solution
> The target is specifically hearts. In the worst case, all 39 non-hearts appear first, followed by 5 hearts:
> $$39+5=44.$$
> With 43 draws, all 39 non-hearts and only 4 hearts could have appeared, so 43 does not guarantee the target.

## Level 5 — combined medium problems

> [!question] 16. At least one ace
> How many five-card hands contain at least one ace?

> [!success]- Solution
> Subtract hands with no ace from all hands:
> $$\binom{52}{5}-\binom{48}{5}
> =2{,}598{,}960-1{,}712{,}304
> =886{,}656.$$

> [!question] 17. Distinct even-digit codes
> How many 5-digit codes use only the digits $0,2,4,6,8$ with no repetition?

> [!success]- Solution
> A code may begin with zero. All five distinct available digits are arranged:
> $$5!=120.$$

> [!question] 18. Distinct five-digit integers
> How many five-digit integers use only $0,2,4,6,8$ with no repetition?

> [!success]- Solution
> Unlike a code, an integer cannot begin with zero. The first digit has 4 choices; the remaining four digits can be arranged in $4!$ ways:
> $$4\cdot4!=96.$$

> [!question] 19. Lower-bounded distribution
> How many integer solutions satisfy
> $$x_1+x_2+x_3=12,$$
> where $x_1\ge2$, $x_2\ge1$, and $x_3\ge3$?

> [!success]- Solution
> Set $y_1=x_1-2$, $y_2=x_2-1$, and $y_3=x_3-3$. Then
> $$y_1+y_2+y_3=12-2-1-3=6,$$
> with all $y_i\ge0$. Therefore,
> $$\binom{3+6-1}{3-1}=\binom82=28.$$

> [!question] 20. Explain, do not calculate
> Why is the number of $r$-combinations from $n$ objects exactly $r!$ times smaller than the number of $r$-permutations?

> [!success]- Solution
> Every unordered group of $r$ distinct objects can be written as an ordered list in exactly $r!$ ways. Thus $P(n,r)$ counts every combination $r!$ times, so
> $$\binom nr=\frac{P(n,r)}{r!}.$$

## Level 6 — assumptions and representations

> [!question] 21. Circular seating
> Five distinct friends sit around a round table. Rotations count as the same seating, and reflections count as different. How many seatings exist? What if the five seats are individually numbered?

> [!success]- Solution
> Unnumbered: $(5-1)!=24$. Numbered: $5!=120$, because rotating people changes their assigned seats.

> [!question] 22. Cartesian product
> Let $A=\{a,b,c\}$ and $B=\{1,2\}$. How many elements are in $A\times B$? What does one element look like?

> [!success]- Solution
> There are $3\cdot2=6$ ordered pairs. One is $(a,2)$: a choice from A followed by a choice from B.

> [!question] 23. An impossible distribution
> How many positive integer solutions satisfy $x_1+x_2+x_3+x_4=3$?

> [!success]- Solution
> Zero. Four positive integers sum to at least four. Check feasibility before using a factorial formula.

> [!question] 24. Finite supplies
> A bag contains 1 red ball and 10 blue balls. Without replacement, how many draws guarantee three balls of the same colour?

> [!success]- Solution
> Four suffice: at most one is red, so at least three are blue. Three can fail with one red and two blue. The unrestricted two-colour formula gives five, which is sufficient but is not minimal here.

## Mastery tracker

If you miss a question, use this return route before retrying: questions 1–3 and 12 → [[01 Fundamental Counting Rules]]; 4–8 and 16–18 → [[02 Permutations and Combinations]]; 9–11, 19, and 23 → [[03 Generalized Counting]]; 13–15 and 24 → [[04 Pigeonhole Principles]]. Questions 20–22 check the explanations behind the formulas.

- [ ] 1–4 correct without notes
- [ ] 5–8 correct without notes
- [ ] 9–12 correct without notes
- [ ] 13–15 correct without notes
- [ ] 16–20 correct without notes
- [ ] 21–24 correct without notes
- [ ] Every wrong answer redone after one day

---

Navigation: [[05 Counting Formula and Decision Sheet|← Prev: Counting Formula Sheet]] · [[Discrete Mathematics/index|Table of Contents]] · [[3. Probability/00 Probability|Next Folder: 3. Probability →]]
