# Midterm II Pri Fixe List Problems & Solutions
## Definitions and Theorems referenced in Pri Fixe List

- **Definition 2.2.3 (Convergence of a Sequence).** (pg. 43)
    - A sequence $(a_{n})$ converges to a real number $a$ if, for every positive number $\epsilon$, there exists an $N \in \mathbb{N}$ such that whenever $n \geq N$ it follows that $\lvert a_{n} - a \rvert < \epsilon$.
        - Intuition your professor used:
            - Think “dots on the number line.”
            - Draw an $\epsilon$-radius “ball” (interval) around $a$.
            - Eventually all dots enter and then stay inside.
        - Quantifier order (what can break memorized statements):
            - $\epsilon$ comes first (adversary chooses how tight).
            - Then you must produce $N$ (your response).

- **Definition 3.2.1.** (pg. 88)
    - A set $O \subseteq \mathbb{R}$ is _open_ if for all points $a \in O$ there exists an $\epsilon$-neighborhood $V_{\epsilon}(a) \subseteq O$.
        - Picture:
            - Big region = the set.
            - Pick a point $a$ inside.
            - You can draw a small ball around $a$ fully contained in the set.

- **Theorem 3.2.3.** (pg. 89)
    - (i) The union of an arbitrary collection of open sets is open.
    - (ii) The intersection of a finite collection of open sets is open.
    - **Proof.**
        1. To prove (i), we let $\{ O_{\lambda} : \lambda \in \Lambda \}$ be a collection of open sets and let $O = \bigcup_{\lambda \in\Lambda} O_{\lambda}$. Let $a$ be an arbitrary element of $O$. In order to show that $O$ is open, Definition 3.2.1 insists that we produce an $\epsilon$-neighborhood of $a$ completely contained in $O$. But $a \in O$ implies that $a$ is an element of at least on particular $O_{\lambda'}$. Because we are assuming $O_{\lambda'}$ is open, we can use Definition 3.2.1 to assert that there exists $V_{\epsilon} \subseteq O_{\lambda'}$. The fact that $O_{\lambda'} \subseteq O$ allows us to conclude that $V_{\epsilon}(a) \subseteq O$. This completes the proof of (i).
            - Key “procedure” point:
                - Find which open set contains $a$.
                - Use its $\epsilon$-ball.
                - Inherit containment because $O_{\lambda'}\subseteq \bigcup O_\lambda$.
        2. For (ii), let $\{ O_{1}, O_{2}, \dots, O_{N} \}$ be a finite collection of open sets. Now, if $a \in \bigcap_{k=1}^N O_{k}$, then $a$ is an element of each of the open sets. By the definition of an open set, we know that, for each $1 \leq k \leq N$, there exists $v_{\epsilon_{k}}(a) \subseteq O_{k}$. We are in search of a sing $\epsilon$-neighborhood of $a$ that is contained in every $O_{k}$, so the trick is to take the smallest one. Letting $\epsilon = \min \{ \epsilon_{1},\ \epsilon_{2},\dots,\epsilon_{N} \}$, it follows that $V_{\epsilon}(a) \subseteq V_{\epsilon_{k}}(a)$ for all $k$, and hence $V_{\epsilon}(a) \subseteq \bigcap_{k=1}^N O_{k}$, as desired. $\square$
            - Where “finite” matters:
                - You can take $\min\{\epsilon_1,\dots,\epsilon_N\}$ only for finitely many numbers.

- **Definition 3.3.1 (Compactness).** (pg. 96)
    - A set $K \subseteq \mathbb{R}$ is _compact_ if every sequence in $K$ has a subsequence that converges to a limit that is also in $K$.
        - Professor-style contrast:
            - BW: bounded sequence ⇒ some convergent subsequence (limit may be outside the original set).
            - Compactness: subsequence converges and the limit stays in the set.

## Pri Fixe List Problems and Solutions

- **2.2.3.** (pg. 47) Describe what we would have to demonstrate in order to disprove each of the following statements.
    - (a) At every college in the United States, there is a student who is at least seven feet tall.
        - Disproof target (negation of the statement):
            - Exhibit one specific college $C$ such that **no** student at $C$ is at least seven feet tall.
                - Formally: $\exists C\ \forall s\in C,\ \text{height}(s) < 7$ ft.
    - (b) For all colleges in the United States, there exists a professor who gives every student a grade of either A or B.
        - Disproof target (negation of the statement):
            - Exhibit one specific college $C$ such that **every** professor fails the property.
                - Formally: $\exists C\ \forall p\in C\ \exists s\in C,\ \text{grade}(p,s)\notin\{A,B\}$.
    - (c) There exists a college in the United States where every student is at least six feet tall.
        - Disproof target (negation of the statement):
            - Show that at **every** college there is **some** student under six feet tall.
                - Formally: $\forall C\ \exists s\in C,\ \text{height}(s) < 6$ ft.

- **2.2.4.** (pg. 48) Give an example of each or state that the request is impossible. For any that are impossible, give a compelling argument for why that is the case.
    - (a) A sequence with an infinite number of ones that does not converge to one.
        - Example:
            - $a_n=\begin{cases}1,&n\text{ even}\\0,&n\text{ odd}\end{cases}$
                - Has infinitely many ones.
                - Does not converge (oscillates between 1 and 0).
    - (b) A sequence with an infinite number of ones that converges to a limit not equal to one.
        - Impossible.
            - Suppose $a_n\to L$ with $L\neq 1$.
            - Choose $\epsilon=\dfrac{|L-1|}{2}>0$.
            - Then $\exists N$ such that $n\ge N\Rightarrow |a_n-L|<\epsilon$.
            - But if $a_n=1$ then $|a_n-L|=|1-L|=2\epsilon$, impossible for $n\ge N$.
            - So only finitely many ones can occur, contradicting “infinitely many ones.”
    - (c) A divergent sequence such that for every $n \in \mathbb{N}$ it is possible to find $n$ consecutive ones somewhere in the sequence.
        - Example (blocks of ones of increasing length separated by zeros):
            - $1,\ 0,\ 1,1,\ 0,\ 1,1,1,\ 0,\ 1,1,1,1,\ 0,\dots$
                - For every $n$, a block of $n$ consecutive ones appears.
                - Diverges because infinitely many zeros occur, so it cannot converge to 1, and infinitely many ones occur, so it cannot converge to 0.

- **2.3.1.** (pg. 54) Let $x_{n} \geq 0$ for all $n \in \mathbb{N}$.
    - (a) If $(x_{n}) \to 0$, show that $(\sqrt{ x_{n} }) \to 0$.
        1. Start with the definition target.
            - Given $\epsilon>0$, want $\exists N$ s.t. $n\ge N\Rightarrow |\sqrt{x_n}-0|<\epsilon$.
        2. Convert the inequality to one about $x_n$.
            - $|\sqrt{x_n}|<\epsilon \iff \sqrt{x_n}<\epsilon \iff x_n<\epsilon^2$ (using $x_n\ge 0$).
        3. Use $x_n\to 0$ with $\epsilon^2$.
            - Since $x_n\to 0$, $\exists N$ s.t. $n\ge N\Rightarrow |x_n-0|<\epsilon^2$, i.e. $x_n<\epsilon^2$.
        4. Conclude $\sqrt{x_n}\to 0$.
    - (b) If $(x_{n}) \to x$, show that $(\sqrt{ x_{n} }) \to \sqrt{ x }$.
        1. Use the “multiply by the conjugate” identity (algebra, no calculus).
            - For $x_n,x\ge 0$:
                - $|\sqrt{x_n}-\sqrt{x}|=\dfrac{|x_n-x|}{\sqrt{x_n}+\sqrt{x}}$.
        2. Split into cases.
            - If $x=0$, then $x_n\to 0$ and part (a) gives $\sqrt{x_n}\to 0=\sqrt{x}$.
            - If $x>0$, force the denominator away from 0.
        3. Denominator away from 0 (professor-style “keep it safe”).
            - Take $\epsilon_0=\dfrac{x}{2}>0$.
            - Then $\exists N_0$ such that $n\ge N_0\Rightarrow |x_n-x|<x/2$, hence $x_n>x/2$.
            - So for $n\ge N_0$, $\sqrt{x_n}+\sqrt{x}\ge \sqrt{x/2}$.
        4. Finish with an $\epsilon$-bound.
            - For $n\ge N_0$:
                - $|\sqrt{x_n}-\sqrt{x}|\le \dfrac{|x_n-x|}{\sqrt{x/2}}$.
            - Since $|x_n-x|\to 0$, the RHS $\to 0$, so $\sqrt{x_n}\to \sqrt{x}$.

- **2.3.2.** (pg. 54) Using only Definition 2.2.3, prove that if $(x_{n}) \to 2$, then
    - (a) $\left( \dfrac{2x_{n} - 1}{3} \right) \to 1$;
        1. Compute the difference you must make $<\epsilon$.
            - $\left|\dfrac{2x_n-1}{3}-1\right| =\left|\dfrac{2x_n-4}{3}\right| =\dfrac{2}{3}|x_n-2|$.
        2. Use the definition of $x_n\to 2$ with a tuned epsilon.
            - Given $\epsilon>0$, choose $N$ such that $n\ge N\Rightarrow |x_n-2|<\dfrac{3}{2}\epsilon$.
        3. Conclude.
            - Then for $n\ge N$, $\left|\dfrac{2x_n-1}{3}-1\right|<\epsilon$.
    - (b) $(1 /x_{n}) \to 1 /2$.
        1. First force $x_n$ away from 0 (the book often forgets to say this; your prof emphasized it).
            - Since $x_n\to 2$, choose $\epsilon=1$.
            - Then $\exists N_0$ such that $n\ge N_0\Rightarrow |x_n-2|<1$, hence $x_n>1$.
        2. Now bound the difference.
            - For $n\ge N_0$:
                - $\left|\dfrac{1}{x_n}-\dfrac{1}{2}\right| =\dfrac{|2-x_n|}{2|x_n|} \le \dfrac{|x_n-2|}{2}$ (since $|x_n|\ge 1$).
        3. Use Definition 2.2.3 again.
            - Given $\epsilon>0$, choose $N_1$ such that $n\ge N_1\Rightarrow |x_n-2|<2\epsilon$.
            - For $n\ge \max(N_0,N_1)$, the difference is $<\epsilon$.

- **2.3.7.** (pg. 54/55) Give an example of each of the following, or state that such a request is impossible by referencing the proper theorem(s):
    - (a) sequences $(x_{n})$ and $(y_{n})$, which both diverge, but whose sum $(x_{n} + y_{n})$ converges;
        - Example:
            - $x_n=n$ and $y_n=-n+\dfrac{1}{n}$.
                - Both diverge.
                - $x_n+y_n=\dfrac{1}{n}\to 0$ converges.
    - (b) sequences $(x_{n})$ and $(y_{n})$, where $(x_{n})$ converges, $(y_{n})$ diverges, and $(x_{n} + y_{n})$ converges;
        - Impossible.
            - If $x_n\to x$ and $x_n+y_n\to L$, then
                - $y_n=(x_n+y_n)-x_n\to L-x$,
                - so $y_n$ converges, contradiction.
    - (c) a convergent sequence $(b_{n})$ with $b_{n} \neq 0$ for all $n$ such that $(1 /b_{n})$ diverges;
        - Example:
            - $b_n=\dfrac{1}{n}$.
                - $b_n\to 0$ and $b_n\neq 0$ for all $n$.
                - $1/b_n=n$ diverges.
    - (d) an unbounded sequence $(a_{n})$ and a convergent sequence $(b_{n})$ with $(a_{n} - b_{n})$ bounded;
        - Impossible.
            - Convergent $(b_n)$ is bounded.
            - If $(a_n-b_n)$ is bounded, then $a_n=(a_n-b_n)+b_n$ is bounded + bounded, hence bounded.
            - Contradiction to $a_n$ unbounded.
    - (e) two sequences $(a_{n})$ and $(b_{n})$, where $(a_{n}b_{n})$ and $(a_{n})$ converge but $(b_{n})$ does not.
        - Example:
            - $a_n=0$ for all $n$ (converges).
            - $b_n=(-1)^n$ (diverges).
            - $a_nb_n=0$ (converges).

- **2.3.8.** (pg. 55) Let $(x_{n}) \to x$ and let $p(x)$ be a polynomial.
    - (a) Show $p(x_{n}) \to p(x)$.
        1. Reduce to monomials using algebraic limit theorems.
            - It suffices to show $x_n^k\to x^k$ for each $k$.
        2. Prove $x_n^k\to x^k$ by induction on $k$.
            - Base $k=0$: $x_n^0=1\to 1$.
            - Step: if $x_n^k\to x^k$, then
                - $x_n^{k+1}=x_n^k\cdot x_n\to x^k\cdot x=x^{k+1}$ by the product rule.
        3. Build the polynomial by sums and scalar multiples.
            - If $p(t)=\sum_{k=0}^m c_k t^k$, then $c_k x_n^k\to c_k x^k$.
            - Sum rule gives $p(x_n)\to p(x)$.
    - (b) Find an example of a function $f(x)$ and a convergent sequence $(x_{n}) \to x$ where the sequence $f(x_{n})$ converges, but not to $f(x)$.
        - Example:
            - $f(t)=\begin{cases}0,&t\neq 0\\1,&t=0\end{cases}$ and $x_n=\dfrac{1}{n}\to 0$.
                - $f(x_n)=0\to 0$.
                - But $f(0)=1$, so the limit is not $f(x)$.

- **2.3.10.** (pg. 55) Consider the following list of conjectures. Provide a short proof for those that are true and a counterexample for any that are false.
    - (a) If $\lim(a_{n} - b_{n}) = 0$, then $\lim a_{n} = \lim b_{n}$.
        - True (with the standard interpretation that these limits exist).
            1. Assume $\lim a_n=A$ and $\lim(a_n-b_n)=0$.
            2. Then $b_n=a_n-(a_n-b_n)\to A-0=A$ (difference of convergent sequences converges).
            3. Hence $\lim b_n=A=\lim a_n$.
    - (b) If $(b_{n}) \to b$, then $|b_{n}| \to |b|$.
        - True.
            1. Reverse triangle inequality:
                - $||b_n|-|b||\le |b_n-b|$.
            2. Since $|b_n-b|\to 0$, we get $||b_n|-|b||\to 0$, i.e. $|b_n|\to |b|$.
    - (c) If $(a_{n}) \to 0$ and $(b_{n} - a_{n}) \to 0$, then $(b_{n}) \to a$.
        - False as stated.
            - Counterexample:
                - Let $a_n\equiv 0$ and $b_n=\dfrac{1}{n}$.
                - Then $a_n\to 0$ and $b_n-a_n=b_n\to 0$.
                - But $b_n\to 0$ (so the correct conclusion is $b_n\to 0$, not “$\to a$” for an arbitrary $a$).
    - (d) If $(a_{n}) \to 0$ and $|b_{n} - b| \leq a_{n}$ for all $n \in \mathbb{N}$, then $(b_{n}) \to b$.
        - True.
            1. We have $0\le |b_n-b|\le a_n$ for all $n$.
            2. Since $a_n\to 0$, given $\epsilon>0$ choose $N$ with $n\ge N\Rightarrow a_n<\epsilon$.
            3. Then $|b_n-b|<\epsilon$ for $n\ge N$, so $b_n\to b$.

- **2.3.11 (Cesaro Means).** (pg. 55)
    - (a) Show that if $(x_{n})$ is a convergent sequence, then the sequence given by the averages $$ y_{n} = \dfrac{x_{1} + x_{2} + \cdots + x_{n}}{n} $$ also converges to the same limit.
        1. Write the difference (professor’s “split into two panels” move).
            - Let $x_n\to x$.
            - $|y_n-x|=\left|\dfrac{(x_1-x)+\cdots+(x_n-x)}{n}\right|$.
        2. Choose a tail where terms are small.
            - Given $\epsilon>0$, choose $N$ such that $k\ge N\Rightarrow |x_k-x|<\epsilon/2$.
        3. Bound the tail contribution by $\epsilon/2$.
            - For $n\ge N$:
                - $\dfrac{1}{n}\sum_{k=N}^n |x_k-x|\le \dfrac{n-N+1}{n}\cdot \dfrac{\epsilon}{2}\le \dfrac{\epsilon}{2}$.
        4. Bound the finite head by making $n$ large (early chaos gets diluted).
            - Let $M=\sum_{k=1}^{N-1}|x_k-x|$ (fixed).
            - Choose $n$ so that $M/n<\epsilon/2$.
        5. Combine:
            - For large $n$, $|y_n-x|\le M/n+\epsilon/2<\epsilon$.
    - (b) Give an example to show that it is possible for the sequence $(y_{n})$ of averages to converge even if $(x_{n})$ does not.
        - Example:
            - $x_n=(-1)^n$ diverges.
            - But the partial sums are bounded by 1 in absolute value, so
                - $|y_n|=\left|\dfrac{x_1+\cdots+x_n}{n}\right|\le \dfrac{1}{n}\to 0$.
            - Hence $y_n\to 0$ while $x_n$ diverges.

- **2.3.12.** (pg. 56) A typical task in analysis is to decipher whether a property possessed by every term in a convergent sequence is necessarily inherited by the limit. Assume $(a_{n}) \to a$, and determine the validity of each claim. Try to produce a counterexample for any that are false.
    - (a) If every $a_{n}$ is an upper bound for a set $B$, then $a$ is also an upper bound for $B$.
        - True.
            1. Suppose $a$ is not an upper bound.
                - Then $\exists b\in B$ with $b>a$.
            2. Choose $\epsilon=\dfrac{b-a}{2}>0$.
            3. Since $a_n\to a$, for large $n$ we have $|a_n-a|<\epsilon$, so $a_n<a+\epsilon=\dfrac{a+b}{2}<b$.
            4. Contradiction: $a_n$ cannot be an upper bound if $b\in B$ exceeds it.
    - (b) If every $a_{n}$ is in the complement of the interval $(0, 1)$, then $a$ is also in the complement of $(0, 1)$.
        - True.
            1. Suppose $a\in(0,1)$.
            2. Choose $\epsilon=\min\{a,1-a\}/2>0$, so $(a-\epsilon,a+\epsilon)\subset(0,1)$.
            3. For large $n$, $|a_n-a|<\epsilon$ implies $a_n\in(0,1)$.
            4. Contradiction to “each $a_n$ is in the complement of $(0,1)$.”
    - (c) If every $a_{n}$ is rational, then $a$ is rational.
        - False.
            - Counterexample:
                - Let $(a_n)$ be rational approximations converging to $\sqrt{2}$.
                - Each $a_n\in\mathbb{Q}$ but $a=\sqrt{2}\notin\mathbb{Q}$.

- **2.4.1.** (pg. 59/60)
    - **(a)** Prove that the sequence defined by $x_{1} = 3$ and $$ x_{n+1} = \frac{1}{4 - x_{n}} $$ converges.
        1. **Show the recursion is well-defined and the tail is bounded: $0<x_n\le 1$ for all $n\ge 2$.**
            - Basis: $x_2=1$, so $0<x_2\le 1$.
            - Inductive step: assume $0<x_n\le 1$.
                - Then $4-x_n\ge 3>0$, so $x_{n+1}=\dfrac{1}{4-x_n}>0$.
                - Also $x_{n+1}=\dfrac{1}{4-x_n}\le \dfrac{1}{3}\le 1$.
            - Conclusion: for all $n\ge 2$, $x_n\in(0,1]$ (bounded below by $0$ and above by $1$).
        2. **Show $(x_n)_{n\ge 2}$ is decreasing (the “crux” your professor emphasized).**
            - Define $f(t)=\dfrac{1}{4-t}$ on $(-\infty,4)$.
            - **Claim:** $f$ is increasing on $(-\infty,4)$.
                - If $u<v<4$, then $4-u>4-v>0$, so $\dfrac{1}{4-u}<\dfrac{1}{4-v}$, hence $f(u)<f(v)$.
            - Base step: $x_2=1$ and $x_3=\dfrac{1}{4-1}=\dfrac{1}{3}$, so $x_2\ge x_3$.
            - Inductive step: assume $x_n\ge x_{n+1}$ (I.H.).
                - Then since $f$ is increasing and $x_n,x_{n+1}<4$,
                    - $x_{n+1}=f(x_n)\ge f(x_{n+1})=x_{n+2}$.
            - Conclusion: $x_n$ is decreasing for $n\ge 2$.
        3. **Apply MCT (monotone + bounded).**
            - For $n\ge 2$, $(x_n)$ is decreasing and bounded below by $0$.
            - Hence $(x_n)$ converges.
    - **(b)** Now that we know $\lim x_{n}$ exists, explain why $\lim x_{n+1}$ must also exist and equal the same value.
        1. **Shift doesn’t change the limiting behavior.**
            - If $x_n\to L$, then for any $\epsilon>0$, $\exists N$ such that $n\ge N\Rightarrow |x_n-L|<\epsilon$.
            - Then for $n\ge N$, also $|x_{n+1}-L|<\epsilon$.
        2. **Conclusion:** $\lim x_{n+1}=L=\lim x_n$.
    - **(c)** Take the limit of each side of the recursive equation in part (a) to explicitly compute $\lim x_{n}$.
        1. **Take limits on both sides (allowed because the limit exists).**
            - Let $L=\lim x_n=\lim x_{n+1}$.
            - Then $L=\lim \dfrac{1}{4-x_n}=\dfrac{1}{4-L}$.
        2. **Solve:**
            - $L(4-L)=1\Rightarrow L^2-4L+1=0\Rightarrow L=2\pm\sqrt{3}$.
        3. **Use bounds to choose the root.**
            - Since $0<L\le 1$, we must have $L=2-\sqrt{3}$.

- **2.4.2.** (pg. 60)
    - (a) Consider the recursively defined sequence $y_{1} = 1$, $$ y_{n+1} = 3 - y_{n}, $$ and set $y = \lim y_{n}$. Because $(y_{n})$ and $(y_{n+1})$ have the same limit, taking the limit across the recursive equation gives $y = 3 - y$. Solving for $y$, we conclude $\lim y_{n} = 3 /2$.
        - What is wrong with this argument?
            1. The argument assumes $\lim y_n$ exists before proving it.
            2. Compute terms:
                - $y_1=1,\ y_2=2,\ y_3=1,\ y_4=2,\dots$
            3. The sequence oscillates and does not converge.
            4. So “take limits on both sides” is not permitted here.
    - (b) This time set $y_{1} = 1$ and $y_{n+1} = 3 - \dfrac{1}{y_{n}}$. Can the strategy in (a) be applied to compute the limit of this sequence?
        1. Not until you prove the limit exists.
            - The “take limits” move is only legal after establishing convergence.
        2. If you do prove $y_n\to y$, then you may solve the fixed-point equation:
            - $y=3-\dfrac{1}{y}\Rightarrow y^2-3y+1=0\Rightarrow y=\dfrac{3\pm\sqrt{5}}{2}$.
        3. The correct root must be chosen using bounds/behavior of the actual sequence.

- **2.4.3.** (pg. 60)
    - (a) Show that $$ \sqrt{ 2 },\ \sqrt{ 2 + \sqrt{ 2 } },\ \sqrt{ 2 + \sqrt{ 2 + \sqrt{ 2 } } },\dots $$ converges and find the limit.
        1. Write the recursion.
            - $a_1=\sqrt{2}$, $a_{n+1}=\sqrt{2+a_n}$.
        2. Show bounded above by 2 (induction).
            - Basis: $a_1\le 2$.
            - If $a_n\le 2$, then $a_{n+1}=\sqrt{2+a_n}\le \sqrt{4}=2$.
        3. Show increasing.
            - For $a_n\in[0,2]$:
                - $a_{n+1}\ge a_n \iff \sqrt{2+a_n}\ge a_n \iff 2+a_n\ge a_n^2$
                - $\iff a_n^2-a_n-2\le 0 \iff (a_n-2)(a_n+1)\le 0$ (true on $[-1,2]$).
        4. Apply MCT.
            - Increasing + bounded above ⇒ convergent.
        5. Take limits to find $L$.
            - $L=\sqrt{2+L}\Rightarrow L^2-L-2=0\Rightarrow L=2$ (positive).
    - (b) Does the sequence $$ \sqrt{ 2 },\ \sqrt{ 2 \sqrt{ 2 } },\ \sqrt{ 2 \sqrt{ 2 \sqrt{ 2 } } },\dots $$ converge? If so, find the limit.
        1. Write the recursion.
            - $b_1=\sqrt{2}$, $b_{n+1}=\sqrt{2b_n}$.
        2. Convert to exponents.
            - Write $b_n=2^{c_n}$.
            - Then $2^{c_{n+1}}=\sqrt{2\cdot 2^{c_n}}=2^{(1+c_n)/2}$, so $c_{n+1}=\dfrac{1+c_n}{2}$.
        3. Show $c_n\to 1$.
            - $c_{n+1}-1=\dfrac{c_n-1}{2}\Rightarrow c_n\to 1$.
        4. Conclude $b_n=2^{c_n}\to 2$.

- **2.4.5 (Calculating Square Roots).** (pg. 60/61) Let $x_{1} = 2$, and define $$ x_{n+1} = \frac{1}{2} \left( x_{n} + \frac{2}{x_{n}} \right).  $$
    - (a) Show that $x_{n}^2$ is always greater than or equal to 2, and then use this to prove that $x_{n} - x_{n+1} \geq 0$. Conclude that $\lim x_{n} = \sqrt{ 2 }$.
        1. Show $x_n>0$ for all $n$.
            - $x_1=2>0$.
            - If $x_n>0$, then $x_{n+1}=\dfrac12\left(x_n+\dfrac{2}{x_n}\right)>0$.
        2. Prove $x_{n+1}^2\ge 2$ (hence $x_n^2\ge 2$ for all $n$).
            - Compute:
                - $x_{n+1}^2=\dfrac14\left(x_n+\dfrac{2}{x_n}\right)^2 =\dfrac14\left(x_n^2+4+\dfrac{4}{x_n^2}\right)$.
            - Then
                - $x_{n+1}^2-2=\left(\dfrac{x_n^2}{4}+\dfrac{1}{x_n^2}-1\right)$.
            - Use AM–GM:
                - $\dfrac{x_n^2}{4}+\dfrac{1}{x_n^2}\ge 2\sqrt{\dfrac{x_n^2}{4}\cdot\dfrac{1}{x_n^2}}=1$.
            - So $x_{n+1}^2-2\ge 0$, i.e. $x_{n+1}^2\ge 2$.
        3. Use $x_n^2\ge 2$ to prove $x_n-x_{n+1}\ge 0$ (decreasing).
            - $x_{n+1}-x_n=\dfrac12\left(\dfrac{2}{x_n}-x_n\right)$.
            - If $x_n^2\ge 2$, then $\dfrac{2}{x_n}\le x_n$, so $x_{n+1}\le x_n$.
        4. Conclude convergence and compute the limit.
            - $(x_n)$ is decreasing and bounded below by $\sqrt{2}$ (since $x_n>0$ and $x_n^2\ge 2$).
            - By MCT, $x_n\to L$.
            - Take limits:
                - $L=\dfrac12\left(L+\dfrac{2}{L}\right)\Rightarrow L^2=2\Rightarrow L=\sqrt2$.
    - (b) Modify the sequence $(x_{n})$ so that it converges to $\sqrt{ c }$.
        1. Define (for $c>0$):
            - $x_{n+1}=\dfrac12\left(x_n+\dfrac{c}{x_n}\right)$ with $x_1>0$.
        2. Same argument gives $x_n\to \sqrt{c}$ via the fixed point:
            - $L=\dfrac12\left(L+\dfrac{c}{L}\right)\Rightarrow L^2=c$.

- **2.4.6 (Arithmetic-Geometric Mean).** (pg. 61)
    - (a) Explain why $\sqrt{ xy } \leq (x+y) /2$ for any two positive real numbers $x$ and $y$. (The geometric mean is always less than the arithmetic mean.)
        1. Use a square is nonnegative.
            - $(\sqrt{x}-\sqrt{y})^2\ge 0$.
        2. Expand:
            - $x+y-2\sqrt{xy}\ge 0\Rightarrow 2\sqrt{xy}\le x+y\Rightarrow \sqrt{xy}\le \dfrac{x+y}{2}$.
    - (b) Now let $0 \leq x_{1} \leq y_{1}$ and define $$ x_{n+1} = \sqrt{ x_{n}y_{n} } \quad\text{and}\quad y_{n+1} = \dfrac{x_{n} + y_{n}}{2}. $$
        - Show $\lim x_{n}$ and $\lim y_{n}$ both exist are equal.
            1. Preserve the order $x_n\le y_n$.
                - From (a): $x_{n+1}=\sqrt{x_ny_n}\le \dfrac{x_n+y_n}{2}=y_{n+1}$.
            2. Show monotonicity.
                - $x_{n+1}=\sqrt{x_ny_n}\ge \sqrt{x_nx_n}=x_n$ so $(x_n)$ is increasing.
                - $y_{n+1}=\dfrac{x_n+y_n}{2}\le \dfrac{y_n+y_n}{2}=y_n$ so $(y_n)$ is decreasing.
            3. Show boundedness.
                - $(x_n)$ is bounded above by $y_1$.
                - $(y_n)$ is bounded below by $x_1$.
            4. Apply MCT to each.
                - $x_n\to \ell$ and $y_n\to m$.
            5. Prove the limits are equal.
                - Take limits in the recursions:
                    - $\ell=\sqrt{\ell m}$ and $m=\dfrac{\ell+m}{2}$.
                - From $m=\dfrac{\ell+m}{2}$ we get $m=\ell$.

- **2.4.7 (Limit Superior).** (pg. 61) Let $(a_{n})$ be a bounded sequence.
    - (a) Prove that the sequence defined by $y_{n} = \operatorname{sup}\{ a_{k} : k \geq n \}$ converges.
        1. Show $(y_n)$ is decreasing.
            - The tail set $\{a_k:k\ge n+1\}\subseteq\{a_k:k\ge n\}$, so its supremum cannot exceed the previous one:
                - $y_{n+1}\le y_n$.
        2. Show $(y_n)$ is bounded below.
            - Since $(a_n)$ is bounded, all tails are bounded, so each $y_n$ is bounded below.
        3. Apply MCT.
            - Decreasing + bounded below ⇒ convergent.
    - (b) The _limit superior_ of $(a_{n})$, or $\lim \operatorname{sup}a_{n}$, is defined by $$ \lim \operatorname{sup} a_{n} = \lim y_{n}, $$ where $y_{n}$ is the sequence from part (a) of this exercise. Provide a reasonable definition for $\lim \operatorname{inf} a_{n}$ and briefly explain why it always exists for any bounded sequence.
        1. Define:
            - $z_n=\inf\{a_k:k\ge n\}$ and $\liminf a_n=\lim z_n$.
        2. Explain existence.
            - $(z_n)$ is increasing (tail infs go up as the set shrinks).
            - Bounded sequence ⇒ each $z_n$ is bounded above.
            - Increasing + bounded above ⇒ convergent by MCT.
    - (c) Prove that $\lim \operatorname{inf} a_{n} \leq \lim \operatorname{sup}a_{n}$ for every bounded sequence, and give an example of a sequence for which the inequality is strict.
        1. Termwise inequality:
            - For each $n$, $z_n\le y_n$.
        2. Take limits:
            - $\lim z_n\le \lim y_n$, i.e. $\liminf a_n\le \limsup a_n$.
        3. Strict example:
            - $a_n=(-1)^n$ gives $\liminf=-1$ and $\limsup=1$.
    - (d) Show that $\lim \operatorname{inf} a_{n} = \lim \operatorname{sup}a_{n}$ if and only if $\lim a_{n}$ exists. In this case, all three share the same value.
        1. If $a_n\to L$, then tails lie in $(L-\epsilon,L+\epsilon)$ eventually.
            - Hence $z_n\to L$ and $y_n\to L$.
        2. If $z_n\to L$ and $y_n\to L$, then squeeze $a_n$ between them.
            - For each $n$, $z_n\le a_n\le y_n$.
            - For large $n$, both $z_n$ and $y_n$ are within $\epsilon$ of $L$, forcing $|a_n-L|<\epsilon$.

- **2.5.1.** (pg. 65) Give an example of each of the following, or argue that such a request is impossible.
    - (a) A sequence that has a subsequence that is bounded but contains no subsequence that converges.
        - Impossible.
            1. If a subsequence is bounded, Bolzano–Weierstrass gives a convergent sub-subsequence.
            2. A sub-subsequence is still a subsequence of the original sequence.
            3. So the original must contain a convergent subsequence, contradiction.
    - (b) A sequence that does not contain $0$ or $1$ as a term but contains subsequences converging to each of these values.
        - Example:
            - $a_{2n}=\dfrac{1}{n}$ and $a_{2n-1}=1-\dfrac{1}{n}$.
                - No term equals 0 or 1.
                - Even subsequence $\to 0$, odd subsequence $\to 1$.
    - (c) A sequence that contains subsequences converging to every point in the infinite set $\left\{  1,\ 1/2,\ 1/3,\ 1/4, 1/5, \dots \right\}$.
        - Example (each value appears infinitely often):
            - List the values in a triangular repetition:
                - $1;\ 1,\tfrac12;\ 1,\tfrac12,\tfrac13;\ 1,\tfrac12,\tfrac13,\tfrac14;\ \dots$
            - For each $k$, the value $1/k$ appears infinitely many times, so the constant subsequence $1/k,1/k,1/k,\dots$ converges to $1/k$.
    - (d) A sequence that contains subsequences converging to every point in the infinite set $\left\{  1,\ 1/2,\ 1/3,\ 1/4, 1/5, \dots \right\}$, and no subsequences converging to points outside of this set.
        - Impossible (this is the “hidden 0” trap).
            1. If for each $k$ there is a subsequence converging to $1/k$, then in particular there are terms of the sequence arbitrarily close to $1/k$ for each $k$.
            2. Choose indices $n_k$ such that $|a_{n_k}-1/k|<1/k$ (possible from the definition of subsequence convergence).
            3. Then $|a_{n_k}|\le |a_{n_k}-1/k|+|1/k|<1/k+1/k=2/k\to 0$.
            4. So $(a_{n_k})\to 0$, meaning 0 is a subsequential limit.
            5. But $0\notin\{1,1/2,1/3,\dots\}$, contradicting “no subsequences converge outside that set.”

- **2.5.2.** (65) Decide whether the following propositions are true or false, providing a short justification for each conclusion.
    - (a) If every proper subsequence of $(x_{n})$ converges, then $(x_{n})$ converges as well.
        - True.
            1. Suppose $(x_n)$ does not converge.
            2. Then there exist $\epsilon>0$ and indices $n_1<n_2<\cdots$ such that $|x_{n_{k+1}}-x_{n_k}|\ge \epsilon$ for all $k$.
                - (Construction idea: because not convergent, the sequence cannot eventually fit inside any single $\epsilon$-ball; pick $n_1$, then pick $n_2$ outside $V_\epsilon(x_{n_1})$, etc.)
            3. Then $(x_{n_k})$ is a proper subsequence that is not Cauchy, hence cannot converge.
            4. Contradiction.
    - (b) If $(x_{n})$ contains a divergent subsequence, then $(x_{n})$ diverges.
        - True.
            - If $x_n$ converged, then every subsequence would converge to the same limit.
    - (c) If $(x_{n})$ is bounded and diverges, then there exists two subsequences of $(x_{n})$ that converge to different limits.
        - True.
            1. Bounded ⇒ by BW, there exists at least one convergent subsequence.
            2. If every convergent subsequence had the same limit $L$, then $(x_n)$ would converge to $L$.
                - (Subsequence criterion: if a sequence is bounded and has a unique subsequential limit, then it converges.)
            3. Since $(x_n)$ diverges, it cannot have a unique subsequential limit.
            4. Hence there must be two subsequences converging to different limits.
    - (d) If $(x_{n})$ is monotone and contains a convergent subsequence, then $(x_{n})$ converges.
        - True.
            1. A monotone sequence either converges (finite limit) or diverges to $\pm\infty$.
            2. A convergent subsequence rules out divergence to $\pm\infty$.
            3. Therefore the whole monotone sequence converges.

- **2.6.2.** (70) Give an example of each of the following, or argue that such a request is impossible.
    - (a) A Cauchy sequence that is not monotone.
        - Example:
            - $a_n=\dfrac{(-1)^n}{n}$.
                - Convergent ⇒ Cauchy.
                - Not monotone due to sign oscillation.
    - (b) A Cauchy sequence with an unbounded subsequence.
        - Impossible.
            - Cauchy ⇒ bounded, hence every subsequence is bounded.
    - (c) A divergent monotone sequence with a Cauchy subsequence.
        - Impossible.
            1. A Cauchy subsequence converges.
            2. A monotone sequence with a convergent subsequence must converge.
            3. Contradiction to “divergent monotone.”
    - (d) An unbounded sequence containing a subsequence that is Cauchy.
        - Example:
            - $a_n=\begin{cases}n,&n\text{ odd}\\0,&n\text{ even}\end{cases}$.
                - Unbounded due to odd terms.
                - Even subsequence is constant 0 ⇒ Cauchy.

- **2.6.4.** (pg. 70) Let $(a_{n})$ and $(b_{n})$ be Cauchy sequences. Decide whether each of the following sequences is a Cauchy sequence, justifying each conclusion.
    - (a) $c_{n} = \lvert a_{n} - b_{n} \rvert$
        1. Use reverse triangle inequality:
            - $||u|-|v||\le |u-v|$ with $u=a_n-b_n$, $v=a_m-b_m$.
        2. Then:
            - $||a_n-b_n|-|a_m-b_m||\le |(a_n-a_m)-(b_n-b_m)|\le |a_n-a_m|+|b_n-b_m|$.
        3. Since $(a_n)$ and $(b_n)$ are Cauchy, choose $N_1,N_2$ with each term $<\epsilon/2$ for $n,m\ge N$.
        4. Conclude $|c_n-c_m|<\epsilon$ for large $n,m$.
    - (b) $c_{n} = (-1)^n a_{n}$
        - Not necessarily Cauchy.
            - Counterexample:
                - $a_n\equiv 1$ is Cauchy.
                - Then $c_n=(-1)^n$ is not Cauchy.
    - (c) $c_{n} = [[a_{n}]]$, where $[[x]]$ refers to the greatest integer less than or equal to $x$.
        - True: $(c_n)$ is Cauchy.
            1. Since $(a_n)$ is Cauchy in $\mathbb{R}$, it converges: $a_n\to a$.
            2. Case 1: $a\notin\mathbb{Z}$.
                - Choose $\delta>0$ so $(a-\delta,a+\delta)\subset(k,k+1)$ for some integer $k$.
                - Then for large $n$, $a_n\in(k,k+1)$, so $[[a_n]]=k$ eventually (hence Cauchy).
            3. Case 2: $a\in\mathbb{Z}$.
                - Choose $\delta=\tfrac12$ so for large $n$, $a_n\in(a-\tfrac12,a+\tfrac12)$.
                - Then $[[a_n]]$ is either $a-1$ or $a$.
                - If it switched between these infinitely often, then there would be infinitely many $n,m$ with $|a_n-a_m|\ge 1$, contradicting Cauchy.
                - Hence $[[a_n]]$ is eventually constant, so Cauchy.

- **3.2.1.** (pg. 93)
    - (a) Where in the proof of Theorem 3.2.3 part (ii) does the assumption that the collection of open sets be _finite_ get used?
        - It is used when choosing $\epsilon=\min\{\epsilon_1,\dots,\epsilon_N\}$.
            - A minimum of finitely many positive numbers exists.
            - For infinitely many, you may only have an infimum, which can be 0.
    - (b) Give an example of a countable collection of open sets $\{ O_{1},\ O_{2},\ O_{3},\dots \}$ whose intersection $\bigcap_{n=1}^\infty O_{n}$ is closed, not empty and not all of $\mathbb{R}$.
        - Example:
            - $O_n=\left(-\dfrac{1}{n},\,1+\dfrac{1}{n}\right)$.
                - Each $O_n$ is open.
                - $\bigcap_{n=1}^\infty O_n=[0,1]$ (closed, nonempty, proper subset of $\mathbb{R}$).

- **3.2.2.** (pg. 93) Let $$
    A = \left\{ (-1)^n + \frac{2}{n}: n = 1, 2, 3,\dots \right\} \quad\text{and}\quad B = \left\{ x \in \mathbb{Q} : 0 < x < 1 \right\}. 
    $$  Answer the following questions for each set:
    - (a) What are the limit points?
        - For $A$:
            - Even $n$: $(-1)^{2n}+\dfrac{2}{2n}=1+\dfrac{1}{n}\to 1$.
            - Odd $n$: $(-1)^{2n-1}+\dfrac{2}{2n-1}=-1+\dfrac{2}{2n-1}\to -1$.
            - Limit points: $\{-1,1\}$.
        - For $B$:
            - Every point in $[0,1]$ is a limit point (density of $\mathbb{Q}$).
    - (b) Is the set open? Closed?
        - For $A$:
            - Not open (no interval around a point stays inside a discrete set).
            - Not closed (does not contain its limit points $\pm 1$).
        - For $B$:
            - Not open (any neighborhood contains irrationals).
            - Not closed (every point of $[0,1]$ is a limit point, but $B$ misses irrationals and endpoints).
    - (c) Does the set contain any isolated points?
        - For $A$:
            - Yes: each point of $A$ is isolated.
        - For $B$:
            - No isolated points (between rationals there are rationals).
    - (d) Find the closure of the set.
        - For $A$:
            - $\overline{A}=A\cup\{-1,1\}$.
        - For $B$:
            - $\overline{B}=[0,1]$.

- **3.2.3.** (pg. 93) Decide whether the following sets are open, closed, or neither. If a set is not open, find a point in the set for which there is no $\epsilon$-neighborhood contained in the set. If a set is not closed, find a limit point that is not contained in the set.
    - (a) $\mathbb{Q}$.
        - Neither open nor closed.
            - Not open: any $\epsilon$-neighborhood contains irrationals.
            - Not closed: any irrational is a limit point not contained.
    - (b) $\mathbb{N}$.
        - Closed, not open.
            - Not open: any neighborhood of $n$ contains non-integers.
            - Closed: $\mathbb{N}$ has no limit points in $\mathbb{R}$ (any convergent sequence of naturals is eventually constant).
    - (c) $\{ x \in \mathbb{R} : x \neq 0 \}$.
        - Open, not closed.
            - Open: for $x\neq 0$, choose $\epsilon=|x|/2$.
            - Not closed: 0 is a limit point not included.
    - (d) $\{ 1 + 1 /4 + 1 /9 + \cdots + 1 / n^2 : n \in \mathbb{N} \}$.
        - Neither open nor closed.
            - Not open: it is a discrete set of points.
            - Not closed: the sequence of its elements converges to $\sum_{k=1}^\infty \dfrac{1}{k^2}$, a limit point not contained in the set.
    - (e) $\{ 1 + 1 /2 + 1 /3 + \cdots + 1 /n : n \in \mathbb{N} \}$.
        - Closed, not open.
            - Not open: discrete set.
            - Closed:
                - The terms are strictly increasing and unbounded (harmonic partial sums).
                - Any convergent sequence chosen from this set must eventually be constant (otherwise it would have to follow indices $n\to\infty$, forcing divergence).
                - Therefore it contains all its (real) limit points (there are none besides constant stabilization).

- **3.2.6.** (pg. 94) Decide whether the following statements are true or false. Provide counterexamples for those that are false, and supply proofs for those that are true.
    - (a) An open set that contains every rational number must necessarily be all of $\mathbb{R}$.
        - False.
            - Counterexample:
                - $O=\mathbb{R}\setminus\{\sqrt{2}\}$ is open and contains every rational, but $O\neq\mathbb{R}$.
            - **N.B.**: Why $O$ is open (professor-style):
                - If $x\in O$ and $x\neq \sqrt{2}$, let $\epsilon=\dfrac{|x-\sqrt{2}|}{2}$.
                - Then $V_\epsilon(x)$ cannot reach $\sqrt{2}$, so $V_\epsilon(x)\subseteq O$.
    - (b) The Nested Interval Property remains true if the term “closed interval” is replaced by “closed set.”
        - False.
            - Counterexample:
                - $F_n=\left(-\infty,-n\right]\cup\left[n,\infty\right)$ is closed and nested decreasing.
                - $\bigcap_{n=1}^\infty F_n=\emptyset$.
    - (c) Every nonempty open set contains a rational number.
        - True.
            - Any nonempty open set contains some interval $(a-\epsilon,a+\epsilon)$.
            - Density of $\mathbb{Q}$ gives a rational in that interval.
    - (d) Every bounded infinite closed set contains a rational number.
        - False.
            - Counterexample (bounded, infinite, closed, no rationals):
                - Let $F=\left\{\sqrt{2}+\dfrac{1}{n}:n\in\mathbb{N}\right\}\cup\{\sqrt{2}\}$.
                    - Infinite and bounded.
                    - Closed because it contains its limit point $\sqrt{2}$.
                    - Contains no rationals because $\sqrt{2}+\dfrac{1}{n}$ is irrational for all $n$.
    - (e) The Cantor set is closed.
        - True.
            - The complement of the Cantor set is a union of open middle-third intervals, hence open.
            - Therefore the Cantor set is closed.

- **3.3.1.** (pg. 99) Show that if $K$ is compact and nonempty, then $\operatorname{sup}K$ and $\operatorname{inf} K$ both exist and are elements of $K$.
    1. Existence in $\mathbb{R}$.
        - Compact $K$ is bounded, so $\sup K$ and $\inf K$ exist.
    2. Show $\sup K\in K$ by constructing a “sup-approaching” sequence.
        - Let $s=\sup K$.
        - For each $n$, choose $x_n\in K$ such that $s-\dfrac{1}{n}<x_n\le s$ (property of supremum).
    3. Use compactness to get a convergent subsequence with limit in $K$.
        - There exists $x_{n_k}\to x$ with $x\in K$.
    4. Identify the limit as $s$.
        - From $x_{n_k}\le s$, get $x\le s$.
        - From $x_{n_k}>s-\dfrac{1}{n_k}$ and $s-\dfrac{1}{n_k}\to s$, get $x\ge s$.
        - So $x=s\in K$.
    5. Same argument for $\inf K$.

- **3.3.2.** (pg. 99) Decide which of the following sets are compact. For those that are not compact, show how Definition 3.3.1 breaks down. In other words, give an example of a sequence contained in the given set that does not possess a subsequence converging to a limit in the set.
    - (a) $\mathbb{N}$.
        - Not compact.
            - Sequence $x_n=n$ is in $\mathbb{N}$ and has no convergent subsequence in $\mathbb{R}$.
    - (b) $\mathbb{Q} \cap [0, 1]$.
        - Not compact.
            - Choose rationals $q_n\to \sqrt{2}/2\in[0,1]$.
            - Then $(q_n)$ has subsequences converging to $\sqrt{2}/2$, but $\sqrt{2}/2\notin\mathbb{Q}\cap[0,1]$.
    - (c) The Cantor set.
        - Compact.
            - It is closed and bounded in $\mathbb{R}$, hence compact.
    - (d) $\{ 1 + 1 /2^2 + 1 /3^2 + \cdots + 1 /n^2 : n \in N \}$.
        - Not compact.
            - Let $s_n=1+\dfrac{1}{2^2}+\cdots+\dfrac{1}{n^2}$ (each $s_n$ is in the set).
            - Then $s_n\to \sum_{k=1}^\infty \dfrac{1}{k^2}$, which is not in the set.
            - So the sequence has no subsequence converging to a limit in the set.
    - (e) $\{ 1,\ 1/2,\ 2/3,\ 3/4,\ 4/5,\dots \}$.
        - Compact.
            - It is bounded (contained in $[1/2,1]$).
            - Its only limit point is 1, and $1$ is included.
            - Therefore it is closed and bounded, hence compact.

- **3.3.12.** (pg. 101) Using the concept of open covers (and explicitly avoiding the Bolzano-Weierstrass Theorem), prove that every bounded infinite set has a limit point.
    1. Assume for contradiction that $E$ is bounded infinite and has no limit point.
        - “No limit point” means: every point of $E$ is isolated.
    2. Isolated-point neighborhoods.
        - For each $p\in E$, choose $\epsilon_p>0$ such that $V_{\epsilon_p}(p)\cap E=\{p\}$.
            - **N.B.**: “other than $p$” is the key phrase in the limit-point definition.
    3. Trap $E$ in a compact interval.
        - Since $E$ is bounded, choose $[a,b]$ with $E\subset[a,b]$.
    4. Build an open cover of $[a,b]$ (professor’s “cover + finite subcover” logic).
        - Consider the open family:
            - $\mathcal{U}=\{V_{\epsilon_p}(p):p\in E\}\ \cup\ \{\mathbb{R}\setminus E\}$.
        - This covers $[a,b]$:
            - Points in $E$ are covered by their $V_{\epsilon_p}(p)$.
            - Points not in $E$ are covered by $\mathbb{R}\setminus E$.
    5. Use compactness of $[a,b]$ (Heine–Borel) to extract a finite subcover.
        - There exist $p_1,\dots,p_m\in E$ such that
            - $[a,b]\subseteq V_{\epsilon_{p_1}}(p_1)\cup\cdots\cup V_{\epsilon_{p_m}}(p_m)\cup(\mathbb{R}\setminus E)$.
    6. Conclude $E$ must be finite.
        - Any point of $E$ cannot lie in $\mathbb{R}\setminus E$, so it must lie in one of the finitely many balls.
        - But each $V_{\epsilon_{p_i}}(p_i)$ contains exactly one point of $E$ (namely $p_i$).
        - So $E\subseteq\{p_1,\dots,p_m\}$, hence $E$ is finite.
    7. Contradiction.
        - $E$ was assumed infinite.
        - Therefore $E$ must have a limit point. $\square$