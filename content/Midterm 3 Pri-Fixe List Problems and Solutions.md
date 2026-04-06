# Midterm 3 Pri-Fixe List Problems and Solutions

## Definitions and Theorems

- **Definition 4.2.1 (Functional Limit).** (pg. 117)
    - Let $f : A \to \mathbb{R}$, and let $c$ be a limit point of the domain $A$. We say that $\lim_{x \to c} f(x) = L$ provided that, for all $\epsilon > 0$, there exists a $\delta > 0$ such that whenever $0 < |x - c| < \delta$ (and $x \in A$) it follows that $|f(x) - L| < \epsilon$.
        - Key distinctions from the sequence definition:
            - $0 < |x - c|$ means $x \neq c$ — the limit does not care about the value at the point
            - $\delta$ responds to $\epsilon$; you must produce $\delta$ given any $\epsilon$
        - Professor's phrasing: the game is "someone gives you $\epsilon$, you must produce $\delta$"; the handle is $|x - c| < \delta$, and the goal is to make $|f(x) - L| < \epsilon$ by controlling the handle

- **Theorem 4.2.3 (Sequential Criterion for Functional Limits).** (pg. 117)
    - Given $f : A \to \mathbb{R}$ and a limit point $c$ of $A$, the following are equivalent:
        - (i) $\lim_{x \to c} f(x) = L$
        - (ii) For every sequence $(x_n) \subseteq A$ with $x_n \neq c$ and $x_n \to c$, it follows that $f(x_n) \to L$

- **Corollary 4.2.4 (Algebraic Limit Theorem for Functional Limits).** (pg. 118)
    - If $\lim_{x \to c} f(x) = L$ and $\lim_{x \to c} g(x) = M$, then:
        - (i) $\lim_{x \to c} [f(x) + g(x)] = L + M$
        - (ii) $\lim_{x \to c} f(x) g(x) = LM$
        - (iii) $\lim_{x \to c} f(x) / g(x) = L/M$ provided $M \neq 0$

- **Definition 4.3.1 (Continuity).** (pg. 122)
    - A function $f : A \to \mathbb{R}$ is continuous at a point $c \in A$ if, for all $\epsilon > 0$, there exists $\delta > 0$ such that whenever $|x - c| < \delta$ (and $x \in A$) it follows that $|f(x) - f(c)| < \epsilon$.
        - Distinction from functional limits: $c$ must be in the domain and $f(c)$ is the target, not an external $L$; also no restriction $x \neq c$
        - Shorthand when $c$ is a limit point: $f$ continuous at $c$ iff $\lim_{x \to c} f(x) = f(c)$

- **Theorem 4.3.2 (Characterizations of Continuity).** (pg. 123)
    - $f : A \to \mathbb{R}$ is continuous at $c \in A$ iff any one of the following holds:
        - (i) $\epsilon$-$\delta$ definition (same as Definition 4.3.1)
        - (ii) For all $V_\epsilon(f(c))$, there exists $V_\delta(c)$ with $f(V_\delta(c) \cap A) \subseteq V_\epsilon(f(c))$
        - (iii) If $(x_n) \to c$ with $x_n \in A$, then $f(x_n) \to f(c)$
        - (iv) If $c$ is a limit point of $A$: $\lim_{x \to c} f(x) = f(c)$
    - Professor note: (iii) is the most useful for showing discontinuity (just find one bad sequence)

- **Corollary 4.3.3 (Criterion for Discontinuity).** (pg. 123)
    - If there exists a sequence $(x_n) \subseteq A$ with $(x_n) \to c$ but $f(x_n) \not\to f(c)$, then $f$ is not continuous at $c$.

- **Theorem 4.4.1 (Preservation of Compact Sets).** (pg. 129)
    - If $f : A \to \mathbb{R}$ is continuous and $K \subseteq A$ is compact, then $f(K)$ is compact.

- **Theorem 4.4.2 (Extreme Value Theorem).** (pg. 130)
    - If $f : K \to \mathbb{R}$ is continuous on a compact set $K$, then $f$ attains a maximum and minimum value.

- **Definition 4.4.4 (Uniform Continuity).** (pg. 132)
    - $f : A \to \mathbb{R}$ is uniformly continuous on $A$ if for every $\epsilon > 0$ there exists $\delta > 0$ such that for **all** $x, y \in A$, $|x - y| < \delta$ implies $|f(x) - f(y)| < \epsilon$.
        - Key difference from pointwise continuity: the same $\delta$ must work for all points simultaneously — $\delta$ depends only on $\epsilon$, not on any particular $c$

- **Theorem 4.4.5 (Sequential Criterion for Absence of Uniform Continuity).** (pg. 132)
    - $f : A \to \mathbb{R}$ fails to be uniformly continuous on $A$ iff there exists $\epsilon_0 > 0$ and sequences $(x_n), (y_n) \subseteq A$ such that $|x_n - y_n| \to 0$ but $|f(x_n) - f(y_n)| \geq \epsilon_0$.

- **Theorem 4.4.7 (Uniform Continuity on Compact Sets).** (pg. 133)
    - A function that is continuous on a compact set $K$ is uniformly continuous on $K$.

- **Theorem 4.5.1 (Intermediate Value Theorem).** (pg. 136)
    - Let $f : [a, b] \to \mathbb{R}$ be continuous. If $L$ is a real number satisfying $f(a) < L < f(b)$ (or $f(a) > L > f(b)$), then there exists a point $c \in (a, b)$ where $f(c) = L$.

## Pri-Fixe List Problems and Solutions

- **4.2.2.** (pg. 120) For each stated limit, find the largest possible $\delta$-neighborhood that is a proper response to the given $\epsilon$ challenge.
    - (a) $\lim_{x \to 3}(5x - 6) = 9$, where $\epsilon = 1$.
        - Strategy: solve the target inequality exactly, then read off the distance.
        1. Solve $|f(x) - 9| < 1$ directly:
            - $|5x - 6 - 9| < 1$
            - $|5x - 15| < 1$
            - $|x - 3| < \dfrac{1}{5}$
            - So the target condition is exactly $x \in \left(\dfrac{14}{5},\ \dfrac{16}{5}\right) = (2.8,\ 3.2)$.
        2. Find the largest $\delta$ so that $(3 - \delta,\ 3 + \delta) \subseteq (2.8,\ 3.2)$:
            - Distance from $3$ to $2.8$ is $0.2 = \dfrac{1}{5}$.
            - Distance from $3$ to $3.2$ is also $0.2 = \dfrac{1}{5}$.
            - Both endpoints are equidistant, so $\delta = \dfrac{1}{5}$.
        3. Verify: $|x - 3| < \dfrac{1}{5}$ implies $|5x - 15| = 5|x - 3| < 5 \cdot \dfrac{1}{5} = 1$. $\checkmark$
    - (b) $\lim_{x \to 4}\sqrt{x} = 2$, where $\epsilon = 1$. *(from 25.3.26 class notes)*
        - Strategy: solve $|\sqrt{x} - 2| < 1$ exactly, then find the closer endpoint.
        1. Solve the target inequality $|\sqrt{x} - 2| < 1$:
            - $-1 < \sqrt{x} - 2 < 1$
            - $1 < \sqrt{x} < 3$
            - $1 < x < 9$
        2. Find the largest $\delta$ so that $(4 - \delta,\ 4 + \delta) \subseteq (1,\ 9)$:
            - Distance from $4$ to $1$ is $3$.
            - Distance from $4$ to $9$ is $5$.
            - The left side is the limiting side, so $\delta = 3$.
        3. Verify both directions:
            - ($\delta = 3$ works): if $|x - 4| < 3$ then $1 < x < 7 \subset (1, 9)$, so $|\sqrt{x} - 2| < 1$. $\checkmark$
            - ($\delta > 3$ fails): if $\delta > 3$, then $4 - \delta < 1$, so we can pick $x \in (4 - \delta,\ 1]$ with $|x - 4| < \delta$ but $|\sqrt{x} - 2| \geq 1$. So $\delta = 3$ is indeed the largest.

- **4.2.3.** (pg. 120) Review the definition of Thomae's function $t(x)$ from Section 4.1.
    - Thomae's function: $t(x) = \begin{cases} 1 & x = 0 \\ \frac{1}{n} & x = \frac{m}{n} \in \mathbb{Q},\ \gcd(|m|,n) = 1,\ n > 0 \\ 0 & x \notin \mathbb{Q} \end{cases}$
    - (a) Construct three sequences $(x_n)$, $(y_n)$, $(z_n)$, each converging to $1$ without using $1$ as a term.
        - $x_n = \dfrac{n+1}{n}$ (rationals approaching $1$ from above; in lowest terms since $\gcd(n+1, n) = 1$)
        - $y_n = \dfrac{2n+1}{2n}$ (rationals approaching $1$ from above with denominators $2n$; in lowest terms since $2n+1$ is odd, $\gcd(2n+1, 2n) = 1$)
        - $z_n = 1 + \dfrac{\sqrt{2}}{n}$ (irrationals approaching $1$ from above, since $\sqrt{2}/n$ is irrational)
    - (b) Compute $\lim t(x_n)$, $\lim t(y_n)$, $\lim t(z_n)$.
        - For $(x_n)$: $t\!\left(\dfrac{n+1}{n}\right) = \dfrac{1}{n} \to 0$
        - For $(y_n)$: $t\!\left(\dfrac{2n+1}{2n}\right) = \dfrac{1}{2n} \to 0$
        - For $(z_n)$: $t\!\left(1 + \dfrac{\sqrt{2}}{n}\right) = 0$ for all $n$ (irrational), so $\to 0$
        - All three limits equal $0$.
    - (c) Conjecture $\lim_{x \to 1} t(x)$ and verify using Definition 4.2.1B.
        - Conjecture: $\lim_{x \to 1} t(x) = 0$.
        - Intuition: the closer a rational is to $1$, the larger its denominator must be, and thus the smaller $t(x)$ is. Irrationals always give $t(x) = 0$.
        - **Proof.**
            1. Let $\epsilon > 0$. Let $T = \{x \in \mathbb{R} : t(x) \geq \epsilon\}$.
                - $x \in T$ iff $x = m/n$ in lowest terms with $n \leq 1/\epsilon$.
                - There are only finitely many such rationals in the interval $[0, 2]$ (the denominator is bounded).
            2. Let $T_0 = T \cap [0, 2] \setminus \{1\}$. Since $T_0$ is finite, define:
                - $\delta = \min \{|1 - y| : y \in T_0\} > 0$ (minimum over a finite, nonempty set)
                - If $T_0$ is empty, any $\delta > 0$ works.
            3. Show $\delta$ works: suppose $0 < |x - 1| < \delta$.
                - Either $x \notin \mathbb{Q}$, in which case $t(x) = 0 < \epsilon$. $\checkmark$
                - Or $x \in \mathbb{Q}$. Since $|x - 1| < \delta$ and $\delta$ was chosen to exclude all elements of $T_0$, we have $x \notin T$, so $t(x) < \epsilon$. $\checkmark$
            4. Thus $t(x) \in V_\epsilon(0)$ for all $x \in V_\delta(1) \setminus \{1\}$, confirming $\lim_{x \to 1} t(x) = 0$.

- **4.2.5.** (pg. 121) Use Definition 4.2.1 to supply a proper proof for the following limit statements.
    - General template: factor to isolate the handle $|x - c|$, bound any leftover term by restricting $\delta \leq 1$, then choose $\delta = \min\{1,\ \epsilon/M\}$.
    - (a) $\lim_{x \to 2}(3x + 4) = 10$.
        1. Compute $|f(x) - 10|$:
            - $|(3x + 4) - 10| = |3x - 6| = 3|x - 2|$
        2. Choose $\delta = \epsilon/3$. Then $|x - 2| < \delta$ implies:
            - $|f(x) - 10| = 3|x - 2| < 3 \cdot \dfrac{\epsilon}{3} = \epsilon$. $\checkmark$
    - (b) $\lim_{x \to 0} x^3 = 0$.
        1. Compute $|f(x) - 0|$:
            - $|x^3 - 0| = |x|^3$
        2. Choose $\delta = \epsilon^{1/3}$. Then $|x| < \delta$ implies:
            - $|x^3| = |x|^3 < (\epsilon^{1/3})^3 = \epsilon$. $\checkmark$
    - (c) $\lim_{x \to 2}(x^2 + x - 1) = 5$.
        1. Factor the expression $|(x^2 + x - 1) - 5|$:
            - $|x^2 + x - 6| = |x + 3||x - 2|$
        2. Bound $|x + 3|$ by restricting $\delta \leq 1$, so $x \in (1, 3)$, hence $|x + 3| < 6$.
        3. Choose $\delta = \min\{1,\ \epsilon/6\}$. Then $|x - 2| < \delta$ implies:
            - $|(x^2 + x - 1) - 5| = |x + 3||x - 2| < 6 \cdot \dfrac{\epsilon}{6} = \epsilon$. $\checkmark$
    - (d) $\lim_{x \to 3} 1/x = 1/3$.
        1. Factor the expression $|1/x - 1/3|$:
            - $\left|\dfrac{1}{x} - \dfrac{1}{3}\right| = \dfrac{|3 - x|}{3|x|} = \dfrac{|x - 3|}{3|x|}$
        2. Bound $1/|3x|$ by restricting $\delta \leq 1$, so $x \in (2, 4)$, hence $|x| > 2$ and $\dfrac{1}{3|x|} < \dfrac{1}{6}$.
        3. Choose $\delta = \min\{1,\ 6\epsilon\}$. Then $|x - 3| < \delta$ implies:
            - $\left|\dfrac{1}{x} - \dfrac{1}{3}\right| < \dfrac{1}{6} \cdot |x - 3| < \dfrac{1}{6} \cdot 6\epsilon = \epsilon$. $\checkmark$

- **4.2.6.** (pg. 121) Decide if the following claims are true or false, and give short justifications.
    - (a) If a particular $\delta$ has been constructed as a suitable response to a particular $\epsilon$ challenge, then any smaller positive $\delta$ will also suffice.
        - **True.**
            - If $|x - a| < \delta'$ and $\delta' < \delta_0$, then $|x - a| < \delta' < \delta_0$, so the condition $|x - a| < \delta_0$ is satisfied.
            - Since $\delta_0$ was already a valid response, $|f(x) - L| < \epsilon$ follows.
            - So any $\delta' < \delta_0$ also works.
    - (b) If $\lim_{x \to a} f(x) = L$ and $a$ happens to be in the domain of $f$, then $L = f(a)$.
        - **False.**
            - Counterexample: let $f(x) = \begin{cases} 0 & x \neq a \\ 1 & x = a \end{cases}$.
            - Then $\lim_{x \to a} f(x) = 0$ (for $x$ near $a$ with $x \neq a$, $f(x) = 0$).
            - But $f(a) = 1 \neq 0 = L$.
            - The limit ignores the value at $a$; it only looks at $x \neq a$.
    - (c) If $\lim_{x \to a} f(x) = L$, then $\lim_{x \to a} 3[f(x) - 2]^2 = 3(L-2)^2$.
        - **True.**
            - By Corollary 4.2.4 (Algebraic Limit Theorem for Functional Limits):
                - $\lim (f(x) - 2) = L - 2$
                - $\lim (f(x) - 2)^2 = (L-2)^2$ (product rule)
                - $\lim 3(f(x) - 2)^2 = 3(L-2)^2$ (scalar multiple)
    - (d) If $\lim_{x \to a} f(x) = 0$, then $\lim_{x \to a} f(x)g(x) = 0$ for any function $g$.
        - **False.**
            - Counterexample: let $f(x) = x$ and $g(x) = 1/x$ on $A = \mathbb{R} \setminus \{0\}$, with $a = 0$.
            - $\lim_{x \to 0} f(x) = \lim_{x \to 0} x = 0$. $\checkmark$
            - But $f(x)g(x) = x \cdot \dfrac{1}{x} = 1$ for all $x \neq 0$, so $\lim_{x \to 0} f(x)g(x) = 1 \neq 0$.
            - The result fails because $g$ is unbounded near $a$.

- **4.3.6.** (pg. 127) Provide an example of each or explain why the request is impossible. *(Solutions manual blank — part (a) from 6.4.26 class notes; parts (b)–(e) from first principles.)*
    - (a) Two functions $f$ and $g$, neither continuous at $0$, but such that $f(x)+g(x)$ and $f(x)g(x)$ are both continuous at $0$.
        - **Possible.**
        - Example (professor's, 6.4.26): let $f(x)=\begin{cases}1,&x\ge 0\\-1,&x<0\end{cases}$ and $g(x)=-f(x)=\begin{cases}-1,&x\ge 0\\1,&x<0\end{cases}$.
        - Neither $f$ nor $g$ is continuous at $0$ (both jump between $\pm 1$).
        - Sum: $(f+g)(x)=0$ for all $x$ — identically $0$, hence continuous. $\checkmark$
        - Product: $(fg)(x)=-(f(x))^2=-1$ for all $x$ — identically $-1$, hence continuous. $\checkmark$
        - **N.B.**: on the exam, just draw the four sketches ([see pic](https://photos.janovitch.com/share/6Q0SB6cdmfaOiYUHjt_6hxEOPO1C5dPUz6aOEJre88X6IbM19I3h9Q8TYUvyvHH1nDI)): a number line for $f$ (flat at $y=0$ with a filled dot above the axis at $x=0$, showing the jump up to $1$), a number line for $g$ (same but dot below the axis, jump down to $-1$), then $f+g$ (a perfectly flat line at $y=0$ — the jumps cancel), and $fg$ (a perfectly flat line at $y=-1$ — the product is constant). The pictures make the cancellation immediately obvious.
    - (b) A function $f$ continuous at $0$ and $g$ not continuous at $0$, such that $f(x)+g(x)$ is continuous at $0$.
        - **Impossible.**
        - If $f+g$ is continuous at $0$ and $f$ is continuous at $0$, then $g=(f+g)-f$ is a difference of two functions continuous at $0$. By the Algebraic Continuity Theorem (Theorem 4.3.4), $g$ is continuous at $0$ — contradiction.
    - (c) A function $f$ continuous at $0$ and $g$ not continuous at $0$, such that $f(x)g(x)$ is continuous at $0$.
        - **Possible.**
        - Example: let $f(x)=0$ identically, and let $g$ be any function discontinuous at $0$ (e.g., $g(x)=\begin{cases}1,&x=0\\0,&x\ne 0\end{cases}$).
        - $f$ is continuous at $0$; $g$ is not.
        - $(fg)(x)=0\cdot g(x)=0$ for all $x$ — identically $0$, hence continuous. $\checkmark$
        - **N.B.**: the zero value of $f$ at $0$ "absorbs" the discontinuity of $g$. If $f(0)\ne 0$ this approach fails.
    - (d) A function $f$ not continuous at $0$ such that $f(x)+\dfrac{1}{f(x)}$ is continuous at $0$.
        - **Possible.**
        - Strategy: if $a+1/a=b+1/b$ with $a\ne b$, then $a-b=(a-b)/(ab)$, which forces $ab=1$, i.e., $b=1/a$. So let $f$ jump between $a$ and $1/a$.
        - Example: let $f(x)=\begin{cases}2,&x\ge 0\\\frac{1}{2},&x<0\end{cases}$.
        - $f$ is not continuous at $0$ (jumps from $\tfrac{1}{2}$ to $2$).
        - $f(x)+\dfrac{1}{f(x)}=2+\dfrac{1}{2}=\dfrac{5}{2}$ for $x\ge 0$, and $\dfrac{1}{2}+2=\dfrac{5}{2}$ for $x<0$.
        - So $f+1/f=\dfrac{5}{2}$ everywhere — constant, hence continuous. $\checkmark$
    - (e) A function $f$ not continuous at $0$ such that $[f(x)]^3$ is continuous at $0$.
        - **Impossible.**
        - The cube root function $t\mapsto t^{1/3}$ is continuous on all of $\mathbb{R}$ (unlike $\sqrt{\cdot}$, it passes through $0$ without issue).
        - If $[f(x)]^3$ is continuous at $0$, then $f(x)=\bigl([f(x)]^3\bigr)^{1/3}$ is the composition of a continuous function with a continuous function, hence continuous at $0$ — contradiction.

- **4.3.8.** (pg. 127) Decide if the following claims are true or false, providing either a short proof or counterexample. Assume $g$ is defined and continuous on all of $\mathbb{R}$.
    - (a) If $g(x) \geq 0$ for all $x < 1$, then $g(1) \geq 0$ as well.
        - **True.**
            - Choose the sequence $x_n = 1 - 1/n$. Then $x_n < 1$ and $x_n \to 1$.
            - Since $g(x_n) \geq 0$ for all $n$, and $g$ is continuous at $1$:
                - $g(1) = \lim_{n \to \infty} g(x_n) \geq 0$
                - (by the Order Limit Theorem: if $a_n \geq 0$ and $a_n \to a$, then $a \geq 0$)
    - (b) If $g(r) = 0$ for all $r \in \mathbb{Q}$, then $g(x) = 0$ for all $x \in \mathbb{R}$.
        - **True.**
            - Since $\mathbb{Q}$ is dense in $\mathbb{R}$, for any $x \in \mathbb{R}$ there exists a sequence of rationals $(r_n) \to x$.
            - $g(r_n) = 0$ for all $n$.
            - By continuity of $g$ at $x$ (Theorem 4.3.2(iii)): $g(x) = \lim g(r_n) = \lim 0 = 0$.
    - (c) If $g(x_0) > 0$ for a single point $x_0 \in \mathbb{R}$, then $g(x)$ is in fact strictly positive for uncountably many points.
        - **True.**
            - Let $\epsilon = g(x_0)/2 > 0$.
            - By continuity of $g$ at $x_0$, there exists $\delta > 0$ such that $|x - x_0| < \delta$ implies $|g(x) - g(x_0)| < \epsilon = g(x_0)/2$.
            - This means $g(x) > g(x_0) - g(x_0)/2 = g(x_0)/2 > 0$ for all $x \in (x_0 - \delta,\ x_0 + \delta)$.
            - The interval $(x_0 - \delta,\ x_0 + \delta)$ is uncountable, so $g > 0$ on uncountably many points. $\checkmark$

- **4.3.9.** (pg. 128) Assume $h : \mathbb{R} \to \mathbb{R}$ is continuous on $\mathbb{R}$ and let $K = \{x : h(x) = 0\}$. Show that $K$ is a closed set.
    - Strategy: show $K$ contains all its limit points by using the sequential characterization of continuity.
    1. Let $c$ be an arbitrary limit point of $K$.
        - By Theorem 3.2.5 (characterization of limit points via sequences), there exists a sequence $(x_n) \subseteq K$ with $x_n \neq c$ and $x_n \to c$.
    2. Since each $x_n \in K$, we have $h(x_n) = 0$ for all $n$.
    3. Since $h$ is continuous at $c$ (Theorem 4.3.2(iii)):
        - $h(c) = \lim_{n \to \infty} h(x_n) = \lim_{n \to \infty} 0 = 0$
    4. Therefore $c \in K$, which means $K$ contains all its limit points, so $K$ is closed. $\square$

- **4.3.11.** (pg. 128) *(Contraction Mapping Theorem — professor opened final lecture with this; treat as exam-likely)* Let $f : \mathbb{R} \to \mathbb{R}$, and assume there is a constant $c$ with $0 < c < 1$ such that $|f(x) - f(y)| \leq c|x - y|$ for all $x, y \in \mathbb{R}$.
    - (a) Show that $f$ is continuous on $\mathbb{R}$.
        1. Let $\epsilon > 0$ and fix $y \in \mathbb{R}$ (arbitrary).
        2. Choose $\delta = \epsilon/c$.
        3. Then $|x - y| < \delta$ implies:
            - $|f(x) - f(y)| \leq c|x - y| < c \cdot \dfrac{\epsilon}{c} = \epsilon$
        4. Since $y$ is arbitrary, $f$ is continuous on all of $\mathbb{R}$. $\square$
    - (b) Pick $y_1 \in \mathbb{R}$ and let $y_{n+1} = f(y_n)$. Show that $(y_n)$ is a Cauchy sequence.
        - Key lemma: differences between consecutive terms shrink by factor $c$.
        1. For any $n$, apply the contraction condition:
            - $|y_{n+1} - y_n| = |f(y_n) - f(y_{n-1})| \leq c|y_n - y_{n-1}|$
            - By induction: $|y_{n+1} - y_n| \leq c^{n-1}|y_2 - y_1|$
        2. For $m < n$, apply the triangle inequality:
            - $|y_m - y_n| \leq |y_m - y_{m+1}| + |y_{m+1} - y_{m+2}| + \cdots + |y_{n-1} - y_n|$
            - $\leq c^{m-1}|y_2 - y_1| + c^m|y_2 - y_1| + \cdots + c^{n-2}|y_2 - y_1|$
            - $= c^{m-1}|y_2 - y_1|(1 + c + \cdots + c^{n-m-1})$
            - $< c^{m-1}|y_2 - y_1| \cdot \dfrac{1}{1 - c}$
        3. Since $0 < c < 1$, $c^{m-1} \to 0$. So given $\epsilon > 0$, choose $N$ large enough that $c^{N-1} < \dfrac{\epsilon(1-c)}{|y_2 - y_1|}$. Then $n > m \geq N$ implies $|y_m - y_n| < \epsilon$.
        4. Therefore $(y_n)$ is Cauchy, and $y = \lim y_n$ exists. $\square$
    - (c) Prove that $y = \lim y_n$ is a fixed point of $f$ and that it is unique.
        - Existence:
        1. Since $f$ is continuous (part (a)) and $y_n \to y$:
            - $f(y) = \lim_{n \to \infty} f(y_n) = \lim_{n \to \infty} y_{n+1} = y$
            - So $f(y) = y$, i.e., $y$ is a fixed point. $\square$
        - Uniqueness:
        1. Suppose $y'$ is another fixed point, so $f(y') = y'$.
        2. Then $|y - y'| = |f(y) - f(y')| \leq c|y - y'|$.
        3. Since $0 < c < 1$, $(1 - c)|y - y'| \leq 0$, which forces $|y - y'| = 0$, i.e., $y = y'$. $\square$
    - (d) Prove that for any $x \in \mathbb{R}$, the sequence $(x,\ f(x),\ f(f(x)),\dots)$ converges to $y$.
        - **Orbit** (plain language): the orbit of a starting point $x$ is the sequence you get by repeatedly applying $f$ — i.e. $z_1 = x,\ z_2 = f(x),\ z_3 = f(f(x)), \ldots$ It's the trail of points you visit.
        - Professor's intuition (1.4.26, 6.4.26): picture the orbit — each step, the gap between consecutive iterates is only $c$ times the previous gap. Since $c < 1$, the gaps shrink geometrically to $0$, so the iterates cluster at a single point. Uniqueness then forces that point to be $y$.
            - **N.B.**: [see cobweb diagram](https://photos.janovitch.com/share/5CSr03SHfh7FXFaEdQ3c7rDoVrG9uAwlCH6cyVsfupkCKIgrE9qMlnJo8fMu8t7i488) — draw the function curve and the diagonal $y = x$; from $z_1$, go up to the curve (gives $z_2$), sideways to the diagonal (resets to x-axis), up to the curve again (gives $z_3$), and so on; the staircase spirals inward to the fixed point where the curve crosses the diagonal.
        1. Let $z_1 = x$ and $z_{n+1} = f(z_n)$. By the contraction condition, consecutive gaps shrink by factor $c$:
            - $|z_{n+1} - z_n| = |f(z_n) - f(z_{n-1})| \leq c|z_n - z_{n-1}| \leq \cdots \leq c^{n-1}|z_2 - z_1|$
            - Since $c^{n-1} \to 0$, the gaps go to $0$, so $(z_n)$ is Cauchy and converges to some limit $z$.
        2. Since $f$ is continuous (part (a)) and $z_n \to z$:
            - $f(z) = \lim f(z_n) = \lim z_{n+1} = z$
            - So $z$ is a fixed point of $f$.
        3. By uniqueness (part (c)), $z = y$. $\square$

- **4.4.1.** (pg. 134) (a) Show that $f(x) = x^3$ is continuous on all of $\mathbb{R}$. (b) Argue, using Theorem 4.4.5, that $f$ is not uniformly continuous on $\mathbb{R}$. (c) Show that $f$ is uniformly continuous on any bounded subset of $\mathbb{R}$.
    - (a) Show $f(x) = x^3$ is continuous on $\mathbb{R}$.
        1. Fix $c \in \mathbb{R}$ and factor:
            - $|x^3 - c^3| = |x - c||x^2 + xc + c^2|$
        2. Restrict $\delta \leq 1$ so $x \in (c - 1, c + 1)$. Bound the second factor:
            - $|x^2 + xc + c^2| \leq |x|^2 + |x||c| + |c|^2 \leq (|c|+1)^2 + (|c|+1)|c| + |c|^2 < 3(|c|+1)^2$
        3. Choose $\delta = \min\!\left\{1,\ \dfrac{\epsilon}{3(|c|+1)^2}\right\}$. Then $|x - c| < \delta$ implies:
            - $|x^3 - c^3| < \dfrac{\epsilon}{3(|c|+1)^2} \cdot 3(|c|+1)^2 = \epsilon$. $\checkmark$ $\square$
    - (b) $f$ is not uniformly continuous on $\mathbb{R}$.
        - Strategy: produce sequences with $|x_n - y_n| \to 0$ but $|f(x_n) - f(y_n)| \not\to 0$ (Theorem 4.4.5).
        1. Let $x_n = n$ and $y_n = n + 1/n$.
            - $|x_n - y_n| = 1/n \to 0$. $\checkmark$
        2. Compute $|x_n^3 - y_n^3|$:
            - $(n + 1/n)^3 = n^3 + 3n + 3/n + 1/n^3$
            - $|x_n^3 - y_n^3| = |(n + 1/n)^3 - n^3| = 3n + 3/n + 1/n^3 \geq 3$ for all $n$.
        3. So $|f(x_n) - f(y_n)| \geq 3$ for all $n$, while $|x_n - y_n| \to 0$.
        4. By Theorem 4.4.5 with $\epsilon_0 = 3$, $f$ is not uniformly continuous on $\mathbb{R}$. $\square$
    - (c) $f$ is uniformly continuous on any bounded subset $A \subseteq \mathbb{R}$.
        1. Since $A$ is bounded, there exists $M > 0$ with $A \subseteq [-M, M]$.
        2. For $x, c \in A$: $|x^2 + xc + c^2| \leq 3M^2$.
        3. Choose $\delta = \epsilon/(3M^2)$ (independent of $c$). Then $|x - c| < \delta$ implies:
            - $|x^3 - c^3| = |x - c||x^2 + xc + c^2| < \dfrac{\epsilon}{3M^2} \cdot 3M^2 = \epsilon$. $\checkmark$ $\square$

- **4.4.2.** (pg. 134) (b) Is $g(x) = \sqrt{x^2 + 1}$ uniformly continuous on $(0, 1)$?
    - **Yes**, $g$ is uniformly continuous on $(0, 1)$.
    - Strategy: show $g$ is Lipschitz with constant $M = 1$, which implies uniform continuity.
    1. Factor using the conjugate:
        - $|g(x) - g(y)| = |\sqrt{x^2+1} - \sqrt{y^2+1}| = \dfrac{|x^2 - y^2|}{\sqrt{x^2+1} + \sqrt{y^2+1}} = \dfrac{|x-y||x+y|}{\sqrt{x^2+1} + \sqrt{y^2+1}}$
    2. Bound from above:
        - Denominator: $\sqrt{x^2+1} + \sqrt{y^2+1} \geq 1 + 1 = 2$ (since $\sqrt{t^2+1} \geq 1$ for all $t$)
        - Numerator: for $x, y \in (0, 1)$, $|x + y| < 2$
        - So $|g(x) - g(y)| \leq \dfrac{|x-y| \cdot 2}{2} = |x-y|$
    3. Thus $g$ is Lipschitz with $M = 1$: $|g(x) - g(y)| \leq 1 \cdot |x - y|$ for all $x, y \in (0, 1)$.
    4. Lipschitz implies uniformly continuous: given $\epsilon > 0$, choose $\delta = \epsilon$. Then $|x - y| < \delta$ implies $|g(x) - g(y)| \leq |x - y| < \epsilon$. $\checkmark$ $\square$

- **4.4.4.** (pg. 134) Decide whether each of the following statements is true or false, justifying each conclusion.
    - (a) If $f$ is continuous on $[a, b]$ with $f(x) > 0$ for all $x \in [a, b]$, then $1/f$ is bounded on $[a, b]$.
        - **True.**
            - $[a, b]$ is compact. By the Extreme Value Theorem (Theorem 4.4.2), $f$ attains its minimum at some $x_0 \in [a, b]$.
            - Let $m = f(x_0) > 0$ (positive by hypothesis).
            - Then $f(x) \geq m > 0$ for all $x \in [a, b]$, so $\dfrac{1}{f(x)} \leq \dfrac{1}{m}$ for all $x \in [a, b]$.
            - Therefore $1/f$ is bounded above by $1/m$.
    - (b) If $f$ is uniformly continuous on a bounded set $A$, then $f(A)$ is bounded.
        - **True.**
            - Let $\epsilon = 1$. Since $f$ is uniformly continuous on $A$, there exists $\delta > 0$ such that $|x - y| < \delta$ implies $|f(x) - f(y)| < 1$ for all $x, y \in A$.
            - Since $A$ is bounded, $A \subseteq [-M, M]$ for some $M$. Cover $[-M, M]$ with finitely many intervals of length $\delta$: say $I_1, I_2, \dots, I_k$ where $k \leq \lceil 2M/\delta \rceil + 1$.
            - For each $j$, pick a sample point $x_j \in A \cap I_j$ if that intersection is nonempty. Let $B = \max_j |f(x_j)|$.
            - For any $x \in A$, $x$ lies in some $I_j$, so $|x - x_j| < \delta$, hence $|f(x) - f(x_j)| < 1$.
            - Thus $|f(x)| \leq |f(x) - f(x_j)| + |f(x_j)| < 1 + B$ for all $x \in A$.
            - So $f(A) \subseteq (-(1+B),\ 1+B)$ is bounded.
    - (c) If $f$ is defined on $\mathbb{R}$ and $f(K)$ is compact whenever $K$ is compact, then $f$ is continuous on $\mathbb{R}$.
        - **False.**
            - Counterexample: define $f(x) = \begin{cases} 0 & x = 0 \\ 1 & x \neq 0 \end{cases}$.
            - $f$ is not continuous at $0$ (a sequence of nonzero values approaching $0$ gives $f(x_n) = 1 \not\to 0 = f(0)$).
            - But $f$ maps every compact set to a compact set: for any compact $K$, $f(K) \subseteq \{0, 1\}$. Any subset of $\{0, 1\}$ is finite, hence closed and bounded, hence compact.
            - So preserving compactness does not imply continuity.

- **4.4.6.** (pg. 135) Give an example of each of the following, or state that such a request is impossible.
    - (a) A continuous $f : (0, 1) \to \mathbb{R}$ and a Cauchy sequence $(x_n)$ such that $f(x_n)$ is not a Cauchy sequence.
        - **Possible.** Example: $f(x) = 1/x$ is continuous on $(0, 1)$.
            - Let $x_n = 1/n$. Then $(x_n) \to 0$, so $(x_n)$ is Cauchy.
            - But $f(x_n) = n \to \infty$, which is not Cauchy.
            - This works because $(0, 1)$ is not closed — the Cauchy sequence converges outside the domain, and $f$ blows up near the missing endpoint.
    - (b) A uniformly continuous $f : (0, 1) \to \mathbb{R}$ and a Cauchy sequence $(x_n)$ such that $f(x_n)$ is not a Cauchy sequence.
        - **Impossible.** A uniformly continuous function always sends Cauchy sequences to Cauchy sequences.
        - **Proof.**
            1. Let $\epsilon > 0$. Since $f$ is uniformly continuous, there exists $\delta > 0$ such that $|x - y| < \delta$ implies $|f(x) - f(y)| < \epsilon$ for all $x, y \in (0, 1)$.
            2. Since $(x_n)$ is Cauchy, there exists $N$ such that $m, n \geq N$ implies $|x_n - x_m| < \delta$.
            3. Then $|f(x_n) - f(x_m)| < \epsilon$ for all $m, n \geq N$.
            4. Therefore $(f(x_n))$ is Cauchy. $\square$
    - (c) A continuous $f : [0, \infty) \to \mathbb{R}$ and a Cauchy sequence $(x_n)$ such that $f(x_n)$ is not a Cauchy sequence.
        - **Impossible.** On $[0, \infty)$, every Cauchy sequence converges to a limit inside $[0, \infty)$.
        - **Proof.**
            1. Since $(x_n)$ is Cauchy in $\mathbb{R}$, it converges: $x_n \to x$.
            2. Since $[0, \infty)$ is closed and each $x_n \geq 0$, we have $x \in [0, \infty)$.
            3. Since $f$ is continuous at $x$: $f(x_n) \to f(x)$ (Theorem 4.3.2(iii)).
            4. A convergent sequence is Cauchy, so $(f(x_n))$ is Cauchy. $\square$

- **4.4.7.** (pg. 135) Prove that $f(x) = \sqrt{x}$ is uniformly continuous on $[0, \infty)$.
    - Use the professor's proof (1.4.26 and 6.4.26 class notes): WLOG squaring approach.
    - **N.B.**: Do not use the textbook/solutions manual approach (splitting into $[0,1]$ and $[1,\infty)$ and combining via Exercise 4.4.5). The professor's approach below is shorter.
    1. Establish the key inequality $|\sqrt{x} - \sqrt{y}| \leq \sqrt{|x-y|}$ for all $x, y \geq 0$.
        - The case $x = y$ is trivial. Assume $x \neq y$ and WLOG $x > y \geq 0$.
        - Then $|\sqrt{x} - \sqrt{y}| = \sqrt{x} - \sqrt{y}$. Square both sides:
            - $(\sqrt{x} - \sqrt{y})^2 = x + y - 2\sqrt{xy}$
        - Since $x > y \geq 0$, we have $\sqrt{x} > \sqrt{y} \geq 0$, so $2\sqrt{xy} = 2\sqrt{x}\cdot\sqrt{y} \geq 2y$. Therefore:
            - $(\sqrt{x} - \sqrt{y})^2 = x + y - 2\sqrt{xy} \leq x + y - 2y = x - y = |x - y|$
        - Both sides are nonnegative, so taking square roots: $|\sqrt{x} - \sqrt{y}| \leq \sqrt{|x-y|}$
    2. Choose $\delta = \epsilon^2$. Given any $x, y \geq 0$ with $|x - y| < \delta$:
        - $|\sqrt{x} - \sqrt{y}| \leq \sqrt{|x - y|} < \sqrt{\delta} = \sqrt{\epsilon^2} = \epsilon$. $\checkmark$
    3. Since $\delta = \epsilon^2$ depends only on $\epsilon$ (not on $x$ or $y$), $\sqrt{x}$ is uniformly continuous on $[0, \infty)$. $\square$

- **4.5.7.** (pg. 140) Let $f$ be a continuous function on the closed interval $[0, 1]$ with range also contained in $[0, 1]$. Prove that $f$ must have a fixed point; that is, show $f(x) = x$ for at least one value of $x \in [0, 1]$.
    - Strategy (from 1.4.26 class notes): define a helper function, check its sign at the endpoints, apply IVT.
    1. Define $h(x) = f(x) - x$.
        - $h$ is continuous on $[0, 1]$ since $f$ and the identity function are both continuous (Algebraic Continuity Theorem).
    2. Check the signs at the endpoints.
        - At $x = 0$: $h(0) = f(0) - 0 = f(0) \geq 0$ since $f(0) \in [0, 1]$.
        - At $x = 1$: $h(1) = f(1) - 1 \leq 0$ since $f(1) \in [0, 1]$ means $f(1) \leq 1$.
    3. Handle the trivial cases:
        - If $h(0) = 0$, then $f(0) = 0$ and $x = 0$ is a fixed point. Done.
        - If $h(1) = 0$, then $f(1) = 1$ and $x = 1$ is a fixed point. Done.
    4. Non-trivial case: $h(0) > 0$ and $h(1) < 0$.
        - By the Intermediate Value Theorem (Theorem 4.5.1) applied to $h$ on $[0, 1]$:
            - $h(0) > 0 > h(1)$, so there exists $c \in (0, 1)$ with $h(c) = 0$.
            - That is, $f(c) - c = 0$, so $f(c) = c$. $\checkmark$
    5. In all cases, there exists $c \in [0, 1]$ with $f(c) = c$. $\square$
    - Professor's geometric intuition (6.4.26): draw the unit square $[0,1]\times[0,1]$ with the diagonal $y=x$. Since $f(0) \geq 0$, the graph starts at or above the diagonal at $x=0$; since $f(1) \leq 1$, the graph ends at or below the diagonal at $x=1$. A continuous curve that starts above $y=x$ and ends below it must cross the diagonal at least once — that crossing point is the fixed point.
