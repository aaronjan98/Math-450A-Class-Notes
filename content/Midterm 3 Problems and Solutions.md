1. Exercise 4.2.2. Part b.
	- For each stated limit, find the largest possible $\delta$-neighborhood that is a proper response to the given $\epsilon$ challenge.
	- (b) $\displaystyle \lim_{ x \to 4 } \sqrt{ x } = 2$, where $\epsilon = 1$.
		- **Solution.**
			- Let $\epsilon = 1$.
			- Then, $\begin{aligned} |\sqrt{ x }-2| < 1 & \Longleftrightarrow -1 < \sqrt{ x } - 2 < 1 \\ &\Longleftrightarrow 1 < \sqrt{ x } < 3 \\ &\Longleftrightarrow 1 < x < 9 \\ &\Longleftrightarrow -3 < x-4 < 5 \end{aligned}$
			- Set $\delta = 3$.
			- Then, we have $\begin{aligned} |x-4| < 3 &\Longleftrightarrow -3 < x-4 < 3 \\ &\Longleftrightarrow 1 < x < 7 \\ &\Longleftrightarrow 1 < \sqrt{ x } < \sqrt{ 7 } \\ &\Longleftrightarrow -1 < \sqrt{ x } -2 < \sqrt{ 7 } -2 \end{aligned}$
			- Notice $\sqrt{ 7 } < \sqrt{ 9 } = 3$, so $\sqrt{ 7 } - 2 < 1$. Thus, $|\sqrt{ x } - 2| < 1 \ \square$.

2. Exercise 4.2.5. Part d.
	- Use Definition 4.2.1 to supply a proper proof for the following limit statements.
	- (d) $\displaystyle \lim_{ x \to 3 } 1 /x = 1 /3$
		- **Proof.**
			- Start with what we want to make small
				- $\displaystyle \Big|f(x) - L\Big| = \Bigg| \frac{1}{x} - \frac{1}{3}\Bigg| = \dfrac{|x-3|}{|3x|}$
			- To bound the denominator $|3x|$, first restrict $|x-3| < 1$
				- $-1 < x - 3 < 1 \Rightarrow 2 < x < 4$.
				- This is the range of $x$.
			- Thus the denominator has to be bounded by the lower bound
				- of $2 < x < 4 \Rightarrow 6 < 3x$.
				- Hence $\dfrac{1}{|3x|} < \dfrac{1}{6}$
			- Thus $\Bigg| \dfrac{1}{x} - \dfrac{1}{3}\Bigg| = \dfrac{|x-3|}{|3x|} < \dfrac{\epsilon}{6}$
			- Choose $\delta = \min\{ 1, 6\epsilon \}$
			- If $|x - 3| < \delta$, then $|x-3| < 1$ and $|x-3| < 6\epsilon$.
			- $\Rightarrow \Bigg| \dfrac{1}{x} - \dfrac{1}{3}\Bigg| = \dfrac{|x-3|}{|3x|} < \dfrac{6 \epsilon}{6} = \epsilon.\ \square$

3. Exercise 4.5.7.
	- Let $f$ be a continuous function on the closed interval $[0, 1]$ with range also contained in $[0, 1]$. Prove that $f$ must have a fixed point; that is, show $f(x) = x$ for at least one value of $x \in [0, 1].$
	- **Proof.**
		- Let $h(x) = f(x) - x = 0$. Since $f$ is continuous on $[0, 1],\ x \mapsto x$ is continuous, $h(x)$ is then continuous by Algebra of Continuous functions.
		- Also, $h(0) = f(0) - 0 \geq 0$ and $h(1) = f(1) - 1 \leq 0$ because $f([0, 1]) \subseteq [0, 1]$.
		- If $h(0) = 0$ or $h(1) = 0$, then those are the fixed points.
		- If $h(0) > 0$ and $h(1) < 0$, then by IVT $\exists c \in (0, 1) \ni h(c) = 0$.
		- Thus $f(x) - c = 0 \Rightarrow f(x) = c.$
		- Therefore, $f$ has a fixed point.

4. Exercise 4.4.7.
	- Prove that $f(x) = \sqrt{ x }$ is uniformly continuous on $[0, \infty)$.
	- **Proof.**
		- Let $\epsilon > 0$ be given.
		- Choose $\delta = \epsilon^{2}$
		- Let $x,y \geq 0$. WLOG assume $x > y$.
		- Then $(\sqrt{ x } - \sqrt{ y })^2 = x + y -2\sqrt{ xy } \leq x-y = |x-y|$
		- Hence $|\sqrt{ x } - \sqrt{ y }| \leq \sqrt{ |x-y| }$
		- So if $|x - y| < \delta = \epsilon^2$, then $|\sqrt{ x } - \sqrt{ y }| \leq \sqrt{ |x-y| } < \sqrt{ \epsilon^{2} } = \epsilon$.
		- Thus, $\sqrt{ x }$ is uniformly continuous. $\square$

5. Exercise 4.4.8.
	- Given an example of each of the following, or provide a short argument for why the request is impossible.
	- (a) A continuous function defined on $[0, 1]$ with range $(0, 1)$.
		- **Impossible.**
			1. $[0, 1]$ is compact (closed and bounded, by Heine–Borel).
			2. By **Theorem 4.4.1** (Preservation of Compact Sets), $f([0,1])$ must be compact.
			3. But $(0, 1)$ is not compact — it is not closed, since its limit points $0$ and $1$ do not belong to it.
			4. Contradiction. No such function exists. $\square$
	- (b) A continuous function defined on $(0, 1)$ with range $[0, 1]$.
		- **Possible.** Let $f(x) = \sin^2(2\pi x)$ on $(0, 1)$.
			- $f\!\left(\tfrac{1}{4}\right) = \sin^2\!\left(\tfrac{\pi}{2}\right) = 1$ — value $1$ is achieved. $\checkmark$
			- $f\!\left(\tfrac{1}{2}\right) = \sin^2(\pi) = 0$ — value $0$ is achieved. $\checkmark$
			- $f$ is continuous on $(0, 1)$ (composition of continuous functions). $\checkmark$
			- By IVT, all values in $[0, 1]$ are achieved. Hence range $= [0, 1]$. $\square$
			- **Intuition** (professor, 13.4.26): Draw the graph on $(0,1)$ as an open-ended wavy curve that dips all the way down to $y = 0$ and rises all the way up to $y = 1$ inside the domain — the endpoints $0$ and $1$ are never visited (open circles), but every height in $[0, 1]$ is still hit.
	- (c) A continuous function defined on $(0, 1]$ with range $(0, 1)$.
		- **Possible.** $(0, 1]$ is not compact (not closed), so there is no compactness obstruction. Define a piecewise linear function $f : (0, 1] \to \mathbb{R}$ as follows:
			- Set $f(1/n) = 1/2$ for all $n \geq 1$ (so $f(1) = 1/2 \in (0,1)$).
			- On each interval $[1/(n+1),\, 1/n]$, let $f$ form a tent: decrease from $1/2$ down to $1/(n+1)$, rise to $1 - 1/(n+1)$, then return to $1/2$.
			- **Continuity**: endpoint values $f(1/n) = 1/2$ match from both sides at every $1/n$. $\checkmark$
			- **Range $\subseteq (0,1)$**: on each interval $[1/(n+1),\, 1/n]$ the range is $[1/(n+1),\; 1 - 1/(n+1)] \subset (0,1)$. $\checkmark$
			- **Range $= (0,1)$**: $\bigcup_{n \geq 1} [1/(n+1),\; 1 - 1/(n+1)] = (0,1)$, since for any $y \in (0,1)$ we can choose $n$ large enough that $1/(n+1) \leq y \leq 1 - 1/(n+1)$, so $y$ is achieved on $[1/(n+1), 1/n]$. $\checkmark$
