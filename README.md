# Combinatorics

## Outlines
  - [Basic Rules](#basic-rules)
  - [Factorial](#factorial)
  - [Permutations](#permutations)
  - [Combinations](#combinations)
  - [Techniques](#techniques)
    - [Casework](#casework)
    - [Complementary counting](#complementary-counting)
    - [Pigeonhole Principle](#pigeonhole-principle)
  - [Inclusion-Exclusion Principle](#inclusion-exclusion-principle)
  - [Permutation with Repetition](#permutation-with-repetition)
  - [stars and bars](#stars-and-bars)
  - [Derangement](#derangement)
  - [Resources](#resources)

## Basic Rules
- [Sum Rule](https://brilliant.org/wiki/rule-of-sum/)
- [Product Rule](https://brilliant.org/wiki/rule-of-product/)
- [Counting Integers in a Range](https://brilliant.org/wiki/counting-integers-in-a-range/)

### Example
How many positive divisors does $2000 = 2^4 \cdot 5^3$ have?

$\mathrm{(A)}\,10\quad\mathrm{(B)}\,21\quad\mathrm{(C)}\,31\quad\mathrm{(D)}\,5\quad\mathrm{(E)}\,7\quad\mathrm{(F)}\,20$


<details> 
  <summary> Solution ✅ </summary>

Any positive divisor of $2000$ must have the form $2^a \cdot 5^b$, where $a$ and $b$ are integers satisfying $0 \leq a \leq 4, 0 \leq b \leq 3$ There are $5$ possibilities for $a$ and $4$ possibilities for $b$, hence there are $5 \times 4 = 20$ (rule of product) positive divisors of 2000 in all.

</details>

## Factorial

### Definition
The factorial is defined for positive integers as $n!=n \cdot (n-1) \cdots 2 \cdot 1 = \prod_{i=1}^n i$. Alternatively, a recursive definition for the factorial is $n!=n \cdot (n-1)!$.

base case $n=0$ is defined as $0!=1$.

The factorial is used in the definitions of **combinations** and **permutations**, as $n!$ is the number of ways to order $n$ distinct objects

### Example
Find the rightmost digit of the sum $\sum_{i=1}^{100}(i!)^{2}$

$\mathrm{(A)}\,0\quad\mathrm{(B)}\,1\quad\mathrm{(C)}\,3\quad\mathrm{(D)}\,5\quad\mathrm{(E)}\,7\quad\mathrm{(F)}\,9$

<details>
  <summary> Solution ✅ </summary>

  If $i$ is less than 5, then $i!$ has a positive rightmost digit, if $i\geq 5$, then $i!$ has a rightmost digit of 0, as does $(i!)^2$. So we only need to worry about i=1-4.

  - $(1!)^2=1$
  - $(2!)^2=4$
  - $(3!)^2=36$
  - $(4!)^2=576$
  - $1+4+6+6=17$, which has a rightmost digit of 7 $\Rightarrow \mathrm{(E)}$
</details>

## Permutations

### Definition
A permutation of $n$ distinct objects is an ordering of these objects. The number of permutations of $n$ distinct objects is $n!$. The number of permutations of $n$ objects taken $k$ at a time is $\frac{n!}{(n-k)!}$.

### Formula
$P(n,r)=n(n-1)(n-2)\cdots(n-r+1)=\frac{n!}{(n-r)!}$.

### Example
Elodie is putting on a fashion show and has five fabulous outfits for her five fabulous fashion models. However, on the day of the show, two of the outfits were ruined in an unfortunate permanent marker incident. Regardless, the show must go on and the remaining outfits will be presented. If each outfit can only be worn by one model and there is no time for any model to wear more than one dress, how many different shows can Elodie put on? (Note: Two shows are considered the same if they contain the same models wearing the same dresses.)


$\mathrm{(A)}\,120\quad\mathrm{(B)}\,60\quad\mathrm{(C)}\,720\quad\mathrm{(D)}\,5040\quad\mathrm{(E)}\,24\quad\mathrm{(F)}\,6$

<details>
  <summary> Solution ✅ </summary>

Answer: $\mathrm{(B)}$

Since two of the outfits are ruined, we only have three outfits. There are five models available for the first outfit, four models available for the second outfit, and three models available for the third outfit. Therefore, there are $5 \cdot 4 \cdot 3 = \boxed{60}$ ways in which the models can be matched to the outfits.

</details>

## Combinations

### Definition
A combination, sometimes called a binomial coefficient, is a way of choosing $r$ objects from a set of $n$ where the order in which the objects are chosen is irrelevant. We are generally concerned with finding the number of combinations of size $r$ from an original set of size $n$

### Formulas/Identities
- ${ {n}\choose {r}} = \frac {n!} {r!(n-r)!}$
  
- $\binom{n-1}{r-1}+\binom{n-1}{r}=\binom{n}{r}$      

### Example
23 people attend a party. Each person shakes hands with at most 22 other people. What is the maximum possible number of handshakes, assuming that any two people can shake hands at most once?

$\mathrm{(A)}\,10\quad\mathrm{(B)}\,231\quad\mathrm{(C)}\,253\quad\mathrm{(D)}\,24\quad\mathrm{(E)}\,25\quad\mathrm{(F)}\,120$

<details>
  <summary> Solution ✅ </summary>

Answer: $\mathrm{(C)}$

Note that if each person shakes hands with every other person, then the number of handshakes is maximized.

There are $\binom{23}{2} = \frac{(23)(22)}{2} = (23)(11) = 230+23 = \boxed{253}$ ways to choose two people to form a handshake.

</details>

## Techniques

### Casework
#### Definition
casework is a counting method that involves splitting a problem into several parts, counting these parts individually, then adding together the totals of each part. Casework is a very general problem-solving approach, and as such has wide applicability.

#### Example
How many positive integers satisfy the equation $x^4 + y < 70$?

<details>
<summary> Solution ✅ </summary>

We use casework, based on the value of x.

Case 1: $x=1$. Then this problem becomes $y<69$, so there are $68$ possible values for $y$, and thus $68$ solutions when $x$ is one.

Case 2: $x=2$. Then this problem becomes $y<54$, so there are $53$ possible values for $y$, and thus $53$ solutions when $x$ is two.

If $x=3$, the problem becomes $y<-11$. But the question mandates that $y$ is positive, so there are no solutions when $y \geq 3$. Thus, there are $68+53=121$ positive integer solutions to the equation. $\square$

</details>

### Complementary counting
#### Definition
complementary counting is a counting method where one counts what they don't want, then subtracts that from the total number of possibilities

#### Example
How many positive integers less than $100$ are not a multiple of five?

<details>
<summary> Solution ✅ </summary>

We use a complementary approach. The total number of positive integers, with no restrictions, is $99$ integers. What we don't want are the multiples of five. These are $5, 10,..., 95$ or $1 \cdot 5, 2 \cdot 5,..., 19 \cdot 5$; it's easy to see that there are $19$ of them. Thus, our answer is is $99-19 = 80$. $\square$

</details>

### Pigeonhole Principle
#### Definition
the pigeonhole principle states that if $n+1$ or more pigeons are placed into $n$ holes, one hole must contain two or more pigeons

#### Example
1. If a Martian has an infinite number of red, blue, yellow, and black socks in a drawer, how many socks must the Martian pull out of the drawer to guarantee he has a pair? 
   <details>
    <summary> Solution ✅ </summary>

    The Martian must pull 5 socks out of the drawer to guarantee he has a pair. In this case the pigeons are the socks he pulls out and the holes are the colors. Thus, if he pulls out 5 socks, the Pigeonhole Principle states that some two of them have the same color. Also, note that it is possible to pull out 4 socks without obtaining a pair.

  </details>

2. Suppose $S$ is a set of $n + 1$ integers. Prove that there exist distinct $a, b \in S$ such that $a - b$ is a multiple of $n$.
   <details>
    <summary> Solution ✅ </summary>

    Consider the residues of the elements of $S$, modulo $n$. By the Pigeonhole Principle, there exist distinct $a, b \in S$ such that $a \equiv b \pmod n$, as desired.

  </details>


## Inclusion-Exclusion Principle
### Definition
The Principle of Inclusion-Exclusion (abbreviated PIE) provides an organized method/formula to find the number of elements in the union of a given group of sets, the size of each set, and the size of all possible intersections among the sets

### Statement
If $(A_i)_{1\leq i\leq n}$ are finite sets, then:

$\left|\bigcup_{i=1}^n A_i\right|=\sum_{i=1}^n\left|A_i\right| -\sum_{i < j}\left|A_i\cap A_j\right| +\sum_{i<j<k}\left|A_i\cap A_j\cap A_k\right|-\cdots\ +(-1)^{n-1} \left|A_1\cap\cdots\cap A_n\right|{}$.

### Example
Many states use a sequence of three letters followed by a sequence of three digits as their standard license-plate pattern. Given that each three-letter three-digit arrangement is equally likely, the probability that such a license plate will contain at least one palindrome (a three-letter arrangement or a three-digit arrangement that reads the same left-to-right as it does right-to-left) is $\dfrac{m}{n}$, where $m$ and $n$ are relatively prime positive integers. Find $m+n.$

<details>
<summary> Solution1 ✅ </summary>

Consider the three-digit arrangement, $\overline{aba}$. There are $10$ choices for $a$ and $10$ choices for $b$ (since it is possible for $a=b$), and so the probability of picking the palindrome is $\frac{10 \times 10}{10^3} = \frac 1{10}$. Similarly, there is a $\frac 1{26}$ probability of picking the three-letter palindrome.

By the Principle of Inclusion-Exclusion, the total probability is

$\frac{1}{26}+\frac{1}{10}-\frac{1}{260}=\frac{35}{260}=\frac{7}{52}\quad\Longrightarrow\quad7+52=\boxed{059}$

</details>

<details>
<summary> Solution2 ✅ </summary>

Using complementary counting, we count all of the license plates that do not have the desired property. In order to not be a palindrome, the first and third characters of each string must be different. Therefore, there are $10\cdot 10\cdot 9$ three digit non-palindromes, and there are $26\cdot 26\cdot 25$ three letter non palindromes. As there are $10^3\cdot 26^3$ total three-letter three-digit arrangements, the probability that a license plate does not have the desired property is $\frac{10\cdot 10\cdot 9\cdot 26\cdot 26\cdot 25}{10^3\cdot 26^3}=\frac{45}{52}$. We subtract this from 1 to get $1-\frac{45}{52}=\frac{7}{52}$ as our probability. Therefore, our answer is $7+52=\boxed{059}$.

</details>

## Permutation with Repetition
### Definition
A permutation with repetition is a permutation where the same element can appear more than once

### Formula

$$ \frac{n!}{ {n_{1}}! \cdot {n_{2}}! \cdots {n_{k}}!} $$

### Example
what is the number of permutations of the word "MISSISSIPPI" with 4 I's, 4 S's, 2 P's, and 1 M's?

<details>
  <summary> Solution ✅ </summary>

  Answer: $ \frac{11!}{4! \cdot 4! \cdot 2! \cdot 1!} = 34650$

</details>

## stars and bars
### Theorem one
For any pair of positive integers n and k, the number of k-tuples of positive integers whose sum is n is equal to the number of (k − 1)-element subsets of a set with n − 1 elements.

For example, if n = 10 and k = 4, the theorem gives the number of solutions to x1 + x2 + x3 + x4 = 10 (with x1, x2, x3, x4 > 0) as the binomial coefficient

${\displaystyle {\binom {n-1}{k-1}}={\binom {10-1}{4-1}}={\binom {9}{3}}=84.}{\displaystyle {\binom {n-1}{k-1}}={\binom {10-1}{4-1}}={\binom {9}{3}}=84.}$

### Theorem two
For any pair of positive integers n and k, the number of k-tuples of non-negative integers whose sum is n is equal to the number of multisets of cardinality n taken from a set of size k, or equivalently, the number of multisets of cardinality k − 1 taken from a set of size n + 1.

For example, if n = 10 and k = 4, the theorem gives the number of solutions to x1 + x2 + x3 + x4 = 10 (with x1, x2, x3, x4 {\displaystyle \geq 0}{\displaystyle \geq 0} ) as:

${\displaystyle {\binom {n+k-1}{k-1}}={\binom {10+4-1}{4-1}}={\binom {13}{3}}=286}{\displaystyle {\binom {n+k-1}{k-1}}={\binom {10+4-1}{4-1}}={\binom {13}{3}}=286}$

## Derangement
### Definition
A derangement is a permutation with no fixed points. That is, a derangement of a set leaves no element in its original place. For example, the derangements of $\{1,2,3\}$ are $\{2, 3, 1\}$ and $\{3, 1, 2\}$, but $\{3,2, 1\}$ is not a derangement of $\{1,2,3\}$ because 2 is a fixed point.

### Formula
\[!n = n! \sum_{k=0}^{n} \frac{(-1)^k}{k!}.\]


## Resources
- [Combinatorics](https://brilliant.org/wiki/combinatorics/)
- [Permutations](https://brilliant.org/wiki/permutations/)
- [Combinations](https://brilliant.org/wiki/combinations/)
- [Stars and Bars](https://brilliant.org/wiki/stars-and-bars/)
- [Probability](https://brilliant.org/wiki/probability)
- [AoPS Combinatorics](https://artofproblemsolving.com/wiki/index.php/Combinatorics)
- [AoPS Alcumus](https://artofproblemsolving.com/alcumus)
