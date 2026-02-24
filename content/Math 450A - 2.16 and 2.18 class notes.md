# Real Analysis 2.16 and 2.18 Class Notes

- Housekeeping:
  - Still needs to upload the updated prix fixe list for midterm II

## Monday February 16 Class Notes

1. **Definition of Limit of a Sequence: $a_n \to a$**
	- **Midterm** — this definition will appear.
	- Picture:
		- Think of sequence terms as dots on the real line.
		- Draw a circle centered at $a$ with radius $\epsilon$.
	- Meaning:
		1. Given $\epsilon > 0$
		2. $\exists N \in \mathbb{N}$ such that $\forall n \ge N$
		3. $|a_n - a| < \epsilon$
	- Interpretation:
		- Eventually all dots fall inside the circle.
		- Once inside, they stay inside.
	- “Only the tail matters” means:
		- The first finitely many terms can behave badly.
		- Convergence ignores finitely many terms.
		- What matters is behavior after some index $N$.

1. **Example:** $\lim_{n\to\infty} \dfrac{2n^2}{n^3+3} = 0$
	- Goal:
		- Trap sequence inside $\epsilon$-circle around 0.
	- Strategy professor used:
		1. Bound the expression:
			- $\dfrac{2n^2}{n^3+3} \le \dfrac{2}{n}$
		2. Control $\dfrac{2}{n}$ instead.
		3. Solve:
			- $\dfrac{2}{n} < \epsilon$
			- $n > \dfrac{2}{\epsilon}$
		4. Archimedean Principle:
			- Naturals exceed any real number.
			- So we can choose $N > \dfrac{2}{\epsilon}$.
	- Pattern:
		- Bound → Solve inequality → Use Archimedean property.

1. **Convergent ⇒ Bounded**
	- Use circle picture.
	- Procedure:
		1. Assume $a_n \to a$.
		2. Choose $\epsilon = 1$.
		3. Then $|a_n - a| < 1$ eventually.
		4. Triangle inequality:
			- $|a_n| \le |a| + |a_n - a|$
	- Meaning:
		- Tail sits inside fixed large circle.
		- First finitely many terms have a maximum.
	- Conclusion:
		- Entire sequence is bounded.

1. **Algebraic Limit Theorem — Sum Rule**
	- If $a_n \to a$ and $b_n \to b$
	- Then $a_n + b_n \to a + b$
	- Professor’s structure:
		1. Rewrite difference
		2. Apply triangle inequality
		3. Split $\epsilon$ into $\epsilon/2$
		4. Choose $N = \max(N_1,N_2)$
	- Pattern:
		- Break error into pieces
		- Control each piece separately

1. **Algebraic Limit Theorem — Product Rule**
	- Subtle asymmetry for this proof
	- Rewrite:
		- $a_nb_n - ab = a_n(b_n-b) + b(a_n-a)$
	- Key issue:
		- Need $a_n$ bounded.
	- Why:
		- One term shrinks because $b_n \to b$.
		- The other must not blow up.
	- Use:
		- Convergent ⇒ bounded.
	- Professor emphasized:
		- This boundedness step is crucial.
		- Do not skip it on exams.

1. **Non-Convergence Example: $1,-1,1,-1,\dots$**
	- Dots oscillate.
	- Choose $\epsilon = \frac12$.
	- Cannot trap both 1 and -1.
	- So no limit.

1. **Monotone Convergence Theorem (MCT)**
	- Very Important for Midterm.
	- Increasing + bounded above ⇒ convergent.
	- Picture:
		- Climbing stairs with a ceiling.
	- Limit equals supremum.
	- Uses completeness of $\mathbb{R}$.
	- Important contrast:
		- Harmonic series increasing but not bounded.
		- So MCT cannot apply.

## Wednesday February 18 Class Notes

1. **Recursive Sequence:** $a_{n+1} = \sqrt{2 + a_n}$
	- Professor’s warning:
		- Taking limit immediately is “unmathematical.”
	- Correct order:
		1. Show increasing.
		2. Show bounded.
		3. Apply MCT.
		4. Then take limit.
	- After convergence justified:
		- $L = \sqrt{2+L}$
		- Solve → $L = 2$.
	- Lesson:
		- Never assume existence of limit before proving it.

1. **Harmonic Series Diverges**
	- Block splitting:
		- $1$
		- $\frac12$
		- $\frac13+\frac14$
		- $\frac15+\dots+\frac18$
		- $\frac19+\dots+\frac1{16}$
	- Each block ≥ $\frac12$.
	- Partial sums grow without bound.
	- Diverges.
	- Professor emphasized:
		- To prove divergence, build a growing lower bound.

1. **Cesàro Mean**
	- If $x_n \to x$
	- Then $\dfrac{x_1+\dots+x_n}{n} \to x$
	- Picture:
		- Early wild terms get diluted.
	- Split:
		- Finite early terms
		- Tail close to $x$
	- Each part controlled separately.

1. **Limit of a Quotient**
	- Condition:
		- $b_n \to b \neq 0$
	- Professor noted:
		- He does this slightly differently than the book.
	- Key inequality:
		- Eventually $|b_n| > \frac{|b|}{2}$
		- This keeps denominator away from 0.
	- Rewrite using common denominator.
	- Use product rule to control numerator.
	- Professor remark:
		- Quantify the cap $M$ carefully.
		- Fill in details for homework.
		- Be precise about where boundedness is used.

1. **BW (Bolzano–Weierstrass)**
	- Major Theorem — more later.
	- Every bounded sequence has a convergent subsequence.
	- Professor’s 2D box picture:
		1. Infinite points in a square.
		2. Split into four panels.
		3. One contains infinitely many points.
		4. Choose that panel.
		5. Repeat.
	- Panels shrink.
	- Nested squares form.
	- Nested Interval Theorem ensures intersection exists.
	- Choose one point from each panel.
	- That subsequence converges.
