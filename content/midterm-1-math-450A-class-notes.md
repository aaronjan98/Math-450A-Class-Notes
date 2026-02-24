# Midterm 1 Math 450A Class Notes

1. **Triangle inequality: $\;|x+y|\le|x|+|y|$**
	- **Proof.**
		1. $(x+y)^2 = x^2 + 2xy + y^2$
			- Since each expression of the inequality is positive, squaring preserves inequalities.
		2. $2xy \le 2|x||y|$
			- We're bounding the worst-case scenario: $xy$ can be negative, but $|x||y|$ is always the largest possible value of $|xy|$.
		3. $(x+y)^2 \le x^2 + 2|x||y| + y^2 = (|x|+|y|)^2$
			- remember how to manufacture a perfect square.
		4. Take square roots: $|x+y|\le |x|+|y|.\ \square$
			- $\sqrt{(x+y)^2}=|x+y|$ is where the absolute value enters naturally.

2. **Reverse triangle inequality: $\;||a|-|b|| \le |a-b|$**
	- **Proof.**
		1. Write $a = (a-b)+b$
			- This identity is the entire trick
		2. Apply triangle inequality: $|a| \le |a-b| + |b|$
			- Think: distance from 0 to $a$ is no more than going from 0 to $b$, then from $b$ to $a$.
		3. Rearrange: $|a| - |b| \le |a-b|$
		4. Swap roles of $a$ and $b$: $|b|-|a| \le |a-b|$
		5. Combine: $||a|-|b|| \le |a-b|.\ \square$
			- Absolute value appears because we proved *both directions*.

3. **Irrationality of $\sqrt{3}$**
	- **Proof (contradiction).**
		1. Assume $\sqrt{3} = p/q$ with $(p,q)=1$
			- we must assume $\gcd$ of 1.
		2. Square: $3q^2 = p^2$
			- This tells us $p^2$ is divisible by $3$.
		3. Conclude $p$ is divisible by $3$, write $p=3k$
			- Prime divisibility: if a prime divides a square, it divides the base.
		4. Substitute: $3q^2=9k^2 \Rightarrow q^2=3k^2$
		5. So $q$ is divisible by $3$
			- The contradiction is that both share a factor.
		6. Contradiction to $(p,q)=1$. Hence $\sqrt{3}\notin\mathbb{Q}.\ \square$
			- procedure doesn't work with $\sqrt{6}$ because the method depends on primes.

4. **Irrationality of $\sqrt{2}$**
	- **Proof (contradiction, parity).**
		1. Assume $\sqrt{2}=m/n$ with $(m,n)=1$
		2. Square: $2n^2=m^2$
			- This forces $m^2$ to be even.
		3. So $m$ is even, write $m=2k$
			- Square of an odd number is odd; this fact is used implicitly.
		4. Substitute: $2n^2=4k^2 \Rightarrow n^2=2k^2$
		5. Hence $n$ is even
		6. Contradiction: both even $\Rightarrow \sqrt{2}\notin\mathbb{Q}.\ \square$

5. **Density of $\mathbb{Q}$ in $\mathbb{R}$**
	- **Claim:** For $\alpha<\beta$, there exists $r\in\mathbb{Q}$ with $\alpha<r<\beta$.
	- **Proof (bucket argument).**
		1. Choose $N\in\mathbb{N}$ with $1/N<\beta-\alpha$
			- This uses the Archimedean property: naturals eventually beat any real.
		2. Define $k=\min\{k\in\mathbb{Z}:\ k/N>\alpha\}$
		3. Then $(k-1)/N\le\alpha<k/N$
			- This inequality is the crux of the proof.
		4. $k/N \le \alpha+1/N < \beta$
			- Think: one bucket step can’t jump over the whole interval.
		5. Therefore $\alpha<k/N<\beta.\ \square$
			- This is why “$\ge$” breaks the argument: you lose strict control.

6. **Axiom of Completeness**
	- **Statement.**
		- Every nonempty set of real numbers that is bounded above has a supremum.
	- **Interpretation from class.**
		- This is not true in $\mathbb{Q}$ (e.g. $\{q\in\mathbb{Q}:q^2<2\}$).
		- The axiom is what separates $\mathbb{R}$ from $\mathbb{Q}$.

7. **Supremum / Infimum examples**
	- $\left\{ \frac{m}{n}:m<n \right\}$: $\sup=1$, $\inf=0$
		- You can approach 1 arbitrarily closely but never exceed it.
	- $\left\{ \frac{(-1)^m}{n} \right\}$: $\sup=1$, $\inf=-1$
		- Alternating signs create symmetric bounds.
	- $\left\{ \frac{n}{3n+1} \right\}$: $\sup=\frac13$, $\inf=\frac14$
		- Rewrite as $\frac{1}{3+1/n}$ to see the limit behavior.
	- $\left\{ \frac{m}{m+n} \right\}$: $\sup=1$, $\inf=0$
		- Fix one variable and let the other grow.

8. **Nested Interval Property (professor’s contradiction approach)**
	- **Claim:** If $I_n=[a_n,b_n]$ and $I_{n+1}\subseteq I_n$, then $\cap I_n\neq\emptyset$.
	- **Proof.**
		1. Let $a=\sup\{a_n\}$
			- Left endpoints are bounded above by any $b_n$.
		2. Assume $a\notin\cap I_n$, and let $I_N$ be the first interval excluding $a$
		3. Case 1: $a<a_N$
			- Then $a$ is not an upper bound of $\{a_n\}$.
		4. Case 2: $a>b_N$
			- Then $b_N$ is a smaller upper bound, contradicting leastness.
		5. Both cases impossible $\Rightarrow a\in\cap I_n.\ \square$
			- Closed intervals matter: endpoints must belong.

9. **Induction with recurrence $x_{n+1}=\frac{x_n}{2}+1$**
	- **Claim:** $x_n\le x_{n+1}$ for all $n$.
	- **Proof.**
		1. Base case: $x_1=1,\ x_2=\frac32$
		2. Induction hypothesis: assume $x_n\le x_{n+1}$
		3. Apply the recurrence to both sides: $$\frac{x_n}{2}+1 \le \frac{x_{n+1}}{2}+1$$
			- the recurrence is the function applied to the inequality.
		4. Recognize $x_{n+1}\le x_{n+2}$
		5. Hence, by mathematical induction, the inequality $x_{n} \leq x_{n+1}$ is true for all $n\geq 1. \square$

10. **Countability examples**
	- $\mathbb{N}\sim 2\mathbb{N}$ via $n\mapsto2n$
		- Proper subsets can have the same cardinality.
	- $\mathbb{N}\sim\mathbb{Z}$ via $0,-1,1,-2,2,\dots$
		- professor emphasized “interleaving”
	- $\mathbb{Q}$ is countable via finite layers $A_n$ with $p+q=n$
		- Reduced form prevents duplicates.
		- Example: $22/7$ appears in $A_{29}$.

11. **Cantor diagonalization: $(0,1)$ is uncountable**
	- **Proof.**
		1. Assume $f:\mathbb{N}\to(0,1)$ is onto, with decimals $f(n)=.a_{n1}a_{n2}\dots$
		2. Define $x=.b_1b_2\dots$ where $b_n\neq a_{nn}$
			- Professor emphasized: change *one digit per row*.
		3. Then $x\neq f(n)$ for every $n$
		4. Contradiction $\Rightarrow (0,1)$ uncountable. $\square$
			- Decimal ambiguity avoided by never using 9.

12. **Cantor’s Theorem: no onto $f:A\to\mathcal{P}(A)$**
	- **Proof.**
		1. Assume $f$ is onto
		2. Define $B=\{a\in A:\ a\notin f(a)\}$
		3. Suppose $B=f(a')$
		4. If $a'\in B$ then $a'\notin f(a')$; if $a'\notin B$ then $a'\in f(a')$
		5. Contradiction $\Rightarrow$ no such $f$. $\square$

13. **Algebraic number example: $\sqrt2+\sqrt3$**
	- **Proof.**
		1. Let $x=\sqrt2+\sqrt3$
		2. Square: $x^2=5+2\sqrt6$
		3. Rearrange: $x^2-5=2\sqrt6$
		4. Square again: $x^4-10x^2+1=0$
		5. Polynomial with integer coefficients $\Rightarrow x$ algebraic. $\square$
