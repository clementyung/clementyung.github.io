---
title: "9) Combinatorial Set Theory"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-9
excerpt: ""
---

{% include commands.html %}

<a name="ex9.1"></a>
## Exercise 9.1.
<i>Solution.</i> Let $L$ be an infinite linear order. Let $(x_0,x_1,\dots)$  be a sequence in $L$. Define $F : [\omega]^2 \to \lbrace 0,1\rbrace$ by:

$$
\begin{align*}
F(\lbrace n,m\rbrace) =
\begin{cases}
1, &\text{if $n > m \to x_n > x_m$} \\
0, &\text{otherwise}
\end{cases}
\end{align*}
$$

By Ramsey's theorem, there exists an infinite homogeneous set $M \subseteq L$. It's easy to check that if $F$ is constantly $0$ on $M$, then $M$ has an infinite increasing sequence, and infinite decreasing otherwise. 
$\square$

<a name="ex9.2"></a>
## Exercise 9.2.
<i>Solution.</i> We may repeat the proof of Erd\"{o}s-Rado Theorem, by changing all $\aleph_0$ to $\kappa$ (and $\aleph_1$ to $\kappa^+$). Note that $\exp_n(\aleph_0) = \beth_n$. At the same time, shall rewrite Jech's proof with more clarity and details.

<b>Step 1 - Prove for base case $n = 1$:</b> Let $F : [(2^\kappa)^+]^2 \to \kappa$ be a partition, and we want to find a homogeneous $H \subseteq (2^\kappa)^+$ of size $\kappa^+$.

For each $a \in (2^\kappa)^+$, define $F : (2^\kappa)^+ - \lbrace a\rbrace \to \kappa$ by stipulating that:

$$
\begin{align*}
F_a(x) = F(\lbrace a,x\rbrace)
\end{align*}
$$

<b>Claim.</b>. There exists a set $A \subseteq (2^\kappa)^+$ such that:
<ol>
<li> $\vert A\vert  = 2^\kappa$..</li>
<li> For every $C \subseteq A$ of size $\leq\kappa$ and every $u \in (2^\kappa)^+ - C$, there exists $v \in A - C$ such that $F_v$ agrees with $F_u$ on $C$. That is, for every $x \in C$, $F_u(x) = F(\lbrace u,x\rbrace) = F(\lbrace v,x\rbrace) = F_v(x)$.</li>
</ol>

<i>Proof.</i> We construct an $\kappa^+$-sequence $A_0 \subseteq A_1 \subseteq \cdots \subseteq A_\alpha \subseteq \cdots$, $\alpha < \kappa^+$, $\vert A_\alpha\vert  = 2^\kappa$ for all $\alpha$, as follows:
<ol>
<li> $A_0 \subseteq (2^\kappa)^+$ is arbitrary with $\vert A_0\vert  = 2^\kappa$..</li>
<li> If $\alpha$ is a limit ordinal, let $A_\alpha := \bigcup_{\beta < \alpha} A_\beta$.</li>

<li> For successor case: Given $A_\alpha$, there are $\vert [A_\alpha]^{\leq\kappa}\vert  = (2^\kappa)^{\leq\kappa} = 2^\kappa$ (by Lemma 5.7 and 5.8) many subsets $C \subseteq A_\alpha$ of size $\leq\kappa$. For each such $C$, there are only at most $2^\kappa$ many $C \to \kappa$ functions, we have:<br/>
$$
\begin{align*}
\vert \lbrace F_u\restrictedto C : u \in (2^\kappa)^+ - C\rbrace\vert  \leq 2^\kappa
\end{align*}
$$

Thus, we take $B_C \subseteq (2^\kappa)^+ - C$ such that $\vert B_C\vert  \leq 2^\kappa$, and:

$$
\begin{align*}
\lbrace F_u\restrictedto C : u \in (2^\kappa)^+ - C\rbrace = \lbrace F_u\restrictedto C : u \in B_C\rbrace
\end{align*}
$$

Now let:

$$
\begin{align*}
A_{\alpha+1} := \bigcup_{\substack{C \subseteq A \\ \vert C\vert  = \kappa}} B_C \cup A_\alpha
\end{align*}
$$
</li>
</ol>
We let $A = \bigcup_{\alpha < \kappa^+} A_\alpha$, and it's easy to see that this $A$ works. 
$\blacksquare$

With this $A$, we fix some $a \in (2^\kappa)^+ - A$. We now construct a sequence $\c{x_\alpha : \alpha < \kappa^+}$ as follows:
<ol>
<li> Let $x_0$ be arbitrary..</li>
<li> Let $C := \lbrace x_\beta : \beta < \alpha\rbrace$. Then let $x_\alpha$ be some $v \in A - C$ such that $F_v\restrictedto C = F_a\restrictedto C$.</li>
</ol>
We then let $X = \lbrace x_\alpha : \alpha < \omega_1\rbrace$.

Finally, we define the function $G : X \to \kappa$ defined by:

$$
\begin{align*}
G(x) = F_a(x)
\end{align*}
$$

We see that if $\alpha < \beta$, then:

$$
\begin{align*}
F(\lbrace x_\alpha,x_\beta\rbrace) = f_{x_\beta}(x_\alpha) = F_a(x_\alpha) = G(x_\alpha)
\end{align*}
$$

Since $\ran(G) \subseteq \kappa$ but $\vert \dom(G)\vert  = \vert X\vert  = \kappa^+$, there exists $H \subseteq X$ of size $\kappa^+$ such that $G$ is constant on $H$. It follows that $F$ is constant on $[H]^2$.

<b>Step 2 - Prove the induction step:</b> Assume that we have $(\exp_{n-1}(\kappa))^+ \to (\kappa^+)^n_\kappa$, and let $F : [(\exp_n(\kappa))^+]^{n+1} \to \kappa$. For each $a \in (\exp_n(\kappa))^+$, let $F_a : [(\exp_n(\kappa))^+ - \lbrace a\rbrace]^n \to \kappa$ be defined by:

$$
\begin{align*}
F_a(x) = F(x \cup\lbrace a\rbrace)
\end{align*}
$$

As in the base case, we can produce a set $A \subseteq (\exp_n(\kappa))^+$ such that:
<ol>
<li> $\vert A\vert  = \exp_n(\kappa)$..</li>
<li> For every $C \subseteq A$ of size $\leq\exp_{n-1}(\kappa)$ and every $u \in (\exp_n(\kappa))^+$, there exists $v \in A - C$ such that $F_v\restrictedto[C]^n = F_u\restrictedto[C]^n$.</li>
</ol>
Next we choose $a \in (\exp_n(\kappa))^+ - A$, and construct $X = \lbrace x_\alpha < (\exp_{n-1}(\kappa))^+\rbrace \subseteq A$ such that for each $\alpha$, $F_{x_\alpha}\restrictedto[\lbrace x_\beta : \beta < \alpha\rbrace]^n = F_a\restrictedto[\lbrace x_\beta : \beta < \alpha\rbrace]^n$ (as in the base case).

Then we consider $G : [X]^n \to \kappa$, where:

$$
\begin{align*}
G(x) = F_a(x)
\end{align*}
$$

As before, if $\alpha_1 < \cdots < \alpha_{n+1}$, then $F(\lbrace x_{\alpha_1},\dots,x_{\alpha_{n+1}}\rbrace) = G(\lbrace x_{\alpha_1},\dots,x_{\alpha_n}\rbrace)$. By IH, there exists $H \subseteq X$ of size $\kappa^+$ such that $G\restrictedto[H]^n$ is constant. Then $F\restrictedto[H]^{n+1}$ is constant. 
$\square$

<b>Remark.</b>. This exercise generalises Erd\"{o}s-Rado Theorem, with the theorem being a special case where $\kappa = \aleph_0$.

<a name="ex9.3"></a>
## Exercise 9.3.
<a name="lem9.3.A"></a>
<b>Lemma 9.3.A.</b> Let $\kappa$ be a regular uncountable cardinal. Let $S \subseteq \kappa$ be stationary, and let $f : S \to [\kappa]^{<\omega}$ be such that $\max{f(\alpha)} < \alpha$. Then $f$ is constant on a stationary subset of $S$.

<i>Proof.</i> We mimic the proof of Fodor's Theorem. Suppose that for each $A \in [\kappa]^{<\omega}$, $\lbrace \alpha \in S : f(\alpha) = A\rbrace$ is non-stationary. Choose a closed unbounded set $C_A$ such that $f(\alpha) \neq A$ for each $\alpha \in S \cap C_A$. For each $\gamma < \kappa$, define:

$$
\begin{align*}
C_\gamma := \bigcap_{A \in [\gamma]^{<\omega}} C_A
\end{align*}
$$

Since $\vert [\gamma]^{<\omega}\vert  < \kappa$ for all $\gamma$, $C_\gamma$ remains a closed unbounded subset. Let:

$$
\begin{align*}
C := \bigtriangle_{\gamma < \kappa} C_\gamma
\end{align*}
$$

Then $S \cap C$ is stationary. If $\alpha \in S \cap C$, then $f(\alpha) \in C_\gamma$ for every $\gamma < \alpha$, i.e. $\max{f(\alpha)} \geq \alpha$. This is a contradiction. 
$\blacksquare$

<i>Solution.</i> Following the hint, we first note that if there exists a $K_\alpha$ that is infinite, then since $K_\alpha \subseteq \alpha$, $\otp(K_\alpha)$ is a countable ordinal. Thus, by taking a subset $K_\alpha' \subseteq K_\alpha$ of order-type $\omega$, we have that $K_\alpha' \cup \lbrace \alpha\rbrace$ forms a homogeneous subset of order-type $\omega + 1$. Thus, it remains to settle the case where all $K_\alpha$'s are finite.

In this case, consider the map $f : \omega_1 \to [\omega_1]^{<\omega}$ defined by:

$$
\begin{align*}
f(\alpha) := K_\alpha
\end{align*}
$$

By <a href="#lem9.3.A">Lemma 9.3.A</a>, $f$ is constant on a stationary subset $S$, say $f(\alpha) = K$ for all $\alpha \in S$. We shall show that $[S]^2 \subseteq A$.

Let $\lbrace \alpha,\beta\rbrace \subseteq S$, say $\alpha < \beta$. Then $K$ is the maximal subset of $\beta$ such that $[K \cup \lbrace \beta\rbrace]^2 \subseteq B$. If $\lbrace \alpha,\beta\rbrace \in B$, then $[(K \cup \lbrace \alpha\rbrace) \cup \lbrace \beta\rbrace]^2 \subseteq B$ (as $[K \cup \lbrace \alpha\rbrace]^2 \subseteq B$), which yields a larger $K_\beta$, a contradiction. 
$\square$

<a name="ex9.4"></a>
## Exercise 9.4.
<i>Solution.</i> The hint solves the problem. Note that if $X \subseteq \kappa$ is infinite and homogeneous, then $F(X) = 0$ or $F(X) = 1$ (WLOG assume the first). Pick any $x \in X$, and we have that $X - \lbrace x\rbrace \equiv X$, yet $F(X - \lbrace x\rbrace) = 1$ clearly, contradicting homogeneity. 
$\square$

<a name="ex9.5"></a>
## Exercise 9.5.
<i>Solution.</i> For any tree $T$ and $\alpha < \func{height}(T)$, let $T(n)$ denote the $\alpha^\text{th}$ level of $T$. For $x \in T$, also let $T_x := \lbrace y \in T : y \geq x\rbrace$. Now fix a tree $T$ of height $\omega$ with $T(n)$ finite. Observe that for each $k < \omega$, we have:

$$
\begin{align*}
\func{height}(T) = \max\lbrace \func{height}(T_x) + k : x \in T(k)\rbrace
\end{align*}
$$

For $k = 1$, since $T(k)$ is finite we have that $\func{height}(T_{x_0})$ is infinite for some $x_0 \in T(0)$. Now suppose $x_n \in T(n)$ has been chosen such that $\func{height}(T_{x_n})$ is infinite. Then similarly for $k < \omega$:

$$
\begin{align*}
\func{height}(T_{x_n}) = \max\lbrace \func{height}(T_x) + k : x \in T_{x_n}(k)\rbrace
\end{align*}
$$

So let $x_{n+1} \in T_{x_n}(0)$ such that $\func{height}(T_{x_{n+1}})$ is infinite, as $T_{x_n}(0) \subseteq T(n)$ is finite. Then $\lbrace x_n : n \in \omega\rbrace$ clearly forms a branch in $T$. 
$\square$

<a name="ex9.6"></a>
## Exercise 9.6.
<i>Solution.</i> For each $x \in T$, if $x$ is not maximal we let $\Succ(x)$ denote the set of nodes of $T$ succeeding $x$. Since $T$ is normal, there exists a one-to-one map $f_x : \Succ(x) \to \omega$.

Define a map $f : T \to \omega^{<\alpha}$ inductively as follows: Let $f(r) := \emptyset$ where $r$ is the root of $T$. If $x \in T(\beta+1)$ and $x$ is a successor of $y \in T(\beta)$, then let $f(x) := f(y)^\frown(f_y(x))$. If $\beta$ is a limit ordinal and $x \in T(\alpha)$, then let $f(x) := \bigcup_{y < x} f(y)$. Let $\bar{T} := \ran(f)$, so $(\bar{T},\sqsubseteq)$ forms a tree.

Clearly $f$ is order-preserving, so it remains show that $f$ is one-to-one. Let $x,y \in T$, and suppose $f(x) = f(y)$. Observe that, by induction, we have $\length(f(x)) = o(x)$, so we have that $o(x) = o(y)$, say $x,y \in T(\beta)$. We now induct on $\beta$ that we must have $x = y$.
<ol>
<li> If $\beta = 0$, then $x = y$ is the unique root of the tree $T$..</li>
<li> If $\beta = \gamma + 1$, then suppose $x \in \Succ(x')$ and $y \in \Succ(y')$. Then $f(x) = f(x')^\frown(f_{x'}(x))$ and $f(y) = f(y')^\frown(f_{y'}(y))$. Then this implies in particular that $f(x') = f(y')$, and by induction hypothesis we have $x' = y'$. Since $f_{x'}$ is one-to-one, we have $f_{x'}(x) = f_{x'}(y) \implies x = y$.</li>

<li> If $\beta$ is a limit ordinal, then:<br/>
$$
\begin{align*}
f(x) = f(y) \implies \lbrace f(z) : z < x\rbrace = \lbrace f(z) : z < y\rbrace
\end{align*}
$$

By induction hypothesis, this implies that $\lbrace z : z < x\rbrace = \lbrace z : z < y\rbrace$. Then by property (iv) of Definition 9.12, we have that $x = y$.</li>
</ol> 
$\square$

<a name="ex9.7"></a>
## Exercise 9.7.
<i>Solution.</i> We shall show that the $A$ in the hint is an antichain. Let $z_x,z_y \in A$ such that $x < y$. Let $x' \in B$ such that $o(x') = o(x) + 1$. Then $x' \leq y$, and $x' \neq z_x$ are both successors of of $x$. Thus $x'$ and $z_x$ are incomparable. Meanwhile, we have $z_y > y \geq x'$. Thus, if $z_y$ and $z_x$ are comparable, then so are $z_x$ and $x'$, a contradiction. 
$\square$

<a name="ex9.8"></a>
## Exercise 9.8.
<i>Solution.</i> We can define $f : T \to \R$ by:

$$
\begin{align*}
f(x) :=
\begin{cases}
0, &\text{if $x = \emptyset$} \\
1 + \sup{x} - \inf{x}, &\text{otherwise}
\end{cases}
\end{align*}
$$

Note that $f(x)$ is finite as all sequences in $T$ are bounded. If $x < y$, then there are two cases:
<ol>
<li> If $x = \emptyset$, then $f(x) = 0$ but observe that $y \neq \emptyset \implies f(y) \geq 1$..</li>
<li> If $x \neq \emptyset$, then $\inf{x} = \inf{y}$ and $\sup{x} < \sup{y}$ (as all branches in $T$ are strictly increasing), so $f(x) < f(y)$.</li>
</ol> 
$\square$

<a name="ex9.9"></a>
## Exercise 9.9.
<i>Solution.</i> <u>$\implies$:</u> Let $f : T \to \Q$ be order-preserving. Then $T = \bigcup_{q \in \Q} f_{-1}(\lbrace q\rbrace)$, in which the order-preserving property of $f$ implies that each $f_{-1}(\lbrace q\rbrace)$ is an antichain.

<u>$\impliedby$:</u> WLOG assume $A_n$ is a maximal antichain for all $n$. Let $S_n$ be the set of all pairwise compatible $\lbrace a_i : i < n\rbrace$ such that $a_i \in A_i$ for all $i < n$. For each $a = \lbrace a_i : i < n\rbrace \in S_n$, define a function $\delta_a : n - 1 \to \lbrace -1,1\rbrace$ by:

$$
\begin{align*}
\delta_a(i) :=
\begin{cases}
-1, &\text{if $a_{n-1} < a_i$} \\
1, &\text{if $a_i < a_{n-1}$}
\end{cases}
\end{align*}
$$

We now define $\pi : T \to \Q$ as follows: For each $x \in T$, suppose $x \in A_n$ for some $n$. Write $a_n := x$. Since the antichains are all maximal, there exists a unique pairwise compatible set $a := \lbrace a_i : i \leq n\rbrace$ such that $a_i \in A_i$ for all $i \leq n$. We then define:

$$
\begin{align*}
\pi(x) := \sum_{i=0}^{n-1} \frac{\delta_a(i)}{2^i}
\end{align*}
$$

Clearly $\ran(\pi) \subseteq \Q$. We shall show that $\pi$ is order-preserving. Indeed, let $x < y$ be two nodes in $T$. Suppose $x \in A_m$ and $y \in A_n$. Note that $m \neq n$ as $x$ and $y$ are compatible. We shall assume that $m > n$ - the other case is similar.

Write $a_m := x$ and let $a := \lbrace a_i : i \leq m\rbrace$ be pairwise compatible such that $a_i \in A_i$ for all $i \leq m$. Then $a_n > x$ and $a_n \in A_n$, so we must have $a_n = y$. Thus:

$$
\begin{align*}
\pi(x) &= \sum_{i=0}^{m-1} \frac{\delta_a(i)}{2^i} \\
&= \pi(y) + \sum_{i=n}^{m-1} \frac{\delta_a(i)}{2^i} \\
&= \pi(y) - \frac{1}{2^n} + \sum_{i=n+1}^{m-1} \frac{\delta_a(i)}{2^i} \\
&\leq \pi(y) + \frac{1}{2^n} + \sum_{i=n+1}^{m-1} \frac{1}{2^i} \\
&< \pi(y)
\end{align*}
$$
 
$\square$

<a name="ex9.10"></a>
## Exercise 9.10.
<i>Solution.</i> Let $f$ be as in the hint. Then $f(\alpha) \in [\alpha]^{<\omega}$, so by <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.17">Exercise 8.17</a> $f$ is constant on a stationary set $S$ (where in <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.17">Exercise 8.17</a> we let $F$ be the closed unbounded filter). We construct $Y_n$, $n \in \omega$, inductively as follows: First let $Y_0 = X_{\alpha_0}$, where $\alpha_0 := \min{S}$. Suppose $Y_n$ has been defined. Since $S$ is stationary, it is in particular unbounded so let $\alpha \in S$ be the least ordinal such that $\alpha > \sup{Y_n}$. Now let $Y_{n+1} := X_\alpha$.

We shall show that $Z := \lbrace Y_n : n \in \omega\rbrace$ is a $\Delta$-system. Let $i < j$, and suppose $Y_i = X_\alpha$ and $Y_j = X_\beta$. By construction, we have that $X_{\alpha_0} \cap \alpha_0 \subseteq \alpha$ $X_\alpha \subseteq \beta$. Thus:

$$
\begin{align*}
X_\alpha \cap X_\beta &= X_\alpha \cap X_\beta \cap X_\beta \\
&= X_\alpha \cap X_{\alpha_0} \cap \alpha_0 \\
&= (X_\alpha \cap \alpha) \cap X_{\alpha_0} \cap \alpha_0 \\
&= (X_{\alpha_0} \cap \alpha_0) \cap X_{\alpha_0} \cap \alpha_0 \\
&= X_{\alpha_0} \cap \alpha_0
\end{align*}
$$

Thus, $Z$ is a $\Delta$-system with root $X_{\alpha_0} \cap \alpha_0$. 
$\square$

<a name="ex9.11"></a>
## Exercise 9.11.
<i>Solution.</i> The proof of Lemma 9.21 can be copied directly. Note that $\vert S\vert  = 2^{<\kappa} = \kappa$ and if $f \neq g$, then $\vert A_f \cap A_g\vert  < \kappa$ (not finite, see Definition 9.20). 
$\square$

<a name="ex9.12"></a>
## Exercise 9.12.
<i>Solution.</i> We note that each $f$ is regressive on the closed unbounded set $\omega_1 - \omega$, so it takes a constant value $n_f$ on a stationary set $S_f$. Let $\G_n := \lbrace f \in \F : f$ takes constant value $n$ on $S_f\rbrace$. Then $\F = \bigcup_{n=0}^\infty \G_n$, and since $\vert \F\vert  = \aleph_2$ we must have $\vert \G_n\vert  = \aleph_2$ for some $n$. Call this set $\G$.

Let $\mathcal{S} = \lbrace S_f : f \in \G\rbrace$. We observe that the sets in $\mathcal{S}$ are pairwise almost disjoint - indeed, let $f,g \in \G$ such that $f \neq g$. Then they are almost disjoint, and since they take the common value $n$ for all $\alpha \in S_f \cap S_g$, we have that $\vert S_f \cap S_g\vert $ is countable.

Enumerate $\mathcal{S} = \lbrace f_\alpha : \alpha < \omega_2\rbrace$, and write $S_\alpha := S_{f_\alpha}$. We shall now construct a pairwise disjoint family of sets $\mathcal{G}' = \lbrace S_\alpha' : \alpha < \omega_2\rbrace$: Let $S_0' := S_0$. Assume $S_\beta'$ has been constructed for $\beta < \alpha$, all which are stationary and pairwise disjoint. Let $T_\alpha := S_\alpha \cap \lbrace \gamma < \omega_2 : \gamma \geq \alpha\rbrace$, which is still stationary. Define a function $g : T_\alpha \to \omega_2$ by:

$$
\begin{align*}
g(\gamma) =
\begin{cases}
\beta, &\text{if $\gamma \in S_\beta'$ where $\beta < \alpha$} \\
\alpha, &\text{otherwise} \\
\end{cases}
\end{align*}
$$

Note that $g$ is well-defined as $S_\beta'$ are pairwise disjoint for $\beta < \alpha$. Then $g$ is regressive on stationary $T_\alpha$, so by Fodor's theorem we have that $g$ takes a constant value $\delta$ on some stationary set $S_\alpha' \subseteq T_\alpha$. We can't have $\delta < \alpha$, for otherwise we have $S_\alpha' \subseteq S_\alpha \cap S_\delta$, but the latter set is countable. Thus we must have $\delta = \alpha$, i.e. $S_\alpha'$ is disjoint from $S_\beta'$ for all $\beta < \alpha$, as desired. 
$\square$

<a name="ex9.13"></a>
## Exercise 9.13.
<i>Solution.</i> Following the hint, let $x,y \in [H]^n$ such that $n \in x$ and $n \notin y$ (obviously this is possible as $H$ is infinite). Then $F(x) = 1$ but $F(y) = 0$, so $F$ is not constant on $[H]^n$. 
$\square$