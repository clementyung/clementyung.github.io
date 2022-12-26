---
title: "5) The Axiom of Choice and Cardinal Arithmetic"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-5
excerpt: ""
---

{% include commands.html %}

<a name="ex5.1"></a>
## Exercise 5.1.
<a name="lem5.1.A"></a>
<b>Lemma 5.1.A.</b> There are exactly $2^{\aleph_0}$ many open sets, $2^{\aleph_0}$ many closed sets, and $2^{\aleph_0}$ many perfect sets.

\begin{proof}
Let $\lbrace (a_\alpha,b_\alpha) : \alpha < \omega\rbrace$ be an enumeration of all open intervals with rational endpoints (possible as $\vert \Q \times \Q\vert  = \aleph_0$). Then, for any open set $U \subseteq \R$, we may write $U = \bigcup_{\alpha \in I} (a_\alpha,b_\alpha)$ for some $I \subseteq \omega$. Thus, by $\AC$, there exists an injection from $\lbrace \text{open subsets of $\R$}\rbrace$ to $P(\omega)$, in which the latter has cardinality $2^{\aleph_0}$. On the other hand, there are clearly at least $2^{\aleph_0}$ open sets, e.g. those of the form $(-\infty,r)$ for some $r \in \R$. Thus, there are exactly $2^{\aleph_0}$ open sets.

Since $A$ is open iff $\R - A$ is closed, there is a bijection between the collection of open sets and collection of closed sets, so there are also exactly $2^{\aleph_0}$ closed sets.

Since every perfect set is closed, there are at most $2^{\aleph_0}$ closed sets. On the other hand, all closed $[0,r]$, where $r > 0$, are perfect, so there are at least $2^{\aleph_0}$ perfect sets.
\end{proof}

<i>Solution.</i> Let $A,B$ be the sets in the hint. Note that such a construction works, as Theorem 4.5 asserts that $\vert P_\alpha\vert  = 2^{\aleph_0}$ for all $\alpha$, and so $P_\alpha - \lbrace a_\xi : \xi \leq \alpha\rbrace$ is always non-empty, hence all $b_\alpha$'s can indeed be chosen. The construction of $A$ and $B$ also requires $\AC$, since the $a_\alpha$'s and $b_\alpha$'s have to be chosen. Finally, such an enumeration of the perfect sets is possible by <a href="#lem5.1.A">Lemma 5.1.A</a>.

We now show that both $A$ and $B$ contain no perfect subset of reals. This follows from the observation that $A \cap B = \emptyset$, and every perfect set $P_\alpha$ has non-empty intersection with $A$ and $B$. 
$\square$

<a name="ex5.2"></a>
## Exercise 5.2.
<i>Solution.</i> We have:

$$
\begin{align*}
S = [X]^{<\omega} = \bigsqcup_{n < \omega} [X]^n
\end{align*}
$$

Thus, by Lemma 5.7:

$$
\begin{align*}
\vert S\vert  = \sum_{n < \omega} \vert [X]^n\vert  = \sum_{n < \omega}\vert X\vert ^n = \sum_{n < \omega} \vert X\vert  = \vert X\vert 
\end{align*}
$$

where $\vert X\vert ^n = X$ for all $n \in \omega$ as $X$ is infinite. 
$\square$

<a name="ex5.3"></a>
## Exercise 5.3.
<i>Solution.</i> For $\alpha \in \boldsymbol{\mathrm{ORD}}$, define a sequence $\c{x_\alpha : \alpha \in \boldsymbol{\mathrm{ORD}}}$ as follows (which will terminate at some ordinal stage):
<ol>
<li> Let $x_0 \in P$ be arbitrary.</li>

<li> Given $x_\alpha$, let $x_{\alpha+1}$ be any element in $P$ such that $x_{\alpha+1} > x_\alpha$, if it exists (this is possible due to $\AC$). Otherwise, terminate the recursion.</li>

<li> If $\alpha$ is limit, then choose $x_\alpha$ to be any element in $P$ such that $x_\alpha > x_\beta$ for all $\beta < \alpha$, if it exists (again, this is possible due to $\AC$). Otherwise, terminate the recursion.</li>
</ol>
Since $P$ is a set it must terminate at some ordinal, say at stage $\lambda$. We then observe that $\lambda \leq \kappa$ - otherwise, $\lbrace x_\alpha : \alpha < \kappa\rbrace$ is an initial segment of size $\kappa$, a contradiction.

Thus, we have:

$$
\begin{align*}
P = \bigcup_{\alpha < \lambda} \lbrace x \in P : x < x_\alpha\rbrace
\end{align*}
$$

Then:

$$
\begin{align*}
\vert P\vert  \leq \sum_{\alpha < \lambda} \kappa = \lambda \cdot \kappa = \kappa
\end{align*}
$$
 
$\square$

<a name="ex5.4"></a>
## Exercise 5.4.
<i>Solution.</i> We do not use $\AC$ here, for otherwise every set is trivially well-ordered. We present a proof which is essentially equivalent to the hint, but presented differently.

It suffices to show that $2^\alpha$ is linearly ordered for all ordinals $\alpha$, where $2^\alpha$ is the set of all functions $f : \alpha \to 2$. Define a relation $<$ on $2^\omega$ as follows: For two functions $f \neq g$, let $\beta_{f,g} := \min\lbrace \beta < \alpha : f(\beta) \neq g(\beta)\rbrace$. Define:

$$
\begin{align*}
f < g \iff f(\beta_{f,g}) < g(\beta_{f,g})
\end{align*}
$$

Observe that $f(\beta_{f,g}) < g(\beta_{f,g})$ iff $f(\beta_{f,g}) = 0$ and $g(\beta_{f,g}) = 1$. We shall show that this is a linear order. Clearly $f \not< f$ for all $f \in 2^\alpha$, and every $f \neq g$ are comparable. Suppose $f < g$ and $g < h$. We consider cases.
<ol>
<li> Note that we must have $\beta_{f,g} \neq \beta_{g,h}$.</li>

<li> Suppose $\beta_{f,g} < \beta_{g,h}$. Then $f(\beta_{f,g}) = 0$, $g(\beta_{f,g}) = 1$, $g(\beta_{g,h}) = 0$, $h(\beta_{g,h}) = 1$. Since $\beta_{f,g} < \beta_{g,h}$, we must have $h(\beta_{f,g}) = g(\beta_{f,g}) = 1$. Furthermore, if $f(\beta) \neq h(\beta)$ for some $\beta < \min\lbrace \beta_{f,g},\beta_{g,h}\rbrace$, then we must have $g(\beta) \neq f(\beta)$ or $g(\beta) \neq h(\beta)$, contradicting the minimality of $\beta_{f,g}$ or $\beta_{g,h}$. Thus, $\beta_{f,h} = \beta_{f,g}$, and $f(\beta_{f,h}) < h(\beta_{f,h})$.</li>

<li> Suppose $\beta_{f,g} > \beta_{g,h}$. Then this implies that $f(\beta_{g,h}) = g(\beta_{g,h}) = 0$, and $h(\beta_{g,h}) = 1$. By similar reasoning as above, we have $f(\beta) = h(\beta)$ for $\beta < \beta_{g,h}$. Thus $\beta_{f,h} = \beta_{g,h}$ and $f(\beta_{f,h}) < h(\beta_{f,h})$.</li>
</ol>
Thus $f < h$, so transitivity holds for $<$. 
$\square$

<a name="ex5.5"></a>
## Exercise 5.5.
<i>Solution.</i> We follow the hint. We note that $P$ is non-empty, as $\emptyset$ is trivially a choice function on $\emptyset \subseteq S$. Furthermore, if $C \subseteq P$ is a chain, then $\bigcup C$ is clearly an upper bound to this chain. Thus, the premise of Zorn's Lemma is satisfied, so we obtain a maximal element $f \in P$. We shall show that $f$ is a choice function on $S$.

Suppose not, so there exists some $X \in S$ such that $x \notin \dom(f)$. Fix $x \in X$. Then observe that $f \cup \lbrace (X,x)\rbrace$ remains a choice function on $\dom(f) \cup \lbrace X\rbrace \subseteq X$, so $f$ is not maximal, a contradiction. 
$\square$

<a name="ex5.6"></a>
## Exercise 5.6.
<a name="lem5.6.A"></a>
<b>Lemma 5.6.A.</b> Assume the countable $\AC$. Let $\lbrace A_n : n \in \omega\rbrace$ be a countable family of pairwise disjoint sets such that $A_n$ is at most countable for each $n$. Then $A := \bigcup_{n \in \omega} A_n$ is at most countable.

<i>Proof.</i> Let:

$$
\begin{align*}
\F_n := \lbrace f : f \text{ is a function of $A_n$ onto $\omega$}\rbrace
\end{align*}
$$

Since $A_n$ is at most countable, $\F_n$ is non-empty for each $n$. Let $\F := \lbrace \F_n : n \in \omega\rbrace$. Countable $\AC$ endows us a choice function $F$ on $\F$. Then $\F$ is an onto function on $\omega \times \omega \to A$ by:

$$
\begin{align*}
F(m,n) := F(m)(n)
\end{align*}
$$

Thus $\vert A\vert  \leq \vert \omega \times \omega\vert  = \aleph_0$. 
$\blacksquare$

<i>Solution.</i> Let $f$ be a choice function on $S$, so $f(A_n) \in A_n$ for all $n$. Now let:

$$
\begin{align*}
B := \bigcup_{n=0}^\infty \ran(f(A_n)) = \bigcup_{n=0}^\infty \mathbb{\ran(f(A_{n+1})) - \bigcup_{i<n} \ran(f(A_i))}
\end{align*}
$$

Clearly $B \subseteq A$. By <a href="#lem5.6.A">Lemma 5.6.A</a>, $B$ is at most countable. Furthermore, it can't be finite as for every $n \in \omega$ the map $i \mapsto f(A_n)(i)$ is one-to-one. Thus $B$ is countable. 
$\square$

<a name="ex5.7"></a>
## Exercise 5.7.
<i>Solution.</i> Following the hint, we note that each $S_n$ is non-empty. Furthermore, if $f$ is a choice function on $S_n$, then for any $x \in A_{n+1}$, $f \cup \lbrace (A_{n+1},x)\rbrace$ is a choice function on $S_{n+1}$. Thus, the premise of $\DC$ is fulfilled, so there exists a chain of choice functions $f_0 \subseteq f_1 \subseteq \dots$, where $f_i$ is a choice function on $S_i$. Let $f := \bigcup_{i=0}^\infty f_i$, and clearly $f$ is a choice function on $S$. 
$\square$

<a name="ex5.8"></a>
## Exercise 5.8.
<i>Solution.</i> For each ordinal $\alpha < \kappa^+$, we let $\c{X_n^\alpha : n \in \omega}$ denote a sequence of sets satisfying the property in the question.

We induct on $\alpha$. Clearly $X_n^0 = \emptyset$ for all $n$ works. Now suppose $\bigcup X_n^\beta = \beta$ works. Let $X_0^{\beta+1} := \lbrace \beta+1\rbrace$ and let $X_{n+1}^{\beta+1} := X_n^\beta$. Then clearly $\beta + 1 = \bigcup_n X_n^{\beta+1}$ works.

Now suppose $\alpha$ is a limit ordinal. Let $\lbrace \alpha_\gamma : \gamma < \cf(\alpha)\rbrace$ be cofinal. Let $X_0^\alpha := \lbrace 0\rbrace$, and let:

$$
\begin{align*}
X_{n+1}^\alpha := \bigcup_{\gamma < \cf(\alpha)} (X_n^{\alpha_{\gamma+1}} - \alpha_\gamma)
\end{align*}
$$

Then:

$$
\begin{align*}
\bigcup_{n < \omega} X_n^\alpha &= \lbrace \alpha_0\rbrace \cup \bigcup_{n < \omega} \bigcup_{\gamma < \cf(\alpha)} (X_n^{\alpha_{\gamma+1}} - \alpha_\gamma) \\
&= \lbrace \alpha_0\rbrace \cup \bigcup_{\gamma < \cf(\alpha)} \bigcup_{n < \omega} (X_n^{\alpha_{\gamma+1}} - \alpha_\gamma) \\
&= \lbrace \alpha_0\rbrace \cup \bigcup_{\gamma < \cf(\alpha)} (\alpha_{\gamma+1} - \alpha_\gamma) \\
&= \alpha
\end{align*}
$$

We now show that the order types work. We note that for each $n$, we have $X_n^{\alpha_{n+1}} - \alpha_\gamma \subseteq [\alpha_\gamma,\alpha_{\gamma+1}) = \lbrace \beta : \alpha_\gamma \leq \beta < \alpha_{\gamma+1}\rbrace$. Thus, the $X_n^\alpha$'s are pairwise disjoint, so:

$$
\begin{align*}
\otp(X_{n+1}^\alpha) &= \otp\mathbb{\bigcup_{\gamma < \cf(\alpha)} (X_n^{\alpha_{\gamma+1}} - \alpha_\gamma)} \\
&= \sum_{\gamma < \cf(\alpha)} \otp(X_n^{\alpha_{\gamma+1}} - \alpha_\gamma) \\
&\leq \sum_{\gamma < \cf(\alpha)} \otp(X_n^{\alpha_{\gamma+1}}) \\
&\leq \sum_{\gamma < \cf(\alpha)} \kappa^n \\
&= \kappa^n \cdot \cf(\alpha) \\
&\leq \kappa^{n+1}
\end{align*}
$$

Note that $\otp(X_0^\alpha) = \otp(\lbrace \alpha_0\rbrace) = 1 = \kappa^0$, so $\alpha = \bigcup_n X_n^\alpha$ works. 
$\square$

<a name="ex5.9"></a>
## Exercise 5.9.
<i>Solution.</i> Let:

$$
\begin{align*}
\F := \ss{f : f \text{ is a one-to-one function of $\bigcup_{i \in J} X_i$ onto $\bigcup_{i \in J} Y_i$ for some $J \subseteq I$}}
\end{align*}
$$

Partially ordered by inclusion. Clearly $\F$ is non-empty, for if $J = \lbrace i\rbrace$ for some $i \in I$ then any one-to-one function $f$ of $X_i$ onto $Y_i$ would be in $\F$. If $C \subseteq \F$ is a chain, then $\bigcup C$ is clearly an upper bound. Thus, let $f \in \F$ be maximal by Zorn's lemma. Then $f$ is a one-to-one function of $\bigcup_{i \in I} X_i$ onto $\bigcup_{i \in I} Y_i$ - otherwise, if $\dom(f) = \bigcup_{i \in J} X_i$ and $i' \notin J$, then let $f_{i'} : X_i \to Y_i$ be one-to-one and onto. Then $f \cup f_{i'}$ would be an element that strictly contains $f$, contradicting maximality. Thus $\mod{\bigcup_{i \in I} X_i} = \mod{\bigcup_{i \in I} Y_i}$. 
$\square$

<a name="ex5.10"></a>
## Exercise 5.10.
<i>Solution.</i> The proof is almost identical to that of <a href="#ex5.9">Exercise 5.9</a>, but replace $\bigcup$ with $\prod$. 
$\square$

<a name="ex5.11"></a>
## Exercise 5.11.
<i>Solution.</i> By Lemma 5.9:

$$
\begin{align*}
\prod_{0 < n < \omega} n = (\sup_n n)^{\aleph_0} = (\aleph_0)^{\aleph_0} = 2^{\aleph_0}
\end{align*}
$$
 
$\square$

<a name="ex5.12"></a>
## Exercise 5.12.
<i>Solution.</i> By Lemma 5.9:

$$
\begin{align*}
\prod_{n < \omega} \aleph_n = (\sup_n \aleph_n)^{\aleph_0} = \aleph_\omega^{\aleph_0}
\end{align*}
$$
 
$\square$

<a name="ex5.13"></a>
## Exercise 5.13.
<i>Solution.</i> By Lemma 5.9:

$$
\begin{align*}
\prod_{\alpha < \omega + \omega} \aleph_\alpha = (\sup_{\alpha<\omega+\omega} \aleph_\alpha)^{\aleph_0} = \aleph_{\omega+\omega}^{\aleph_0}
\end{align*}
$$
 
$\square$

<a name="ex5.14"></a>
## Exercise 5.14.
<a name="ex5.14(i)"></a>
### Exercise 5.14(i).
<i>Solution.</i> If $\kappa = \aleph_{\alpha+1}$ then:

$$
\begin{align*}
\aleph_{\alpha+1} = 2^{\aleph_\alpha} = \sup_{\beta<\alpha+1} 2^{\aleph_\beta} = 2^{<\aleph_{\alpha+1}}
\end{align*}
$$

If $\kappa = \aleph_\alpha$, and $\alpha$ is a limit ordinal, then:

$$
\begin{align*}
\aleph_\alpha = \sup_{\beta<\alpha} \aleph_\beta = \sup_{\beta<\alpha} \aleph_{\beta+1} = \sup_{\beta<\alpha} 2^{\aleph_\beta} = 2^{<\aleph_\alpha}
\end{align*}
$$
 
$\square$

<a name="ex5.14(ii)"></a>
### Exercise 5.14(ii).
<i>Solution.</i> By Theorem 5.15:

$$
\begin{align*}
\kappa^{<\kappa} = \sup_{\lambda<\kappa} \kappa^\lambda = \sup_{\lambda<\kappa} \kappa = \kappa
\end{align*}
$$
 
$\square$

<a name="ex5.15"></a>
## Exercise 5.15.
<i>Solution.</i> We fill in some details of the hint.
<ol>
<li> $\alpha \leq \beta$, as for all $\alpha > \beta$ we have $\alpha + \beta \geq \beta + \beta > \beta$.</li>

<li> If $\alpha + \beta = \beta$, then $\alpha + 1 + \beta = \alpha + \beta = \beta$ as $\beta \geq \omega$. Thus $\alpha$ is a limit ordinal.</li>

<li> $\beta < \alpha + \beta \implies \alpha + \beta < \alpha + \alpha + \beta$, so $\aleph_{\alpha+\beta} < \aleph_{\alpha+\alpha+\beta}$.</li>
</ol> 
$\square$

<a name="ex5.16"></a>
## Exercise 5.16.
$\prod_{\alpha<\omega_1+\omega} \aleph_\alpha = \aleph_{\omega_1+\omega}^{\aleph_1}$.

\begin{hint}
$\aleph_{\omega_1+\omega}^{\aleph_1} \leq \mathbb{\prod_{n=0}^\infty \aleph_{\omega_1+n}}^{\aleph_1} = \prod_n \aleph_{\omega_1+n}^{\aleph_1} = \prod_n (\aleph_{\omega_1}^{\aleph_1} \cdot \aleph_{\omega_1+n}^{\aleph_1}) = \aleph_{\omega_1}^{\aleph_1} \cdot \prod_n \aleph_{\omega_1+n} = \prod_{\alpha<\omega_1+\omega} \aleph_\alpha$.
\end{hint}

<i>Solution.</i> Alternatively, observe that one may easily generalise Lemma 5.9 such that for ordinals $\alpha$, we have:

$$
\begin{align*}
\prod_{i < \alpha} \kappa_i = \mathbb{\sup_i \kappa_i}^{\vert \alpha\vert }
\end{align*}
$$

In which then this exercise follows immediately. 
$\square$

<a name="ex5.17"></a>
## Exercise 5.17.
If $\kappa$ is a limit cardinal and $\lambda < \cf{\kappa}$, then $\kappa^\lambda = \sum_{\alpha<\kappa} \vert \alpha\vert ^\lambda$.

<i>Solution.</i> On one hand we have $\sum_{\alpha<\kappa} \vert \alpha\vert ^\lambda \leq \sum_{\alpha<\kappa} \kappa^\lambda = \kappa$. On the other hand, since $\lambda < \cf(\kappa)$ we have that all subsets in $[\kappa]^\lambda$ are bounded, so:

$$
\begin{align*}
[\kappa]^\lambda = \bigcup_{\alpha < \kappa} [\alpha]^\lambda
\end{align*}
$$

Therefore:

$$
\begin{align*}
\kappa^\lambda = \vert [\kappa]^\lambda\vert  = \mod{\bigcup_{\alpha<\kappa} [\alpha]^\lambda} \leq \sum_{\alpha<\kappa} \vert [\alpha]^\lambda\vert  = \sum_{\alpha<\kappa} \vert \alpha\vert ^\lambda
\end{align*}
$$
 
$\square$

<a name="ex5.18"></a>
## Exercise 5.18.
$\aleph_\omega^{\aleph_1} = \aleph_\omega^{\aleph_0} \cdot 2^{\aleph_1}$.

<a name="lem5.18.A"></a>
<b>Lemma 5.18.A.</b> For $\beta < \omega_{\alpha+1}$, we have:

$$
\begin{align*}
\aleph_\beta^{\aleph_{\alpha+1}} = \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}
\end{align*}
$$

<i>Proof.</i> Note that clearly $\aleph_\beta^{\aleph_{\alpha+1}} \geq \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}$, so it suffices to prove $\leq$. We induct on $\beta$. For $\beta \leq \alpha + 1$, by Theorem 5.20(i) we have:

$$
\begin{align*}
\aleph_\beta^{\aleph_{\alpha+1}} = 2^{\aleph_{\alpha+1}} = 2^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}} = \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}
\end{align*}
$$

Note that $2^{\aleph_\alpha} \leq \aleph_{\alpha+1}^{\aleph_\alpha} \leq (2^{\aleph_\alpha})^{\aleph_\alpha} = 2^{\aleph_\alpha}$. Now assume that $\beta > \alpha + 1$. Suppose $\aleph_\beta^{\aleph_{\alpha+1}} = \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}$. Then, by the Hausdorff formula:

$$
\begin{align*}
\aleph_{\beta+1}^{\aleph_{\alpha+1}} &= \aleph_\beta^{\aleph_{\alpha+1}} \cdot \aleph_{\beta+1} \\
&= \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}} \cdot \aleph_{\beta+1} \\
&= \aleph_\beta^{\aleph_\alpha} \cdot \aleph_{\beta+1} \cdot 2^{\aleph_{\alpha+1}} \\
&= \aleph_{\beta+1}^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}
\end{align*}
$$

Now suppose $\beta$ is a limit ordinal, and for all $\gamma < \beta$ we have $\aleph_\gamma^{\aleph_{\alpha+1}} = \aleph_\gamma^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}$. By Theorem 5.20, there are three possible cases ((i) is not possible as $\beta > \alpha + 1$).
<ol>
<li> If $\aleph_\beta^{\aleph_{\alpha+1}} = \aleph_\gamma^{\aleph_{\alpha+1}}$ for some $\gamma < \beta$, then:

$$
\begin{align*}
\aleph_\beta^{\aleph_{\alpha+1}} = \aleph_\gamma^{\aleph_{\alpha+1}} = \aleph_\gamma^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}} \leq \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}
\end{align*}
$$
</li>

<li> If $\cf(\aleph_\beta) > \aleph_{\alpha+1}$, then:

$$
\begin{align*}
\aleph_\beta^{\aleph_{\alpha+1}} = \aleph_\beta \leq \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}
\end{align*}
$$
</li>

<li> If $\cf(\aleph_\beta) \leq \aleph_{\alpha+1}$, then since $\aleph_{\alpha+1} < \aleph_\beta$:

$$
\begin{align*}
\aleph_\beta^{\aleph_{\alpha+1}} = \aleph_\beta^{\cf(\aleph_\beta)} \leq \aleph_\beta^{\aleph_\alpha} \leq \aleph_\beta^{\aleph_\alpha} \cdot 2^{\aleph_{\alpha+1}}
\end{align*}
$$
</li>
</ol>
This completes the induction. 
$\blacksquare$

<i>Solution.</i> This follows from <a href="#lem5.18.A">Lemma 5.18.A</a>. 
$\square$

<a name="ex5.19"></a>
## Exercise 5.19.
If $\alpha < \omega_1$, then $\aleph_\alpha^{\aleph_1} = \aleph_\alpha^{\aleph_0} \cdot 2^{\aleph_1}$.

<i>Solution.</i> This follows from <a href="#lem5.18.A">Lemma 5.18.A</a>. 
$\square$

<a name="ex5.20"></a>
## Exercise 5.20.
If $\alpha < \omega_2$, then $\aleph_\alpha^{\aleph_2} = \aleph_\alpha^{\aleph_1} \cdot 2^{\aleph_2}$.

<i>Solution.</i> This follows from <a href="#lem5.18.A">Lemma 5.18.A</a>. 
$\square$

<a name="ex5.21"></a>
## Exercise 5.21.
If $\kappa$ is regular and limit, then $\kappa^{<\kappa} = 2^{<\kappa}$. If $\kappa$ is regular and strong limit then $\kappa^{<\kappa} = \kappa$.

<i>Solution.</i> Suppose $\kappa$ is regular and limit. Clearly $\kappa^{<\kappa} \geq 2^{<\kappa}$. On the other hand, let $\lambda < \kappa$. Since $\kappa$ is regular, we have:

$$
\begin{align*}
\kappa^\lambda = \sum_{\mu < \kappa} \mu^\lambda \leq \sum_{\mu < \kappa} 2^{\mu^+} = 2^{<\kappa}
\end{align*}
$$

Suppose $\kappa$ is regular and strong limit. Clearly $\kappa^{<\kappa} \geq 2^{<\kappa}$. On the other hand, by above we have $\kappa^{<\kappa} = 2^{<\kappa}$. Since $\kappa$ is strong limit, we have $2^\lambda < \kappa$ for all $\lambda < \kappa$. Thus $2^{<\kappa} \leq \kappa$. 
$\square$

<a name="ex5.22"></a>
## Exercise 5.22.
If $\kappa$ is singular and is not strong limit, then $\kappa^{<\kappa} = 2^{<\kappa} > \kappa$.

<i>Solution.</i> Again, clearly $\kappa^{<\kappa} \geq 2^{<\kappa}$. On the other hand, let $\lambda < \kappa$. Since $\kappa$ is not a strong limit, there exists $\mu < \kappa$ such that $\kappa \leq 2^\mu$. Then $\kappa^\lambda \leq (2^\mu)^{\lambda} = 2^{\mu \cdot \lambda} \leq 2^{<\kappa}$, so $\kappa^{<\kappa} \leq 2^{<\kappa}$.

For the second inequality, it follows from Corollary 5.14 that $\kappa < \kappa^{\cf(\kappa)} \leq \kappa^{<\kappa}$. 
$\square$

<a name="ex5.23"></a>
## Exercise 5.23.
If $\kappa$ is singular and strong limit, then $2^{<\kappa} = \kappa$ and $\kappa^{<\kappa} = \kappa^{\cf(\kappa)}$.

<i>Solution.</i> Since $\kappa$ is a strong limit:

$$
\begin{align*}
\kappa = \sup\lbrace \lambda : \lambda < \kappa\rbrace \leq \underbrace{\sup\lbrace 2^\lambda : \lambda < \kappa\rbrace}_{=2^{<\kappa}} \leq \kappa
\end{align*}
$$

For the second equality, we note that for $\lambda < \kappa$ and $\mu < \kappa$, we have $\mu^\lambda \leq 2^{\mu^+} < \kappa$. Thus for $\lambda \geq \cf(\kappa)$ we have $\kappa^\lambda = \kappa^{\cf(\kappa)}$ by Theorem 5.20. This implies that $\kappa^{<\kappa} = \kappa^{\cf(\kappa)}$. 
$\square$

<a name="ex5.24"></a>
## Exercise 5.24.
If $2^{\aleph_0} > \aleph_\omega$, then $\aleph_\omega^{\aleph_0} = 2^{\aleph_0}$.

<i>Solution.</i> 
$$
\begin{align*}
2^{\aleph_0} \leq \aleph_\omega^{\aleph_0} \leq (2^{\aleph_0})^{\aleph_0} = 2^{\aleph_0}
\end{align*}
$$
 
$\square$

<a name="ex5.25"></a>
## Exercise 5.25.
If $2^{\aleph_1} = \aleph_2$ and $\aleph_\omega^{\aleph_0} > \aleph_{\omega_1}$, then $\aleph_{\omega_1}^{\aleph_1} = \aleph_\omega^{\aleph_0}$.

<i>Solution.</i> By <a href="#ex5.18">Exercise 5.18</a>:

$$
\begin{align*}
\aleph_\omega^{\aleph_0} \leq \aleph_{\omega_1}^{\aleph_1} \leq (\aleph_\omega^{\aleph_0})^{\aleph_1} = \aleph_\omega^{\aleph_1} = \aleph_\omega^{\aleph_0} \cdot 2^{\aleph_1} = \aleph_\omega^{\aleph_0} \cdot \aleph_2 = \aleph_\omega^{\aleph_0}
\end{align*}
$$
 
$\square$

<a name="ex5.26"></a>
## Exercise 5.26.
If $2^{\aleph_0} \geq \aleph_{\omega_1}$, then $\gimel(\aleph_\omega) = 2^{\aleph_0}$ and $\gimel(\aleph_{\omega_1}) = 2^{\aleph_1}$.

<i>Solution.</i> We have $\gimel(\aleph_\omega) = \aleph_\omega^{\aleph_0}$, and:

$$
\begin{align*}
2^{\aleph_0} = \aleph_\omega^{\aleph_0} \leq \aleph_{\omega_1}^{\aleph_0} \leq (2^{\aleph_0})^{\aleph_0} = 2^{\aleph_0}
\end{align*}
$$

For second part, we have $\gimel(\aleph_{\omega_1}) = \aleph_{\omega_1}^{\aleph_1}$, and:

$$
\begin{align*}
2^{\aleph_1} = \aleph_{\omega_1}^{\aleph_1} \leq (2^{\aleph_0})^{\aleph_1} = 2^{\aleph_1}
\end{align*}
$$
 
$\square$

<a name="ex5.27"></a>
## Exercise 5.27.
If $2^{\aleph_1} = \aleph_2$, then $\aleph_\omega^{\aleph_0} \neq \aleph_{\omega_1}$.

<i>Solution.</i> If $2^{\aleph_1} = \aleph_2$ then by <a href="#ex5.18">Exercise 5.18</a> we have $\aleph_\omega^{\aleph_0} = \aleph_\omega^{\aleph_1}$. Thus, if $\aleph_\omega^{\aleph_1} = \aleph_{\omega_1}$ then:

$$
\begin{align*}
\cf(\aleph_\omega^{\aleph_1}) = \cf(\aleph_{\omega_1}) = \omega_1
\end{align*}
$$

contradicting Corollary 5.13. 
$\square$

<a name="ex5.28"></a>
## Exercise 5.28.
If $\kappa$ is a singular cardinal and if $\kappa < \gimel(\lambda)$ for some $\lambda < \kappa$ such that $\cf{\kappa} \leq \cf{\lambda}$ then $\gimel(\kappa) \leq \gimel(\lambda)$.

<i>Solution.</i> 
$$
\begin{align*}
\gimel(\kappa) = \kappa^{\cf(\kappa)} \leq (\lambda^{\cf(\lambda)})^{\cf(\kappa)} \leq (\lambda^{\cf(\lambda)})^{\cf(\lambda)} = \lambda^{\cf(\lambda)} = \gimel(\lambda)
\end{align*}
$$
 
$\square$

<a name="ex5.29"></a>
## Exercise 5.29.
If $\kappa$ is a singular cardinal such that $2^{\cf{\kappa}} < \kappa \leq \lambda^{\cf{\kappa}}$ for some $\lambda < \kappa$, then $\gimel(\kappa) = \gimel(\lambda)$ where $\lambda$ is the least $\lambda$ such that $\kappa \leq \lambda^{\cf{\kappa}}$.

<i>Solution.</i> By Theorem 5.20(ii), we have that $\gimel(\kappa) = \kappa^{\cf(\kappa)} = \lambda^{\cf(\kappa)}$. If $\mu < \lambda$ and $\mu^{\cf(\kappa)} \geq \lambda$, then $\mu^{\cf(\kappa)} = \lambda^{\cf(\kappa)}$, contradicting minimality of $\lambda$. Thus, we must have that $\mu^{\cf(\kappa)} < \lambda$ for all $\mu < \lambda$.

Now observe that we can't have $\cf(\lambda) > \cf(\kappa)$ - otherwise, by Theorem 5.20(iii) we have $\lambda^{\cf(\kappa)} = \lambda < \kappa$, a contradiction. Thus, by the same theorem, $\cf(\lambda) \leq \cf(\kappa)$ implies that $\lambda^{\cf(\kappa)} = \lambda^{\cf(\lambda)} = \gimel(\lambda)$, as desired. 
$\square$