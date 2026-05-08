Problems ordered from most to least likely to appear on the final exam, based on professor's verbal flags, post-exam review pattern, and format match. Solutions cross-referenced: textbook → solution manual → class notes (professor's approach preferred).

## Key Theorems

### Ch. 5 — Differentiation

- **Theorem 5.3.1 (Rolle's Theorem).** (pg. 158) If $f$ is continuous on $[a,b]$, differentiable on $(a,b)$, and $f(a) = f(b)$, then $\exists\,c \in (a,b)$ with $f'(c) = 0$.

- **Theorem 5.3.2 (Mean Value Theorem).** (pg. 159) If $f$ is continuous on $[a,b]$ and differentiable on $(a,b)$, then $\exists\,c \in (a,b)$ with $f'(c) = \dfrac{f(b)-f(a)}{b-a}$.

- **Theorem 5.2.7 (Darboux's Theorem).** (pg. 155) If $f$ is differentiable on $[a,b]$ and $\alpha$ is any value strictly between $f'(a)$ and $f'(b)$, then $\exists\,c \in (a,b)$ with $f'(c) = \alpha$.
    - **Key use:** IVT for derivatives — $f'$ need not be continuous; Darboux still forces it to hit every intermediate value.

- **Theorem 5.2.4 (Algebraic Differentiability Theorem / ADT).** (pg. 149) If $f$ and $g$ are differentiable at $c$, then $f+g$, $fg$, and $f/g$ (when $g(c)\neq 0$) are also differentiable at $c$.

### Ch. 6 — Sequences and Series of Functions

- **Theorem 6.2.6 (Continuous Limit Theorem / CLT).** (pg. 178) Let $(f_n)$ converge uniformly on $A$ to $f$. If each $f_n$ is continuous at $c \in A$, then $f$ is continuous at $c$.
    - **Contrapositive (exam-critical):** if the limit $f$ is discontinuous at some point $c$, then the convergence cannot be uniform on any domain containing $c$ as a limit point.

- **Theorem 6.3.1 (Differentiable Limit Theorem / DLT).** (pg. 183) If $f_n \to f$ pointwise (at least at one point), each $f_n$ is differentiable on $[a,b]$, and $f_n' \rightrightarrows g$ uniformly, then $f_n \rightrightarrows f$ uniformly and $f' = g$.

- **Theorem 4.4.7 (Heine-Cantor).** If $f$ is continuous on a compact set $K$, then $f$ is uniformly continuous on $K$.

### Ch. 7 — The Riemann Integral

- **Theorem 7.5.1 (Fundamental Theorem of Calculus).** (pg. 234)
    - **(i)** If $f: [a,b] \to \mathbb{R}$ is integrable and $F: [a,b] \to \mathbb{R}$ satisfies $F'(x) = f(x)$ for all $x$, then $\displaystyle\int_a^b f = F(b) - F(a)$.
    - **(ii)** Let $g: [a,b] \to \mathbb{R}$ be integrable and define $G(x) = \displaystyle\int_a^x g$. Then $G$ is continuous on $[a,b]$. If $g$ is continuous at $c$, then $G'(c) = g(c)$.

- **Theorem 7.4.4 (Integrable Limit Theorem).** (pg. 231) If $f_n \rightrightarrows f$ on $[a,b]$ and each $f_n$ is integrable, then $f$ is integrable and $\displaystyle\lim_{n\to\infty} \int_a^b f_n = \int_a^b f$.

### Ch. 2 — Review Theorems Needed

- **Theorem 2.4.2 (Monotone Convergence Theorem / MCT).** (pg. 54) A monotone bounded sequence converges.

- **Theorem 2.2.3 (Algebraic Limit Theorem / ALT).** (pg. 44) If $\lim a_n = a$ and $\lim b_n = b$, then $\lim(a_n + b_n) = a+b$, $\lim(a_n b_n) = ab$, and $\lim(a_n/b_n) = a/b$ (when $b \neq 0$).

## Problems and Solutions

### Tier 1 — Near-Certain

- **1. Exercise 6.2.3** (pg. 180) For each $n \in \mathbb{N}$ and $x \in [0, \infty)$, let $g_n(x) = \dfrac{x}{1+x^n}$ and $h_n(x) = \begin{cases} 1 & x \geq 1/n \\ nx & 0 \leq x < 1/n \end{cases}$. For both sequences: (a) find the pointwise limit on $[0,\infty)$; (b) explain why convergence cannot be uniform on $[0,\infty)$; (c) give a smaller set where convergence is uniform and prove it.
    - Only $g_n$ was covered in class. Prepare $g_n$ first; $h_n$ solutions below for completeness.
    - **$g_n(x) = x/(1+x^n)$:**
        - **(a)** Pointwise limit:
            - $0 \leq x < 1$: $x^n \to 0$, so $g_n(x) \to x$.
            - $x = 1$: $g_n(1) = 1/(1+1) = 1/2$ for all $n$.
            - $x > 1$: $x^n \to \infty$, so $g_n(x) \to 0$.
            - $$g(x) = \begin{cases} x & 0 \leq x < 1 \\ \tfrac{1}{2} & x = 1 \\ 0 & x > 1 \end{cases}$$
        - **(b)** Not uniform on $[0,\infty)$:
            - Each $g_n$ is continuous. The limit $g$ is discontinuous at $x = 1$: $\lim_{x \to 1^-} g(x) = 1 \neq 1/2 = g(1)$.
            - **Contrapositive of CLT:** if the limit is discontinuous somewhere, convergence cannot be uniform on any domain containing that point. $\square$
        - **(c)** Uniform convergence on $[2,\infty)$ (limit $g \equiv 0$ there):
            1. For $x \geq 2$: $|g_n(x) - 0| = \dfrac{x}{1+x^n} < \dfrac{x}{x^n} = x^{1-n} \leq 2^{1-n} = \dfrac{1}{2^{n-1}}$.
            2. Given $\epsilon > 0$, choose $N$ so $1/2^{N-1} < \epsilon$. Then for all $n \geq N$ and all $x \geq 2$: $|g_n(x) - 0| < \epsilon$. $\square$
            - **N.B.:** Professor said subdomain $(0,1)$ in class; this is mathematically incorrect (sup of error $\to 1/2$ as $x \to 1^-$). SM gives $[2,\infty)$, the clean rigorous proof. Uniform convergence also holds on $[0,a]$ for any $a < 1$.
    - **$h_n(x)$:**
        - **(a)** For $x = 0$: $h_n(0) = 0$. For $x > 0$: eventually $x \geq 1/n$, so $h_n(x) = 1$. Thus $h(x) = \begin{cases} 0 & x = 0 \\ 1 & x > 0 \end{cases}$.
        - **(b)** Each $h_n$ continuous, but $h$ discontinuous at $x = 0$ ($\lim_{x\to 0^+} h(x) = 1 \neq 0 = h(0)$). CLT contrapositive applies. $\square$
        - **(c)** Uniform on $[a,\infty)$ for any $a > 0$: choose $N$ with $1/N < a$. For $n \geq N$ and $x \geq a > 1/n$: $h_n(x) = 1 = h(x)$, so error $= 0 < \epsilon$. $\square$

- **2. Exercise 2.4.5** (pg. 58) Let $x_1 = 2$ and define $x_{n+1} = \dfrac{1}{2}\!\left(x_n + \dfrac{2}{x_n}\right)$. Show $(x_n)$ converges and find the limit.
    - Strategy (professor's order): establish $x_n^2 \geq 2$ by induction → show decreasing → MCT → identify limit.
    - Warm-up: $x_2 = \tfrac{1}{2}(2+1) = \tfrac{3}{2}$, confirming the sequence decreases initially.
    - **Step 1: $x_n^2 \geq 2$ for all $n$ (by induction).**
        1. Base case: $x_1^2 = 4 \geq 2$. ✓
        2. Inductive step — expand $(x_{n+1})^2$:
            - $(x_{n+1})^2 = \dfrac{1}{4}\!\left(x_n + \dfrac{2}{x_n}\right)^2 = \dfrac{x_n^2}{4} + 1 + \dfrac{1}{x_n^2}$
            - Complete the square: $= \left(\dfrac{x_n}{2} - \dfrac{1}{x_n}\right)^2 + 2 \geq 2$. $\checkmark$
        3. Therefore $x_n^2 \geq 2$ for all $n$. $\square$
    - **Step 2: the sequence is decreasing.**
        - $x_n - x_{n+1} = \dfrac{x_n^2 - 2}{2x_n} \geq 0$ since $x_n^2 \geq 2$ and $x_n > 0$. $\square$
    - **Step 3: bounded below and MCT.**
        - From $x_n^2 \geq 2$ and $x_n > 0$: $x_n \geq \sqrt{2}$. Decreasing and bounded below → MCT → limit exists. $\square$
    - **Step 4: identify the limit.** Let $x = \lim x_n$. Apply ALT to both sides of the recurrence:
        - $x = \dfrac{1}{2}\!\left(x + \dfrac{2}{x}\right) \implies \dfrac{x}{2} = \dfrac{1}{x} \implies x^2 = 2 \implies x = \sqrt{2}$ (positive root since all terms positive). $\square$

- **3. Theorem 7.5.1 — FTOC** (pg. 234)
    - **Statement:**
        - (i) If $f: [a,b] \to \mathbb{R}$ integrable and $F'(x) = f(x)$ for all $x$, then $\displaystyle\int_a^b f = F(b) - F(a)$.
        - (ii) If $g: [a,b] \to \mathbb{R}$ integrable and $G(x) = \displaystyle\int_a^x g$, then $G$ is continuous; if $g$ continuous at $c$ then $G'(c) = g(c)$.
    - **Proof of Part (i):**
        1. Let $P = \{x_0, x_1, \ldots, x_n\}$ be any partition of $[a,b]$.
        2. Apply MVT to $F$ on each subinterval: $\exists\,t_k \in (x_{k-1},x_k)$ with $F(x_k) - F(x_{k-1}) = f(t_k)\,\Delta x_k$.
        3. Since $m_k \leq f(t_k) \leq M_k$: multiply by $\Delta x_k$ and sum to get $L(f,P) \leq \displaystyle\sum_{k=1}^n (F(x_k)-F(x_{k-1})) \leq U(f,P)$.
        4. The middle sum telescopes: $\displaystyle\sum_{k=1}^n (F(x_k) - F(x_{k-1})) = F(b) - F(a)$.
        5. So $L(f,P) \leq F(b)-F(a) \leq U(f,P)$ holds for every partition.
        6. Since $f$ integrable: $\sup L = \inf U = \displaystyle\int_a^b f$. Therefore $\displaystyle\int_a^b f = F(b)-F(a)$. $\square$
    - Key moves: MVT converts each antiderivative increment into a Riemann-sum term; telescoping gives $F(b)-F(a)$; integrability squeezes.
    - Computation example (from [[6.5.26 Real Analysis Class Notes|6.5.26]]): $\displaystyle\int_0^2 (x^3+1)\,dx = \left[\dfrac{x^4}{4}+x\right]_0^2 = (4+2) - 0 = 6$.
    - Part (i) vs. Part (ii): (i) is the computation tool (evaluate via antiderivative); (ii) is the theoretical tool (differentiate an integral defined by its upper limit).

- **4. Theorem 6.2.6 — CLT** (pg. 178)
    - **Statement:** If $(f_n)$ converges uniformly to $f$ on $A$ and each $f_n$ is continuous at $c \in A$, then $f$ is continuous at $c$.
    - **Proof** ($\epsilon/3$ argument, [[27.4.26 Real Analysis Class Notes|27.4.26]]):
        1. Let $\epsilon > 0$. By uniform convergence, choose $N$ so $|f_n(x)-f(x)| < \epsilon/3$ for all $x \in A$, all $n \geq N$.
        2. Apply the triangle inequality:
            $$|f(x)-f(c)| \leq \underbrace{|f(x)-f_N(x)|}_{<\,\epsilon/3} + \underbrace{|f_N(x)-f_N(c)|}_{<\,\epsilon/3} + \underbrace{|f_N(c)-f(c)|}_{<\,\epsilon/3}$$
        3. Terms I and III: uniform convergence supplies the same $N$ for all $x \in A$ simultaneously — no $x$-dependence.
        4. Term II: once $N$ is fixed, $f_N$ is a specific continuous function; choose $\delta$ so $|x-c|<\delta \Rightarrow |f_N(x)-f_N(c)|<\epsilon/3$.
        5. For $|x-c|<\delta$: all three terms $< \epsilon/3$, so $|f(x)-f(c)| < \epsilon$. $\square$
    - **Contrapositive (exam application):** if the limit is NOT continuous somewhere, convergence cannot be uniform.

### Tier 2 — High Probability

- **5. Exercise 5.2.2** (pg. 152) Exactly one of the following requests is impossible. Decide which it is and provide examples for the other three (all functions defined on $\mathbb{R}$): (a) $f,g$ not differentiable at $0$, $fg$ differentiable at $0$; (b) $f$ not differentiable at $0$, $g$ differentiable at $0$, $fg$ differentiable at $0$; (c) $f$ not differentiable at $0$, $g$ differentiable at $0$, $f+g$ differentiable at $0$; (d) $f$ differentiable at $0$ but not at any other point.
    - **The impossible one is (c).** Know this cold — it's what gets graded.
    - **(c) IMPOSSIBLE — Proof:**
        1. Suppose for contradiction $h = f+g$ is differentiable at $0$ and $g$ is differentiable at $0$.
        2. Then $f = h - g$ is the difference of two functions differentiable at $0$.
        3. By **ADT (Theorem 5.2.4)**, $f$ is differentiable at $0$ — contradiction. $\square$
    - Why (b) has no analogous impossibility: knowing $fg$ and $g$ differentiable doesn't force $f$ differentiable — the "quotient" $f = (fg)/g$ fails when $g(0) = 0$.
    - **(a) POSSIBLE:** Let $f(x) = g(x) = |x|$. Neither differentiable at $0$; $(fg)(x) = x^2$ is. ✓
    - **(b) POSSIBLE:** Let $f(x) = |x|$, $g(x) = x$. Then $(fg)(x) = x|x|$; $(fg)'(0) = \lim_{x\to 0}|x| = 0$. ✓
    - **(d) POSSIBLE:** Let $f(x) = x^2 d(x)$ where $d$ is the Dirichlet function.
        - At $0$: $f'(0) = \lim_{x\to 0} x\,d(x) = 0$ (since $|x\,d(x)| \leq |x| \to 0$). ✓
        - At $c \neq 0$: $f$ oscillates between $0$ and $c^2$ in every neighborhood — not continuous, hence not differentiable. ✓
        - Why $x^2$ not $x$: $f(x) = x\,d(x)$ gives $f'(0) = \lim d(x)$, which doesn't exist. The $x^2$ provides sufficient damping.

- **6. Exercise 5.3.3** (pg. 161) Let $h$ be differentiable on $[0,3]$ with $h(0)=1$, $h(1)=2$, $h(3)=2$. (a) Show $\exists\,d \in [0,3]$ with $h(d)=d$. (b) Show $\exists\,c \in (0,3)$ with $h'(c)=1/3$. (c) Show $\exists\,d \in (0,3)$ with $h'(d)=1/4$.
    - **(a) IVT:**
        1. Define $g(x) = h(x) - x$. Then $g(0) = 1 > 0$ and $g(3) = 2-3 = -1 < 0$.
        2. $g$ continuous. By **IVT**, $\exists\,d \in (0,3)$ with $g(d) = 0$, i.e., $h(d) = d$. $\square$
    - **(b) MVT:**
        1. Apply **MVT** to $h$ on $[0,3]$: $h'(c) = \dfrac{h(3)-h(0)}{3-0} = \dfrac{1}{3}$ for some $c \in (0,3)$. $\square$
    - **(c) Darboux:**
        1. Apply MVT to $h$ on $[1,3]$: $h'(e) = \dfrac{h(3)-h(1)}{3-1} = 0$ for some $e \in (1,3)$.
        2. Now $h'$ takes value $0$ at $e$ and $1/3$ at $c$ from (b). Since $0 < 1/4 < 1/3$, and $h'$ need not be continuous, IVT does not apply directly.
        3. By **Darboux's Theorem** (IVT for derivatives): $\exists\,d$ between $c$ and $e$ with $h'(d) = 1/4$. $\square$
    - **Darboux under pressure:** $h'$ not required continuous → standard IVT on $h'$ is invalid → Darboux is the substitute that applies specifically to derivatives.

- **7. Exercise 5.3.7** (pg. 161) A fixed point of $f$ is a value $x$ where $f(x) = x$. Show that if $f$ is differentiable on an interval with $f'(x) \neq 1$ for all $x$, then $f$ has at most one fixed point.
    - Covered in class ([[22.4.26 Real Analysis Class Notes|22.4.26]]). Short two-sentence proof. Could appear as "prove this" or T-F with justification.
    - **Proof (by contradiction):**
        1. Suppose $f$ has two distinct fixed points $x_1, x_2$ with $f(x_i) = x_i$.
        2. Apply **MVT** on the interval between $x_1$ and $x_2$:
            $$f'(c) = \frac{f(x_1)-f(x_2)}{x_1-x_2} = \frac{x_1-x_2}{x_1-x_2} = 1 \quad \text{for some } c.$$
        3. But $f'(c) \neq 1$ for all $c$ — contradiction. At most one fixed point. $\square$
    - Geometric intuition: two fixed points → graph crosses diagonal $y=x$ twice → Rolle's on $g(x) = f(x)-x$ gives $g'(c) = 0$, i.e., $f'(c) = 1$ — forbidden.

- **8. Exercise 6.2.6** (pg. 181) Assume $f_n \to f$ on $A$. Provide examples showing all propositions false under pointwise convergence; decide which hold under uniform convergence: (a) each $f_n$ UC $\Rightarrow$ $f$ UC; (b) each $f_n$ bounded $\Rightarrow$ $f$ bounded; (c)–(e) discontinuity count questions.
    - Covered as "hard version" with "exam priority" flag — [[29.4.26 Real Analysis Class Notes|29.4.26]]. If only one of CLT vs 6.2.6 can be prepped, prep CLT.
    - Professor only covered (a) and (b) — these are the exam priorities.
    - **(a) Pointwise → FALSE:**
        - Counterexample: $f_n(x) = x^n$ on $[0,1]$. Each $f_n$ continuous on compact set → UC by Heine-Cantor. Pointwise limit: $f(x) = 0$ for $x < 1$, $f(1) = 1$ — not continuous at $x=1$, hence not UC.
    - **(a) Uniform → TRUE:**
        1. Let $\epsilon > 0$. Choose $N$ so $|f_n(x)-f(x)| < \epsilon/3$ for all $x$, $n \geq N$.
        2. Triangle inequality: $|f(x)-f(y)| \leq \underbrace{|f(x)-f_N(x)|}_{<\,\epsilon/3} + \underbrace{|f_N(x)-f_N(y)|}_{<\,\epsilon/3} + \underbrace{|f_N(y)-f(y)|}_{<\,\epsilon/3}$
        3. Since $f_N$ UC, $\exists\,\delta$ so $|x-y|<\delta \Rightarrow |f_N(x)-f_N(y)|<\epsilon/3$.
        4. Outer terms bounded by uniform convergence — no $x,y$-dependence. For $|x-y|<\delta$: $|f(x)-f(y)|<\epsilon$. $\square$
        - **Crux (state explicitly on exam):** the same $\delta$ from $f_N$'s UC works for $f$ because the outer terms are controlled independently of $x$ and $y$.
    - **(b) Pointwise → FALSE:**
        - Counterexample: $f_n(x) = \min(1/x,\,n)$ on $(0,1)$. Each $f_n$ bounded; pointwise limit $1/x$ is unbounded.
    - **(b) Uniform → TRUE:**
        1. Choose $N$ so $|f_N(x)-f(x)| \leq 1$ for all $x$. Since $f_N$ bounded by $M$: $|f(x)| \leq |f(x)-f_N(x)| + |f_N(x)| < 1 + M$. $\square$
    - **(c)–(e):** Not covered in class. For reference: all false under pointwise; under uniform, (c)(d) remain false but (e) is true.

### Tier 3 — Possible

- **9. Example 6.2.2(iii)** (pg. 174) $h_n(x) = x^{1+1/(2n-1)}$ on $[-1,1]$: find the pointwise limit; determine if the limit is differentiable.
    - **N.B.:** This is an in-text example, not a numbered exercise. "Exercise 6.2.2" in the textbook is a different problem.
    - **Pointwise limit** (write $h_n(x) = x \cdot x^{1/(2n-1)}$):
        - $x > 0$: $x^{1/(2n-1)} \to 1$, so $h_n(x) \to x$.
        - $x = 0$: $h_n(0) = 0$.
        - $x < 0$: denominator $2n-1$ always odd, so $x^{1/(2n-1)}$ is a real odd root, preserving sign: $(-|x|)^{1/(2n-1)} = -|x|^{1/(2n-1)} \to -1$. So $h_n(x) \to x \cdot (-1) = |x|$.
        - Combining: $h_n \to |x|$ pointwise on $[-1,1]$.
    - Each $h_n$ differentiable; limit $|x|$ continuous but not differentiable at $0$.
    - This shows: pointwise limit of differentiable functions need not be differentiable.
    - **Key exam detail:** the odd denominator $2n-1$ forces correct sign for $x < 0$ — most likely what appears in MC.

- **10. MCT + Convergent Subsequence** Prove: if $(x_n)$ is increasing with a convergent subsequence $(x_{n_k})$, then $(x_n)$ converges.
    - **Proof:**
        1. Since $(x_{n_k})$ converges, it is bounded above by some $M$.
        2. For any $n$, choose $k$ with $n_k \geq n$. Since $(x_n)$ is increasing: $x_n \leq x_{n_k} \leq M$.
        3. So $(x_n)$ is bounded above. By **MCT**, $(x_n)$ converges. $\square$
    - Crux: use the subsequence only to extract an upper bound $M$ — don't try to identify the limit from it.

- **11. Exercise 7.3.1** (pg. 226) Let $h(x) = \begin{cases} 1 & 0 \leq x < 1 \\ 2 & x = 1 \end{cases}$ on $[0,1]$. (a) Show $L(h,P) = 1$ for every partition $P$. (b) Find $P$ with $U(h,P) < 1 + 1/10$. (c) For any $\epsilon > 0$, find $P$ with $U(h,P) < 1 + \epsilon$.
    - **(a):** On any subinterval $[x_{k-1},x_k]$: $h = 1$ everywhere except the single point $x = 1$, so $m_k = 1$ for every subinterval. Thus $L(h,P) = \sum m_k\,\Delta x_k = \sum \Delta x_k = 1$. $\square$
    - **(b):** Take $P_\delta = \{0,\, 1-\delta,\, 1\}$ for any $\delta < 1/10$:
        - $U(h,P_\delta) = (1-\delta)\cdot 1 + \delta \cdot 2 = 1 + \delta < 1 + 1/10$. $\square$
    - **(c):** Take $P_\epsilon = \{0,\, 1-\epsilon/2,\, 1\}$:
        - $U(h,P_\epsilon) = (1-\epsilon/2) + 2\cdot(\epsilon/2) = 1 + \epsilon/2 < 1 + \epsilon$.
        - Since $L = 1$ for all $P$ and $U$ can be pushed within any $\epsilon$ of $1$: $h$ is integrable with $\int_0^1 h = 1$. $\square$
    - Model argument: isolate the jump in a subinterval of width $\delta$; jump contributes at most $(\sup h - \inf h)\cdot\delta = \delta$ to $U-L$; choose $\delta < \epsilon$.

- **12. Theorem 4.4.7 — Heine-Cantor** (approx. pg. 116) Continuous on compact $K$ $\Rightarrow$ uniformly continuous on $K$.
    - How it appears: "Is $f(x) = x^2$ uniformly continuous on $[0,5]$?" — Yes: $[0,5]$ compact, $f$ continuous, Heine-Cantor applies.
    - Key use cases in this unit:
        - Justifying each $f_n = x^n$ is UC on $[0,1]$ in the 6.2.6(a) counterexample.
        - Justifying $f_N$ is UC on compact subsets in the 6.2.6 hard-version proof.
        - Recognizing when a UC argument can be shortcut by compactness.
    - Contrast with non-compact: $f(x) = 1/x$ on $(0,1)$ continuous but NOT UC. On $[a,1]$ for any $a > 0$ (compact), it is UC.
