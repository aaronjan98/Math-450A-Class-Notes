# 23.2.26 Real Analysis Class Notes (Cleaned + Clarified)

1. **Cesàro Mean**
	- **Statement:** If $x_n \to x$, then
		- $\dfrac{x_1 + \dots + x_n}{n} \to x$
	- Interpretation:
		- Even if the beginning of a sequence behaves badly, averaging dilutes the early terms.
		- As $n$ grows, the influence of finitely many early terms becomes negligible.
	- Important clarification:
		- The Cesàro theorem applies when the original sequence converges.
		- It does **not** say that averaging makes every divergent sequence converge.

	- Harmonic numbers tangent:
		- $H_n = 1 + \frac{1}{2} + \cdots + \frac{1}{n}$
		- $H_n$ diverges.
		- However, $H_n$ grows like $\log n$.
		- So consider $\dfrac{H_n}{n}$.
			- Compare with $\dfrac{\ln n}{n}$.
			- Using L'Hospital:
				- $\lim_{n\to\infty} \dfrac{\ln n}{n} = 0$.
			- So $\dfrac{H_n}{n} \to 0$.
		- Important:
			- $H_n$ diverges,
			- but it grows slowly enough that dividing by $n$ forces convergence to 0.

	- CS tangent: Hiring problem
		- Probability of hiring the $k$-th candidate is $\frac{1}{k}$.
		- Expected number of hires:
			- $E = 1 + \frac{1}{2} + \frac{1}{3} + \cdots + \frac{1}{n} = H_n$.
		- Since $H_n \to \infty$, expected hires grow slowly but without bound.

1. **Monotone Convergence Theorem (MCT)**
	- **Statement:**
		1. If $a_n$ is monotone (increasing or decreasing),
		2. and bounded,
		3. then $a_n$ converges.
	- **N.B.**: Main theorem to get stuff done throughout this course.

1. **Problem 2.4.1 — Recursive Sequence**
	- Given:
		- $x_1 = 3$
		- $x_2 = 1$
		- $x_{n+1} = \dfrac{1}{4 - x_n}$
	- Compute:
		- $x_3 = \dfrac{1}{4 - 1} = \dfrac{1}{3}$
		- $x_4 = \dfrac{1}{4 - 1/3} = \dfrac{3}{11}$

	- Goal:
		- Use MCT → need boundedness + monotonicity.

	- Step 1: Boundedness
		- For $n \ge 2$, show:
			- $0 < x_n \le 1$
		- If $0 < x_n \le 1$, then:
			- $4 - x_n \ge 3$
			- So $x_{n+1} = \dfrac{1}{4-x_n} \le \dfrac{1}{3} \le 1$
			- Also $x_{n+1} > 0$
		- So bounded below by 0 and above by 1 (for $n \ge 2$).

	- Step 2: Show it is decreasing
		- **No argument made as to why it's decreasing in the book.**
		- Want: $x_n \ge x_{n+1}$.
		- Since $x_{n+1} = \dfrac{1}{4 - x_n}$,
			- inequality becomes:
				- $x_n \ge \dfrac{1}{4 - x_n}$
		- Multiply both sides by $(4 - x_n)$:
			- $x_n(4 - x_n) \ge 1$
			- $4x_n - x_n^2 \ge 1$
			- $x_n^2 - 4x_n + 1 \le 0$
		- Solve quadratic:
			- $x = 2 \pm \sqrt{3}$
		- Since $0 < x_n \le 1$,
			- relevant root is $2 - \sqrt{3}$.
		- On interval $[2-\sqrt{3},1]$,
			- inequality holds.
		- So once sequence enters that interval,
			- it is decreasing.
		- **N.B.**: This is the algebra you must supply on exams.

	- Step 3: Take limit
		- Since bounded and decreasing → limit exists by MCT.
		- Let $L = \lim x_n$.
		- Take limit both sides:
			- $L = \dfrac{1}{4 - L}$
		- Solve:
			- $L(4 - L) = 1$
			- $L^2 - 4L + 1 = 0$
			- $L = 2 \pm \sqrt{3}$
		- Choose:
			- $L = 2 - \sqrt{3}$ (since $0 < L \le 1$).

1. **Proof of Monotone Convergence Theorem**
	- Let $a_n$ be increasing and bounded above.
	- Let $a = \sup\{a_n\}$.
	- Professor’s picture:
		- Vertical line at $a$.
		- Mark $a - \epsilon$ slightly below it.
	- Since $a$ is least upper bound:
		- $a - \epsilon$ cannot be an upper bound.
		- So $\exists N$ such that:
			- $a_N > a - \epsilon$
	- Because sequence increasing:
		- for all $n \ge N$:
			- $a_n \ge a_N > a - \epsilon$
	- Also $a_n \le a$.
	- So:
		- $a - \epsilon < a_n \le a$
	- Hence:
		- $|a_n - a| < \epsilon$
	- So $a_n \to a$.

1. **Bolzano–Weierstrass Theorem**
	- Statement:
		- Every bounded sequence has a convergent subsequence.
	- Weak hypothesis → strong conclusion.
	- Important logical point:
		- If a subsequence is bounded,
			- then that subsequence itself has a convergent sub-subsequence.
		- So original sequence must contain a convergent subsequence.

	- Example professor likes:
		- $a_n = \begin{cases}
			1 - \frac{1}{n} & n \text{ odd} \\
			\frac{1}{n} & n \text{ even}
		  \end{cases}$
		- Odd terms → 1
		- Even terms → 0
		- **N.B.**: professor likes these problems on the exam.

	- Construction idea:
		- Start with bounded interval.
		- Split in half.
		- One half contains infinitely many points.
		- Choose that half.
		- Repeat.
		- Intervals are nested.
		- Intersection point is the limit.
		- Choose one point from each interval → convergent subsequence.

- **N.B.**: Start practicing the easy problems in the textbook.
