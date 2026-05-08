1. Exercise 3.3.2.
    - Decide which of the following sets are compact. For those that are not compact, show how Definition 3.3.1 breaks down. In other words, give an example of a sequence contained in the given set that does not possess a subsequence converging to a limit in the set.
    - (a) $\mathbb{N}$.
        - **Not compact.**
            - $\mathbb{N}$ is unbounded, so it cannot be compact by Heine–Borel.
            - The sequence $x_n = n$ is contained in $\mathbb{N}$, and every subsequence of $(x_n)$ diverges to $+\infty$; there is no convergent subsequence in $\mathbb{N}$.
    - (b) $\mathbb{Q} \cap [0, 1]$.
        - **Not compact.**
            - $\mathbb{Q} \cap [0,1]$ is not closed in $\mathbb{R}$ — it is missing irrational limit points.
            - Let $x_n$ be the $n$-th decimal truncation of $\sqrt{2}/2 \approx 0.7071\ldots$: $$x_1 = 0.7,\quad x_2 = 0.70,\quad x_3 = 0.707,\quad \ldots$$
            - Each $x_n \in \mathbb{Q} \cap [0,1]$, but $x_n \to \sqrt{2}/2 \notin \mathbb{Q} \cap [0,1]$. No subsequence can converge to a limit in the set.
    - (c) The Cantor set.
        - **Compact.**
            - The Cantor set $\mathcal{C}$ is constructed by removing open intervals from $[0,1]$, so its complement is a union of open sets, making $\mathcal{C}$ closed.
            - $\mathcal{C} \subseteq [0,1]$, so it is bounded.
            - By Heine–Borel, closed and bounded implies compact. $\square$
    - (d) $\{ 1 + 1/2^2 + 1/3^2 + \cdots + 1/n^2 : n \in \mathbb{N} \}$.
        - **Not compact.**
            - This is the set $\{S_n\}$ of partial sums $S_n = \sum_{k=1}^n 1/k^2$.
            - The sequence $(S_n)$ is contained in the set and converges to $\pi^2/6$, but $\pi^2/6 \notin \{S_n\}$ (the limit is not itself a partial sum).
            - So the sequence $(S_n)$ has no convergent subsequence with limit in the set, breaking Definition 3.3.1.
    - (e) $\{ 1,\ 1/2,\ 2/3,\ 3/4,\ 4/5,\dots \}$.
        - **Compact.**
            - The set is $\{1\} \cup \{(n-1)/n : n \geq 2\}$.
            - **Bounded**: all terms lie in $[1/2, 1]$.
            - **Closed**: the only limit point is $1$ (since $(n-1)/n \to 1$), and $1$ is already in the set.
            - By Heine–Borel, compact. $\square$

2. Exercise 3.3.12.
    - Using the concept of open covers (and explicitly avoiding the Bolzano-Weierstrass Theorem), prove that every bounded infinite set has a limit point.
    - **Proof** (by contradiction).
        1. Let $E \subseteq \mathbb{R}$ be bounded and infinite. Assume for contradiction that $E$ has no limit point.
        2. Then every point $x \in E$ is isolated: for each $x \in E$, $\exists\, \varepsilon_x > 0$ such that $V_{\varepsilon_x}(x) \cap E = \{x\}$.
        3. Since $E$ has no limit points, $E$ is vacuously closed (a set contains all its limit points if there are none).
        4. $E$ is also bounded by assumption. By Heine–Borel, $E$ is compact.
        5. The collection $\{V_{\varepsilon_x}(x) : x \in E\}$ is an open cover of $E$.
        6. By compactness, there is a finite subcover: $E \subseteq V_{\varepsilon_{x_1}}(x_1) \cup \cdots \cup V_{\varepsilon_{x_n}}(x_n)$.
        7. But $V_{\varepsilon_{x_i}}(x_i) \cap E = \{x_i\}$ for each $i$, so $E \subseteq \{x_1,\ldots, x_n\}$, making $E$ finite. Contradiction.
        8. Therefore $E$ must have a limit point. $\square$
        - **N.B.**: on the final, can just cite Bolzano–Weierstrass instead.

3. Exercise 2.4.2.
    - (a) Consider the recursively defined sequence $y_1 = 1$, $y_{n+1} = 3 - y_n$, and set $y = \lim y_n$. Because $(y_n)$ and $(y_{n+1})$ have the same limit, taking the limit across the recursive equation gives $y = 3 - y$. Solving for $y$, we conclude $\lim y_n = 3/2$. What is wrong with this argument?
        - **Solution.**
            - Compute the first few terms: $y_1 = 1,\ y_2 = 2,\ y_3 = 1,\ y_4 = 2,\ \ldots$
            - The sequence oscillates between $1$ and $2$ and does not converge.
            - The flaw: you may only take the limit of both sides of a recurrence once convergence has already been established. The argument assumes $\lim y_n$ exists before proving it. Since the sequence diverges, the equation $y = 3-y$ is meaningless and the conclusion $y = 3/2$ is invalid.
    - (b) This time set $y_1 = 1$ and $y_{n+1} = 3 - 1/y_n$. Can the strategy in (a) be applied to compute the limit of this sequence?
        - **Solution.** Yes — once convergence is established. We first show the sequence is monotone increasing and bounded, then apply MCT, then take the limit.
        - Compute a few terms: $y_1 = 1,\ y_2 = 2,\ y_3 = 5/2,\ y_4 = 13/5 \approx 2.6,\ y_5 = 34/13 \approx 2.615,\ldots$ (increasing).
        - **Step 1 — Show increasing (induction).**
            - Base case: $y_2 - y_1 = 2 - 1 = 1 > 0$. ✓
            - Inductive step: Assume $y_{n+1} > y_n$. Then: $$y_{n+2} - y_{n+1} = \left(3 - \frac{1}{y_{n+1}}\right) - \left(3 - \frac{1}{y_n}\right) = \frac{1}{y_n} - \frac{1}{y_{n+1}} = \frac{y_{n+1} - y_n}{y_n\, y_{n+1}} > 0$$
                - since $y_{n+1} > y_n > 0$ by the inductive hypothesis. So monotonicity propagates. ✓ $\square$
        - **Step 2 — Show bounded.**
            - Claim: $1 \leq y_n < 3$ for all $n$.
            - Base: $y_1 = 1$. ✓
            - If $y_n \geq 1$, then $y_{n+1} = 3 - 1/y_n \leq 3 - 1/3 < 3$. ✓
            - If $y_n \geq 1$, then $y_{n+1} = 3 - 1/y_n \geq 3 - 1 = 2 \geq 1$. ✓
        - **Step 3 — Apply MCT.**
            - Increasing and bounded above $\Rightarrow$ $L = \lim y_n$ exists by the Monotone Convergence Theorem.
        - **Step 4 — Compute the limit.**
            - Take the limit of both sides: $L = 3 - 1/L$, so $L^2 - 3L + 1 = 0$, giving $L = \dfrac{3 \pm \sqrt{5}}{2}$.
            - Since $y_n \geq 2$ for all $n \geq 2$ and $(y_n)$ is increasing, $L = \dfrac{3 + \sqrt{5}}{2} \approx 2.618$. $\square$

4. Exercise 2.5.1.
    - Give an example of each of the following, or argue that such a request is impossible.
    - (a) A sequence that has a subsequence that is bounded but contains no subsequence that converges.
        - **Impossible.** Any bounded subsequence has a convergent sub-subsequence by Bolzano–Weierstrass. That convergent sub-subsequence is also a subsequence of the original sequence, so the original contains a convergent subsequence.
    - (b) A sequence that does not contain $0$ or $1$ as a term but contains subsequences converging to each of these values.
        - **Possible.** Consider: $$\left(\frac{1}{2},\ \frac{1}{2},\ \frac{2}{3},\ \frac{1}{3},\ \frac{3}{4},\ \frac{1}{4},\ \frac{4}{5},\ \frac{1}{5},\ \ldots,\ \frac{n-1}{n},\ \frac{1}{n},\ \ldots\right)$$
            - Even-indexed terms $1/n \to 0$, and $1/n \neq 0$ for all $n$. ✓
            - Odd-indexed terms $(n-1)/n \to 1$, and $(n-1)/n \neq 1$ for all $n$. ✓
    - (c) A sequence that contains subsequences converging to every point in the infinite set $\{ 1,\ 1/2,\ 1/3,\ 1/4,\ldots \}$.
        - **Possible.** List the values in diagonal groups: $$1,\quad 1,\ \tfrac{1}{2},\quad 1,\ \tfrac{1}{2},\ \tfrac{1}{3},\quad 1,\ \tfrac{1}{2},\ \tfrac{1}{3},\ \tfrac{1}{4},\quad \ldots$$
            - Each value $1/k$ first appears in the $k$-th group and appears infinitely many times thereafter, so the constant subsequence at $1/k$ converges to $1/k$. ✓
    - (d) A sequence that contains subsequences converging to every point in the infinite set $\{ 1,\ 1/2,\ 1/3,\ 1/4,\ldots \}$, and no subsequences converging to points outside of this set.
        - **Impossible.** If for each $k \in \mathbb{N}$ there is a subsequence converging to $1/k$, then for each $k$ we can find a term $a_{n_k}$ (with $n_1 < n_2 < n_3 < \cdots$) satisfying $|a_{n_k} - 1/k| < 1/(2k)$. Then: $$|a_{n_k}| \leq |a_{n_k} - 1/k| + 1/k < \frac{1}{2k} + \frac{1}{k} = \frac{3}{2k} \to 0$$
            - So $(a_{n_k}) \to 0$, but $0 \notin \{1, 1/2, 1/3,\ldots\}$. Contradiction. $\square$

5. Exercise 2.5.2. Part d.
    - Decide whether the following proposition is true or false, providing a short justification.
    - (d) If $(x_n)$ is monotone and contains a convergent subsequence, then $(x_n)$ converges.
    - **True.**
    - **Proof.**
        - WLOG assume $(x_n)$ is increasing. Let $x_{n_k} \to x$ be a convergent subsequence.
        - **Step 1 — $(x_n)$ is bounded above.**
            - Suppose for contradiction $(x_n)$ is not bounded above. Then $\exists\, r \in \mathbb{N}$ such that $x_r > |x| + 1$.
            - Since $(x_n)$ is increasing, for all $n_k > r$: $x_{n_k} \geq x_r > |x| + 1$.
            - Hence $|x_{n_k} - x| \geq x_{n_k} - |x| > 1$ for all $n_k > r$, contradicting $x_{n_k} \to x$. $\Rightarrow\Leftarrow$
        - **Step 2 — Apply MCT.**
            - $(x_n)$ is increasing and bounded above, so by the Monotone Convergence Theorem, $\lim x_n$ exists. $\square$

6. Exercise 2.6.4. Parts a and b.
    - Let $(a_n)$ and $(b_n)$ be Cauchy sequences. Decide whether each of the following sequences is a Cauchy sequence, justifying each conclusion.
    - (a) $c_n = |a_n - b_n|$.
        - **Cauchy.**
        - **Proof.** Apply the reverse triangle inequality:
            $$|c_n - c_m| = \big||a_n - b_n| - |a_m - b_m|\big| \leq |(a_n - b_n) - (a_m - b_m)| = |(a_n - a_m) - (b_n - b_m)| \leq |a_n - a_m| + |b_n - b_m|$$
        - Since $(a_n)$ and $(b_n)$ are Cauchy, for any $\epsilon > 0$ there exist $N_1, N_2 \in \mathbb{N}$ such that:
            - $n,m \geq N_1 \Rightarrow |a_n - a_m| < \epsilon/2$
            - $n,m \geq N_2 \Rightarrow |b_n - b_m| < \epsilon/2$
        - Let $N = \max(N_1, N_2)$. Then for $n,m \geq N$: $$|c_n - c_m| \leq |a_n - a_m| + |b_n - b_m| < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon$$
        - Hence $(c_n)$ is Cauchy. $\square$
        - **N.B.**: Do not argue via ALT ("$c_n$ converges because $a_n, b_n$ converge"). The professor expects the explicit reverse triangle inequality manipulation.
    - (b) $c_n = (-1)^n a_n$.
        - **Not necessarily Cauchy.**
        - **Counterexample.** Let $a_n = 1$ for all $n$. Then $(a_n)$ is Cauchy (constant sequence). But $c_n = (-1)^n$, which alternates between $+1$ and $-1$.
        - For any $N$, pick $n$ even and $m$ odd with $n, m \geq N$: $|c_n - c_m| = |1 - (-1)| = 2 \not< 1$.
        - Hence $(c_n)$ is not Cauchy. $\square$
