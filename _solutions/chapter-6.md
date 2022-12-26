---
title: "6) The Axiom of Regularity"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-6
excerpt: ""
---

{% include commands.html %}

<a name="ex6.1"></a>
## Exercise 6.1.
<i>Solution.</i> We induct on $\rank(x)$. If $\rank(x) = 0$, then $\lbrace \rank(z) + 1 : z \in x\rbrace = \emptyset$, so $\sup\lbrace \rank(z) + 1 : z \in x\rbrace = 0$.

If $\rank(x) = \alpha + 1$, then $x \in V_{\alpha+1} \implies x \subseteq V_\alpha$. In other words, every $z \in x$ has $\rank(z) \leq \alpha$. Thus:

$$
\begin{align*}
\sup\lbrace \rank(z) + 1 : z \in x\rbrace \leq \sup\lbrace \alpha + 1 : z \in x\rbrace = \alpha + 1 = \rank(x)
\end{align*}
$$

On the other hand, suppose $\beta := \sup\lbrace \rank(z) + 1 : z \in x\rbrace < \rank(x) \implies \sup\lbrace \rank(z) + 1 : z \in x\rbrace \leq \alpha$. Then $\beta + 1 \leq \alpha$, and $\rank(z) + 1 \leq \beta + 1 \implies z \in V_\beta$ for all $z \in x$. Thus, $x \subseteq P(V_\beta) = V_{\beta + 1} \subseteq V_\alpha$. contradicting the minimality of $\rank(x) = \alpha + 1$.

If $\rank(x) = \alpha$ is a limit ordinal, then we must have:

$$
\begin{align*}
\forall \beta < \alpha \, \exists z \in x \, (z \in V_\beta \wedge \forall \gamma < \beta \, (z \notin V_\gamma))
\end{align*}
$$

In other words:

$$
\begin{align*}
\forall \beta < \alpha \, \exists z \in x \, (\rank(z) = \beta)
\end{align*}
$$

which implies that $\sup\lbrace \rank(z) + 1 : z \in x\rbrace = \alpha$. 
$\square$

<a name="ex6.2"></a>
## Exercise 6.2.
<i>Solution.</i> We induct on $\alpha$ on the second assertion. For the base case $\alpha = 0$, we note that $V_\omega = \bigcup_{n < \omega} V_n$, and it's easy to see that $\vert V_{n+1}\vert  = 2^{\vert V_n\vert }$. Thus, $V_\omega$ is a countable union of finite sets, hence:

$$
\begin{align*}
\vert V_\omega\vert  \leq \sum_{n < \omega} \vert V_n\vert  \leq \sum_{n < \omega} \aleph_0 = \aleph_0 \cdot \aleph_0 = \aleph_0
\end{align*}
$$

On the other hand, clearly $\omega \subseteq V_\omega$, so $\vert V_\omega\vert  \geq \aleph_0$.

If $\alpha = \beta + 1$, then $V_{\omega + \beta+1} = P(V_{\omega + \beta})$, so by Lemma 3.3 $\vert V_{\omega+\beta+1}\vert  = 2^{\vert V_{\omega + \beta}\vert }$. By induction hypothesis, $\vert V_{\omega + \beta}\vert  = \beth_{\omega + \beta}$, so $\vert V_{\omega+\beta+1}\vert  = 2^{\beth_\beta} = \beth_{\omega+\beta+1}$.

If $\alpha$ is a limit ordinal, then first let:

$$
\begin{align*}
V_\beta' := V_\beta - \bigcup_{\gamma < \beta} V_\gamma
\end{align*}
$$

Note that:

$$
\begin{align*}
\vert V_\beta'\vert  =
\begin{cases}
\vert V_\beta\vert , &\text{if $\beta$ is not a limit ordinal} \\
0, &\text{otherwise}
\end{cases}
\end{align*}
$$

and $\c{V_\beta' : \beta < \alpha}$ is a disjoint family of sets. Thus, we have:

$$
\begin{align*}
\vert V_{\omega+\alpha}\vert  = \sum_{\beta < \omega + \alpha} \vert V_\beta'\vert  = \vert \aleph_0 + \alpha\vert  \cdot \sup_{\beta<\alpha} \beth_\beta = \vert \alpha\vert  \cdot \beth_\alpha
\end{align*}
$$

Since $\beth_\alpha \geq \alpha$ for all $\alpha$ (easy to prove via induction), we have that $\vert V_{\omega+\alpha}\vert  = \beth_\alpha$. 
$\square$

<a name="ex6.3"></a>
## Exercise 6.3.
<a name="lem6.3.A"></a>
<b>Lemma 6.3.A.</b> If $\kappa$ is uncountable inaccessible, then $\kappa = \aleph_\kappa = \beth_\kappa$.

<i>Proof.</i> Note that clearly $\kappa \leq \aleph_\kappa \leq \beth_\kappa$. To show that $\beth_\kappa \leq \kappa$, since $\beth_\kappa = \sup\lbrace \beth_\alpha : \alpha < \kappa\rbrace$, it suffices to show that if $\alpha < \kappa$ then $\beth_\alpha < \kappa$.

We prove this by transfinite induction.
<ol>
<li> Since $\kappa$ is uncountable, $\beth_0 = \aleph_0 < \kappa$.</li>

<li> If $\beth_\alpha < \kappa$, then since $\kappa$ is a strong limit, we have that $\beth_{\alpha+1} = 2^{\beth_\alpha} < \kappa$.</li>

<li> If $\alpha$ is a limit ordinal, then $\sup\lbrace \beth_\beta : \beta < \alpha\rbrace \leq \kappa$. Since $\kappa$ is regular and $\alpha < \kappa$, then inequality must be strict.</li>
</ol> 
$\blacksquare$

<i>Solution.</i> If $\kappa = \omega$, then $\vert V_\omega\vert  = \aleph_0$ by <a href="#ex6.2">Exercise 6.2</a>. Otherwise, since $\kappa$ is uncountable we have $\omega + \kappa = \kappa$ (here addition is ordinal addition). Thus, by <a href="#ex6.2">Exercise 6.2</a> and <a href="#lem6.3.A">Lemma 6.3.A</a>, we have $\vert V_\kappa\vert  = \beth_\kappa$. 
$\square$

<a name="ex6.4"></a>
## Exercise 6.4.
<i>Solution.</i> We can do better. We show that if $\rank(x) = \alpha$ and $\rank(y) = \beta$, then:

| Set | Header2 |
|:--:|:----:|
| $\lbrace x,y\rbrace$ | $\max\lbrace\alpha,\beta\rbrace + 1$ |
| $\c{x,y}$ | $\max\lbrace\alpha,\beta\rbrace + 2$ |
| $x \cup y$ | $\max\lbrace\alpha,\beta\rbrace$ |
| $\bigcup x$ | $\bigcup \alpha$ |
| $P(x)$ | $\alpha + 1$ |
| $x^y$ | $\max\lbrace\alpha,\beta\rbrace$ |

We use <a href="#ex6.1">Exercise 6.1</a>. It's clear that if $x \subseteq y$ then $\rank(x) \leq \rank(y)$.

<u>$\lbrace x,y\rbrace$:</u>

$$
\begin{align*}
\rank(\lbrace x,y\rbrace) &= \sup\lbrace \rank(x)+1,\rank(y)+1\rbrace \\
&= \max\lbrace \alpha+1,\beta+1\rbrace \\
&= \max\lbrace \alpha,\beta\rbrace + 1
\end{align*}
$$

<u>$\c{x,y}$:</u>

$$
\begin{align*}
\rank(\c{x,y}) &= \rank(\lbrace \lbrace x\rbrace,\lbrace x,y\rbrace\rbrace) \\
&= \sup\lbrace \rank(\lbrace x\rbrace)+1,\rank(\lbrace x,y\rbrace)+1\rbrace \\
&= \max\lbrace \rank(x)+2,\rank(\lbrace x,y\rbrace)+1\rbrace \\
&= \max\lbrace \alpha+2,\max\lbrace \alpha,\beta\rbrace+2\rbrace \\
&= \max\lbrace \alpha,\beta\rbrace+2
\end{align*}
$$

<u>$x \cup y$:</u>

$$
\begin{align*}
\rank(x \cup y) &= \sup\lbrace \rank(z) + 1 : z \in x \cup y\rbrace \\
&= \sup\lbrace \sup\lbrace \rank(z) + 1 : z \in x\rbrace, \sup\lbrace \rank(z) + 1 : z \in y\rbrace\rbrace \\
&= \sup\lbrace \rank(x),\rank(y)\rbrace \\
&= \max\lbrace \alpha,\beta\rbrace
\end{align*}
$$

<u>$\bigcup x$:</u> We note that $z \in \bigcup x$ iff $z \in y$ for some $y \in x$. This implies that $\rank(z) + 2 \leq \rank(x)$, so $\rank(z) + 1 < \rank(x)$. Therefore:

$$
\begin{align*}
\rank\mathbb{\bigcup x} &= \sup\ss{\rank(z) + 1 : z \in \bigcup x} \\
&\leq \sup\lbrace \beta : \beta < \rank(x)\rbrace \\
&= \bigcup \alpha
\end{align*}
$$

On the other hand, suppose $\rank\mathbb{\bigcup x} < \bigcup \alpha$, so there exists some $\beta < \alpha$ such that $\rank\mathbb{\bigcup x} < \beta$. Since $\rank(x) = \alpha$, there exists $y \in x$ such that $\rank(y) \geq \beta$. Since $\rank\mathbb{\bigcup x} < \beta$, this implies that $\rank(z) + 1 \geq \rank\mathbb{\bigcup x}$ for some $z \in y$. This contradicts that $\rank(z) + 1 < \rank(x)$.

<u>$P(x)$:</u> Since $x \in P(x)$, clearly $\rank(x) + 1 \leq P(x)$. On the other hand:

$$
\begin{align*}
\rank(P(x)) &= \sup\lbrace \rank(z) + 1 : z \in P(x)\rbrace \\
&= \sup\lbrace \rank(z) + 1 : z \subseteq x\rbrace \\
&\leq \sup\lbrace \rank(x) + 1 : z \subseteq x\rbrace \\
&= \rank(x) + 1
\end{align*}
$$

<u>$x^y$:</u> We first note that for all $f \in x^y$, we have $f \subseteq y \times x$. Since:

$$
\begin{align*}
\rank(y \times x) &= \sup\lbrace \rank(\c{z,w}) + 1 : z \in y \wedge w \in x\rbrace \\
&= \sup\lbrace \max\lbrace \rank(z)+1,\rank(w)+1\rbrace + 1 : z \in y \wedge w \in x\rbrace \\
&\leq \max\lbrace \rank(y),\rank(x)\rbrace + 1 \\
&= \max\lbrace \alpha,\beta\rbrace + 1
\end{align*}
$$

Therefore, $\rank(f) \leq \max\lbrace \alpha,\beta\rbrace + 1$ for all $f \in x^y$, so $\rank(x^y) \leq \max\lbrace \alpha,\beta\rbrace + 2$. On the other hand, for each $\gamma < \max\lbrace \alpha,\beta\rbrace$, let $\c{z,w} \in y \times x$ such that $\max\lbrace \rank(z),\rank(w)\rbrace > \gamma$. Then there exists a function $f \in x^y$ such that $\c{z,w} \in f$, Therefore:

$$
\begin{align*}
\rank(x^y) \geq \rank(f) + 1 \geq \max\lbrace \rank(z),\rank(w)\rbrace + 2 > \gamma + 2
\end{align*}
$$

for all $\gamma < \max\lbrace \alpha,\beta\rbrace$. 
$\square$

<a name="ex6.5"></a>
## Exercise 6.5.
<i>Solution.</i> While these sets do not have universally agreed set-theoretic definitions, it is sufficient to define $\Z$, $\Q$ and $\R$ in $V_{\omega+\omega}$ in their "intended way".

<u>Integers:</u> For $\Z$, we may define it as (along with some operation $+$) the unique infinite cyclic group. we first note that $\boldsymbol{N} \in V_{\omega+1}$. Now define an equivalence relation $\sim$ on $\boldsymbol{N} \times \boldsymbol{N}$ by stipulating that:

$$
\begin{gather*}
(m,n) \sim (m',n') \\
\iff \\
\exists k \in \boldsymbol{N} \, ((m = n + k \wedge m' = n' + k) \vee (m + k = n \wedge m' + k = n))
\end{gather*}
$$

Define $\Z := (\boldsymbol{N} \times \boldsymbol{N})/\sim$. Clearly $\Z$ can be defined in $V_{\omega+\omega}$. Now define the operation $+$ by stipulating that:

$$
\begin{align*}
[(m,n)] + [(m',n')] := [(m + m',n + n')]
\end{align*}
$$

We first show that $+$ is well-defined (which will then clearly be definable in $V_{\omega+\omega}$). Suppose $(m_1,n_1) \sim (m_2,n_2)$ and $(m_1',n_1') \sim (m_2',n_2')$. Let $k,k' \in \boldsymbol{N}$, and for one case suppose they are such that $m_1 = n_1 + k$ and $m_1' = n_1' + k'$. Then:

$$
\begin{align*}
m_1 + m_1' = n_1 + n_1' + (k + k'), \; m_2 + m_2' = n_2 + n_2' + (k + k')
\end{align*}
$$

The other three cases are similar. Clearly $+$ is commutative, associative, and $[(0,0)]$ the identity element. For inverse, define:

$$
\begin{align*}
[(m,n)]^{-1} := [(n,m)]
\end{align*}
$$

Then $[(m,n)] + [(n,m)] = [(m+n,m+n)] = [(0,0)]$, so $(\Z,+)$ is the unique infinite cyclic group.

<u>Rationals:</u> For $\Q$, we consider another equivalence relation $\sim$ on $\Z \times (\Z - \lbrace 0\rbrace)$, where $0$ is the identity element of $(\Z,+)$, as follows (it is no longer relevant how $\Z$ is defined - it only matters that $\Z \in V_{\omega+\omega}$):

$$
\begin{align*}
(m,n) \sim (m',n') \iff \exists j,k \in \boldsymbol{N} \, (j \cdot m = k \cdot n \wedge j \cdot m' = k \cdot n')
\end{align*}
$$

Here $\cdot$ denotes multiplication on $\Z$ which may be defined in the usual way using $+$. Now define $+,\times$ on $\Q/\sim$ by stipulating that:

$$
\begin{gather*}
[(m,n)] + [(m',n')] = (m \cdot n' + m' \cdot n,n \cdot n') \\
[(m,n)] \times [(m',n')] = (m \cdot m', n \cdot n')
\end{gather*}
$$

One may show that $+$ and $\times$ are well-defined (and are clearly definable in $V_{\omega+\omega}$), and make $(\Q,+,\times)$ the commutative ring as intended.

<u>Reals:</u> For $\R$, they are canonically defined using Dedekind cuts on $\Q$ (see Theorem 4.4). All Dedekind cuts are clearly definable in $V_{\omega,\omega}$. Proving that the $+$ and $\times$ operations (which will be defined in the obvious sense) work are tedious - we refer to readers to Rudin's book. 
$\square$

<a name="ex6.6"></a>
## Exercise 6.6.
<a name="ex6.6(i)"></a>
### Exercise 6.6(i).
<i>Solution.</i> We induct on $\rank(x)$. Since $V_0 = \emptyset$, the base case is trivial. Suppose the statement holds for ranks $\beta < \alpha$, and suppose $\rank(x) = \alpha$.

<u>$\implies$:</u> If $x \in B$, then by definition we have $x \in A$ and $x \subseteq B \subseteq A$, i.e. $\forall y \in x \, (y \in B)$. Since $\rank(y) < \rank(x)$, we have that $\TC(y) \subseteq A$. Thus, $\TC(x) = x \cup \bigcup_{y \in x} \TC(y) \subseteq A$.

<u>$\impliedby$:</u> We note that if $y \in x$, then $\TC(y) \subseteq A$. By induction hypothesis, $y \in B$ for all $y \in x$, so $x \subseteq B$. Thus, $x \in B$. 
$\square$

<a name="ex6.6(ii)"></a>
### Exercise 6.6(ii).
<i>Solution.</i> Let $C \subseteq A$ be another transitive class. We induct on $\rank(x)$ showing that if $x \in C$, then $x \in B$. Again, base case is trivial, so suppose the statement holds for ranks $\beta < \alpha$, and suppose $\rank(x) = \alpha$.

Let $x \in C$. Since $C$ is transitive, $y \in C$ for all $y \in x$. Since $\rank(y) < \rank(x)$, by induction hypothesis we have that $y \in B$. In other words, $x \subseteq B$. By definition of $B$, $x \in B$. 
$\square$