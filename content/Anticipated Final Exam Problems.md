**Format tags used below:** `[proof]` `[counterexample]` `[application]` `[T-F/MC]`

## Section 1 — New and Untested Problems

*Problems from Ch. 5–7 or earlier chapters that have never appeared on a midterm. Ranked by likelihood within each tier.*

### Tier 1 — Near-Certain

1. **6.2.3 (pg. 180)** — $g_n(x) = \dfrac{x}{1+x^n}$ on $(0, \infty)$: pointwise limit, uniform convergence, subdomain `[application]`
    - Three parts test everything in the uniform convergence unit: (a) find the piecewise pointwise limit; (b) use the **contrapositive of CLT** — limit is discontinuous at $x=1$, so convergence cannot be uniform on $(0,\infty)$; (c) argue uniform convergence holds on a smaller subdomain

2. **2.4.5 (pg. 58)** — Recurrence $x_{n+1} = \frac{1}{2}(x_n + 2/x_n)$; show $(x_n) \to \sqrt{2}$ `[proof]`
    - Full four-step proof: induction (perfect square trick) → decreasing → MCT → ALT. Likely one of the 1–2 proof questions.

3. **Theorem 7.5.1 — FTOC (pg. 234)** — $F' = f \Rightarrow \int_a^b f = F(b) - F(a)$ `[proof or application]`
    - Could appear as: (a) a computation: $\int_0^2 (x^3+1)\,dx = 6$, or (b) a proof sketch (MVT on each subinterval → telescoping sum → integrability squeezes $F(b)-F(a)$ to equal the integral)
    - Prepare both forms

4. **Theorem 6.2.6 — CLT (pg. 178)** — $f_n \rightrightarrows f$, each $f_n$ continuous $\Rightarrow$ $f$ continuous `[proof]`
    - The $\epsilon/3$ argument: insert $f_N$, control outer terms by uniform convergence (same $N$ covers all $x$), control middle term by continuity of $f_N$

---

### Tier 2 — High Probability

5. **5.2.2 (pg. 152)** — "Exactly one of the following is impossible; provide examples for the other three" `[counterexample]`
    - Four parts, one impossible: (a) POSSIBLE — $f = g = |x|$, product $= x^2$; (b) POSSIBLE — $f = |x|$, $g = x$, product $= x|x|$; (c) **IMPOSSIBLE** — ADT forces $f = (f+g) - g$ differentiable; (d) POSSIBLE — $f(x) = x^2 d(x)$, differentiable at 0 only
    - Focus on **(c)** — the impossibility argument via ADT

6. **5.3.3 (pg. 161)** — $h$ continuous on $[0,3]$, $h(0)=1$, $h(1)=2$, $h(3)=2$: (a) fixed point; (b) $h'(c) = 1/3$; (c) $h'(d) = 1/4$ `[application]`
    - Three parts sequentially use IVT, MVT, then **Darboux** — the only problem that chains all three Ch. 5 tools. Part (c) is the hardest: need MVT to get $h'(e) = 0$, then Darboux fills in $1/4$ between $0$ and $1/3$.
    - Darboux is easy to forget under exam pressure — the reasoning is: $h'$ is not required to be continuous, so IVT does not directly apply; Darboux is IVT specifically for derivatives

7. **5.3.7 (pg. 161)** — $f'(x) \neq 1$ for all $x$ $\Rightarrow$ $f$ has at most one fixed point `[proof or T-F]`
    - Contradiction + MVT proof: two fixed points $\Rightarrow$ MVT gives $f'(c) = 1$ somewhere $\Rightarrow$ contradiction
    - Short, clean, two-sentence proof. Could appear as "prove this statement" or as a T-F with justification.

8. **6.2.6 Exercise (pg. 181)** — UC is preserved under uniform convergence `[proof]`
    - $\epsilon/3$ argument identical to CLT but the $\delta$ from $f_N$'s uniform continuity works **for all $x, y$** (not just at a fixed $c$) — that's the crux to state explicitly on the exam

---

### Tier 3 — Possible

9. **Example 6.2.2(iii) (pg. 174)** — $h_n(x) = x^{1+1/(2n-1)} \to \lvert x \rvert$ on $[-1,1]$ `[T-F/MC]`
    - Pointwise limit of differentiable functions need not be differentiable
    - The key is the odd denominator $2n-1$: odd roots preserve sign for $x < 0$, so the limit is $|x|$ not $x$
    - More likely to appear as a MC "what is the pointwise limit?" or "is the convergence uniform?" than as a full proof

10. **MCT + convergent subsequence** — $x_n \uparrow$ with a convergent subsequence $\Rightarrow$ $x_n$ converges `[proof or T-F]`
    - Short proof: subsequence convergent $\Rightarrow$ bounded $\Rightarrow$ sequence bounded above $\Rightarrow$ MCT. Three lines.

11. **7.3.1 (pg. 226)** — $h(x) = 1$ on $[0,1)$, $h(1) = 2$: show $L(h,P) = 1$ for all $P$; find $P$ with $U(h,P) < 1 + \tfrac{1}{10}$ `[application]`
    - Model argument for any single jump discontinuity
    - Likely format: find a specific partition (choose $\delta < 1/10$ to isolate the jump) — computation/verification style

12. **Theorem 4.4.7 — Heine-Cantor (pg. 133)** — continuous on compact $\Rightarrow$ uniformly continuous `[T-F/MC or application]`
    - More likely as: "is $f(x) = x^2$ uniformly continuous on $[0,5]$? Why?" than a full proof of Heine-Cantor itself
    - **Key use case:** invoking it to justify UC when the domain is compact (e.g., in the 6.2.6 proof)

---

## Section 2 — Previously Tested Problems

*These appeared on Midterm 1, 2, or 3.*

### Tier 1 — High Return Probability

1. **3.3.2** (all 5 parts) — classify each set as compact or not `[counterexample]`
    - Know cold: $\mathbb{N}$ unbounded → not compact; $\mathbb{Q} \cap [0,1]$ not closed → not compact; Cantor set = compact; partial sums of $\sum 1/k^2$ — limit $\pi^2/6$ not in set → not compact; $\{1, 1/2, 2/3, \ldots\}$ limit point $1$ is in set → compact

2. **4.4.8 (pg. 134)** (all 3 parts) — continuous function range examples `[counterexample]`
    - Know cold: (a) **impossible** (compactness); (b) $\sin^2(2\pi x)$ on $(0,1)$; (c) tent function on $(0,1]$

3. **2.6.4(a)** — prove $c_n = |a_n - b_n|$ is Cauchy `[proof]`
    - Use the reverse triangle inequality — do not argue via ALT
    - Required structure: $|c_n - c_m| \leq |(a_n - a_m) - (b_n - b_m)| \leq |a_n - a_m| + |b_n - b_m| < \epsilon/2 + \epsilon/2$

4. **2.5.2(d)** — monotone sequence with convergent subsequence $\Rightarrow$ converges `[proof or T-F]`
    - Short proof: subsequence bounded $\Rightarrow$ sequence bounded above $\Rightarrow$ MCT. This is exactly the two-step argument.

---

### Tier 2 — Moderate Return Probability

5. **2.5.1** (all 4 parts) — subsequence existence/impossibility `[counterexample]`
    - Trickiest part is (d): if subsequences converge to every $1/k$, a diagonal construction forces a subsequence converging to $0$ — impossible to avoid.

6. **2.4.2(b)** — MCT proof for $y_{n+1} = 3 - 1/y_n$ `[proof]`
    - Structurally identical to **2.4.5** — same MCT approach for a recursive sequence.

7. **4.2.2(b) (pg. 120)** — largest $\delta$ for $\lim_{x \to 4} \sqrt{x} = 2$, $\epsilon = 1$ `[application]`
    - Answer: $\delta = 3$ (distance from 4 to the closer endpoint of $(1,9)$)

8. **1.4.7** — show $\alpha^2 > 2$ leads to contradiction ($\alpha = \sup T$, $T = \{t : t^2 < 2\}$) `[proof]`
    - The Archimedean Property $n_0$ construction is the key move.

---

### Tier 3 — Lower Priority

9. **3.3.12** — bounded infinite set has a limit point (open cover proof) `[proof]`
    - Standard compactness-contradiction argument

10. **1.2.8** (all 3 parts) — 1-1 not onto, onto not 1-1, bijection $\mathbb{N} \to \mathbb{Z}$ `[counterexample]`
