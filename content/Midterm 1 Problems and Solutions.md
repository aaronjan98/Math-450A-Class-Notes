1. Exercise 1.2.1.
    - (a) Prove that $\sqrt{3}$ is irrational. Does a similar argument work to show $\sqrt{6}$ is irrational?
        - **$\sqrt{3}$ is irrational.**
        - **Proof (contradiction).**
            1. Assume $\sqrt{3} = p/q$ with $\gcd(p,q) = 1$.
            2. Then $3q^2 = p^2$, so $3 \mid p^2$.
            3. Since $3$ is prime, $3 \mid p^2 \Rightarrow 3 \mid p$. Write $p = 3k$.
            4. Substitute: $3q^2 = 9k^2 \Rightarrow q^2 = 3k^2$, so $3 \mid q$.
            5. But then $3 \mid p$ and $3 \mid q$, contradicting $\gcd(p,q) = 1$. $\square$
        - **$\sqrt{6}$ is irrational.**
        - **Proof (contradiction).**
            1. Assume $\sqrt{6} = p/q$ with $\gcd(p,q) = 1$.
            2. Then $6q^2 = p^2$. Since $6 = 2 \cdot 3$, both $2 \mid p^2$ and $3 \mid p^2$.
            3. Since $2$ and $3$ are prime: $2 \mid p$ and $3 \mid p$. Hence $6 \mid p$. Write $p = 6k$.
            4. Substitute: $6q^2 = 36k^2 \Rightarrow q^2 = 6k^2$, so $6 \mid q$.
            5. But then $6 \mid p$ and $6 \mid q$, contradicting $\gcd(p,q) = 1$. $\square$
    - (b) Where does the proof of Theorem 1.1.1 break down if we try to use it to prove $\sqrt{4}$ is irrational?
        - **Solution.**
            - Assume $\sqrt{4} = p/q$ with $\gcd(p,q)=1$. Then $4q^2 = p^2$, so $4 \mid p^2$.
            - This implies $2 \mid p$ (since $2$ is the prime factor of $4$), but **not** $4 \mid p$.
            - Write $p = 2k$. Then $4q^2 = 4k^2 \Rightarrow q^2 = k^2 \Rightarrow q = k$.
            - So $p/q = 2k/k = 2$, which is perfectly consistent — no contradiction arises.
            - **The breakdown**: "4 divides $p^2$" implies only "2 divides $p$", not "4 divides $p$". The prime-divisibility argument works because for a prime $r$: $r \mid p^2 \Rightarrow r \mid p$. But $4$ is not prime, so this step fails.

2. Exercise 1.2.6. Part d.
    - Prove $\||a| - |b|\| \leq |a - b|$. (The unremarkable identity $a = a - b + b$ may be useful.)
        - **Proof.**
            1. Write $a = (a - b) + b$.
            2. By the triangle inequality: $|a| = |(a-b)+b| \leq |a-b| + |b|$.
            3. Rearrange: $|a| - |b| \leq |a-b|$.
            4. Swap $a$ and $b$: $|b| - |a| \leq |b - a| = |a-b|$.
            5. Since $\||a|-|b|\| = \max(|a|-|b|,\ |b|-|a|)$, combining $(*)$ and $(**)$ gives $\||a|-|b|\| \leq |a-b|.\ \square$

3. Exercise 1.2.8.
    - Here are two important definitions related to a function $f: A \to B$. The function $f$ is **one-to-one (1–1)** if $a_1 \neq a_2$ in $A$ implies $f(a_1) \neq f(a_2)$ in $B$. The function $f$ is **onto** if, given any $b \in B$, it is possible to find an element $a \in A$ for which $f(a) = b$. Give an example of each or state that the request is impossible:
    - (a) $f: \mathbb{N} \to \mathbb{N}$ that is $1$–$1$ but not onto.
        - **Example:** $f(n) = n + 1$.
            - **1–1:** If $f(a_1) = f(a_2)$, then $a_1 + 1 = a_2 + 1$, so $a_1 = a_2$. $\checkmark$
            - **Not onto:** $1 \in \mathbb{N}$ has no preimage, since $n+1 \geq 2$ for all $n \in \mathbb{N}$. $\checkmark$
    - (b) $f: \mathbb{N} \to \mathbb{N}$ that is onto but not $1$–$1$.
        - **Example:** $f(1) = 1,\ f(n) = n-1$ for $n \geq 2$ (i.e., $1, 1, 2, 3, 4, \ldots$).
            - **Onto:** For any $m \in \mathbb{N}$, $f(m+1) = m$. $\checkmark$
            - **Not 1–1:** $f(1) = f(2) = 1$. $\checkmark$
    - (c) $f: \mathbb{N} \to \mathbb{Z}$ that is $1$–$1$ and onto.
        - **Example:** The interleaving bijection: $$f(n) = \begin{cases} \dfrac{n-1}{2} & \text{if } n \text{ is odd} \\[4pt] -\dfrac{n}{2} & \text{if } n \text{ is even.} \end{cases}$$
            - This maps $1 \mapsto 0,\ 2 \mapsto -1,\ 3 \mapsto 1,\ 4 \mapsto -2,\ 5 \mapsto 2,\ \ldots$
            - Every integer appears exactly once, so $f$ is both 1–1 and onto. $\checkmark$

4. Exercise 1.3.8.
    - Compute, without proofs, the suprema and infima (if they exist) of the following sets:
    - (a) $\displaystyle\left\{ \frac{m}{n} : m, n \in \mathbb{N} \text{ with } m < n \right\}$
        - **$\sup = 1$, $\inf = 0$.** Neither is achieved.
            - $\sup = 1$: Since $m < n$, we have $m/n < 1$ always. But $(n-1)/n \to 1$, so $1$ is the least upper bound.
            - $\inf = 0$: $1/n \to 0$ (fixing $m=1$, letting $n \to \infty$), but $m/n \geq 1/n > 0$ always.
    - (b) $\displaystyle\left\{ \frac{(-1)^m}{n} : m, n \in \mathbb{N} \right\}$
        - **$\sup = 1$, $\inf = -1$.** Both are achieved.
            - When $m$ is even: elements are $1, 1/2, 1/3, \ldots$ — positive fractions approaching $0$.
            - When $m$ is odd: elements are $-1, -1/2, -1/3, \ldots$ — negative fractions approaching $0$.
            - $\sup = 1$: achieved at $m = 2, n = 1$ (giving $(-1)^2/1 = 1$).
            - $\inf = -1$: achieved at $m = 1, n = 1$ (giving $(-1)^1/1 = -1$).
    - (c) $\displaystyle\left\{ \frac{n}{3n+1} : n \in \mathbb{N} \right\}$
        - **$\sup = 1/3$, $\inf = 1/4$.** $\inf$ achieved; $\sup$ is not.
            - Rewrite: $n/(3n+1) = 1/(3+1/n)$. As $n \to \infty$, this increases toward $1/3$.
            - $\sup = 1/3$: limit but never reached.
            - $\inf = 1/4$: achieved at $n = 1$ (minimum of the increasing sequence).
    - (d) $\displaystyle\left\{ \frac{m}{m+n} : m, n \in \mathbb{N} \right\}$
        - **$\sup = 1$, $\inf = 0$.** Neither is achieved.
            - Fix $n$, let $m \to \infty$: $m/(m+n) \to 1$ from below.
            - Fix $m$, let $n \to \infty$: $m/(m+n) \to 0$ from above.
            - $\sup = 1$: requires $n = 0 \notin \mathbb{N}$, so never achieved.
            - $\inf = 0$: requires $m = 0 \notin \mathbb{N}$, so never achieved.

5. Exercise 1.4.7.
    - Finish the proof of Theorem 1.4.5 by showing that the assumption $\alpha^2 > 2$ leads to a contradiction of the fact that $\alpha = \sup T$ (where $T = \{t \in \mathbb{R} : t^2 < 2\}$).
    - **Proof.**
        - Assume $\alpha^2 > 2$. We produce an upper bound for $T$ strictly less than $\alpha$, contradicting $\alpha = \sup T$.
        - By the Archimedean Property, choose $n_0 \in \mathbb{N}$ large enough so that $$\frac{1}{n_0} < \frac{\alpha^2 - 2}{2\alpha}.$$
        - Then $\dfrac{2\alpha}{n_0} < \alpha^2 - 2$, so $\alpha^2 - \dfrac{2\alpha}{n_0} > 2$.
        - Compute: $$\left(\alpha - \frac{1}{n_0}\right)^2 = \alpha^2 - \frac{2\alpha}{n_0} + \frac{1}{n_0^2} > \alpha^2 - \frac{2\alpha}{n_0} > 2.$$
        - Therefore $(\alpha - 1/n_0)^2 > 2$, which means $\alpha - 1/n_0$ is an upper bound for $T$ (since any $t \in T$ satisfies $t^2 < 2 < (\alpha - 1/n_0)^2$, hence $t < \alpha - 1/n_0$).
        - But $\alpha - 1/n_0 < \alpha$, contradicting $\alpha = \sup T$ (the **least** upper bound). $\Rightarrow\Leftarrow$
        - Therefore $\alpha^2 > 2$ is impossible. Combined with the textbook proof that $\alpha^2 < 2$ is impossible, we conclude $\alpha^2 = 2$. $\square$

6. Exercise 1.5.6. (Extra Credit)
    - (a) Give an example of a countable collection of disjoint open intervals.
        - **Example:** $\{(n, n+1) : n \in \mathbb{N}\} = (1,2),\ (2,3),\ (3,4),\ \ldots$
            - Indexed by $\mathbb{N}$, so countable. $\checkmark$
            - Each pair of intervals shares no points, so they are disjoint. $\checkmark$
            - Each is an open interval. $\checkmark$
    - (b) Give an example of an uncountable collection of disjoint open intervals, or argue that no such collection exists.
        - **No such collection exists.**
        - **Proof.**
            1. Let $\mathcal{C}$ be any collection of pairwise disjoint open intervals.
            2. Each interval $(a, b) \in \mathcal{C}$ satisfies $a < b$, so by the density of $\mathbb{Q}$, it contains at least one rational number $r_{(a,b)} \in \mathbb{Q}$.
            3. Since the intervals are pairwise disjoint, $r_{(a,b)} \neq r_{(a',b')}$ for distinct intervals.
            4. This defines an injection $\mathcal{C} \hookrightarrow \mathbb{Q}$.
            5. Since $\mathbb{Q}$ is countable, $\mathcal{C}$ is at most countable. $\square$

7. Exercise 1.6.6. Part b.
    - Letting $C = \{1, 2, 3, 4\}$, produce an example of a $1$–$1$ map $g: C \to \mathcal{P}(C)$.
        - **Example:** Define $g(n) = \{n\}$ for each $n \in C$:
            $$g(1) = \{1\},\quad g(2) = \{2\},\quad g(3) = \{3\},\quad g(4) = \{4\}.$$
        - **$g$ is $1$–$1$:** If $g(a) = g(b)$, then $\{a\} = \{b\}$, so $a = b$. $\checkmark$
        - **$g$ is not onto:** $|\mathcal{P}(C)| = 2^4 = 16$ but $|C| = 4$, so the range of $g$ has only $4$ elements out of $16$ — far from exhausting $\mathcal{P}(C)$.
        - **Why onto is impossible (general):** By Cantor's Theorem (Theorem 1.6.2), for any set $A$, there is no surjection $f: A \to \mathcal{P}(A)$. The construction $B = \{a \in A : a \notin f(a)\}$ always produces a set not in the range of $f$.
