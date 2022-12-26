---
title: "4) Real Numbers"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-4
excerpt: ""
---

{% include commands.html %}

<a name="ex4.1"></a>
## Exercise 4.1.
<i>Solution.</i> Let $C(\R)$ be the set of all continuous functions $\R \to \R$. Following the hint, by identifying the continuous functions $f : \R \to \R$ by their definition on $\Q$, there is an injection $F : C(\R) \to {}^{\R}\Q$ given by $F(f) = f\restrictedto\Q$. But $\vert {}^{\R}\Q\vert  = \vert \R\vert ^{\vert \Q\vert } = (2^{\aleph_0})^{\aleph_0} = 2^{\aleph_0 \cdot \aleph_0} = 2^{\aleph_0} = \mathfrak{c}$. 
$\square$

<a name="ex4.2"></a>
## Exercise 4.2.
<i>Solution.</i> We shall write:

$$
\begin{align*}
\tau_a = a_0 + \xi_0 + a_1 + \xi_1 + a_2 + \xi_2 + \cdots
\end{align*}
$$

Suppose $\tau_a = \tau_b$, so there exists an isomorphism $f : \tau_a \to \tau_b$. Suppose for a contradiction that there is some $n$ such that $a_n \neq b_n$. Let $n$ be the least natural number such that $a_n \neq b_n$, and assume WLOG that $a_n > b_n$. Let $y = \max b_n$, and suppose $f(x) = y$. Then $y < f(x + 1) \in \xi_n$. Since $\xi_n$ is the order-type of the integers, there exists a $y' \in \tau_b$ such that $f(x) < y' < f(x + 1)$. By order-preserving property, there is no $x'$ such that $f(x') = y'$, contradicting bijectivity. 
$\square$

<a name="ex4.3"></a>
## Exercise 4.3.
<a name="lem4.3.A"></a>
<b>Lemma 4.3.A.</b> Let $\Z[x]$ denote the the set of all polynomials of integer coefficients. Then $\Z[x]$ is countably infinite.

<i>Proof.</i> Note that $\Z$ is countable, as the map $f : \boldsymbol{N} \to \Z$ defined by:

$$
\begin{align*}
f(n) =
\begin{cases}
k, &\text{if $n = 2k$ for some $k \in \boldsymbol{N}$} \\
-k, &\text{if $n = 2k + 1$ for some $k \in \boldsymbol{N}$}
\end{cases}
\end{align*}
$$

is a bijection. We may now define a map $g : \Z[x] \to \boldsymbol{N}$ defined by:

$$
\begin{align*}
g(a_nx^n + \cdots + a_1x + a_0) = 2^{f^{-1}(a_0)}3^{f^{-1}(a_1)}\cdots p_{n+1}^{f^{-1}(a_n)}
\end{align*}
$$

where $p_n$ is the $n^\text{th}$ smallest prime number. Fundamental Theorem of Arithmetic then tells us that $g$ is injective (in fact it's bijective, but we do not need it here). Thus, $\Z[x]$ is countable, and clearly it is infinite. 
$\blacksquare$

<a name="lem4.3.B"></a>
<b>Lemma 4.3.B.</b> $\Z[x]$ is well-orderable.

<i>Proof.</i> We define $\prec \; \subseteq \Z[x] \times \Z[x]$ as follows: Given $a_nx^n + \cdots + a_1x + a_0,b_mx^m + \cdots + b_1x + b_0 \in \Z[x]$, we define:

$$
\begin{gather*}
a_nx^n + \cdots + a_1x + a_0 \prec b_mx^m + \cdots + b_1x + b_0 \\
\updownarrow \\
n < m \text{ or } (n = m \wedge a_n < b_m)
\end{gather*}
$$

It's easy to check that $\prec$ defines a well-order, with the zero polynomial being the minimal element. 
$\blacksquare$

<i>Solution.</i> Let $X$ be the set of all algebraic reals. Define $h : X \to \boldsymbol{N} \times \Z[x]$ by $h(a) = (k,p(x))$, where $p(x)$ is the $\prec$-least polynomial (as in <a href="#lem4.3.B">Lemma 4.3.B</a>), and $a$ is the $(k + 1)^\text{th}$ smallest root of $p(x)$. Then $h$ is clearly injective, and since $\Z[x]$ is countable by <a href="#lem4.3.A">Lemma 4.3.A</a>, $\boldsymbol{N} \times \Z[x]$ is also countable, so $X$ must be countable. 
$\square$

<b>Remark.</b>. If we assume $\AC$, then this exercise becomes far easier as countable union of countable sets is countable (which makes proving <a href="#lem4.3.A">Lemma 4.3.A</a> slightly easier), and every set is well-orderable (trivialising <a href="#lem4.3.B">Lemma 4.3.B</a>).

<a name="ex4.4"></a>
## Exercise 4.4.
<i>Solution.</i> Using a choiceless bijection we may work with the Baire space $\N = \omega^\omega$ in place of $\R$, and $S \subseteq \N$. Let $S = \lbrace f_i : i \in \omega\rbrace$. Define:

$$
\begin{align*}
X = \prod_{i \in \omega} \lbrace f_i(i)+1,f_i(i)+2\rbrace
\end{align*}
$$

Clearly $X \cap S = \emptyset$, for if $f \in X$ then for any $i \in \omega$, $f(i) > f_i(i)$. Thus, $X \subseteq \N - S$. Clearly $\vert X\vert  = 2^{\aleph_0} = \mathfrak{c}$, so $\vert \N - S\vert  \geq \mathfrak{c}$. On the other hand, $\vert \N - S\vert  \leq \vert \N\vert  = \mathfrak{c}$. 
$\square$

<a name="ex4.5"></a>
## Exercise 4.5.
<a name="ex4.5(i)"></a>
### Exercise 4.5(i).
<i>Solution.</i> This follows from <a href="#ex4.4">Exercise 4.4</a> and that $\Q$ is countable. 
$\square$

<a name="ex4.5(ii)"></a>
### Exercise 4.5(ii).
<i>Solution.</i> This follows from <a href="#ex4.4">Exercise 4.4</a> and that by <a href="#ex4.3">Exercise 4.3</a>, the set of all algebraic numbers is countable. 
$\square$

<a name="ex4.6"></a>
## Exercise 4.6.
<a name="lem4.6.A"></a>
<b>Lemma 4.6.A.</b> Every open set of reals is a countable union of disjoint open intervals.

<b>Note.</b>. For this exercise, we use $(a,b)$ to denote the open interval, and $\c{a,b}$ to denote ordered pair.

<i>Proof.</i> Let $U \subseteq \R$ be open. First observe that for $x \in U$, there exists a maximal open interval $U_x \subseteq U$ containing $x$ - this is because all open sets are generated by open intervals as basic sets, and if $U_x,U_x'$ are open intervals containing $x$, then $U_x \cup U_x'$ is also an open interval containing $x$.

For each $x \in U$, let $U_x \subseteq U$ be the maximal open interval that contains $x$. Let $\U := \lbrace U_x : x \in U\rbrace$ be the set of all maximal open intervals in $U$. Then they must be disjoint, as if $U_x \cap U_y \neq \emptyset$ then $U_x \cup U_y$ is a larger open interval. Clearly $\bigcup \U = U$, so it remains to show that $\U$ is countable.

Write $\U = \lbrace U_i : i \in I\rbrace$, where $I$ is an index set and $U_i \cap U_j = \emptyset$ for $i \neq j$. For each $i$, there exists a rational number $q_i \in U_i$. Since the $U_i$'s are disjoint, the map $U_i \mapsto q_i$ is one-to-one. Thus $I$ is countable as desired. Note that the map $U_i \mapsto q_i$ does not require the Axiom of Choice, as there is a choiceless algorithm to obtain a rational number $q_i \in U_i$. 
$\blacksquare$

<i>Solution.</i> Let $X := \lbrace \c{a,b} \in \R \times \R : a < b\rbrace$, and let $\mathcal{T}$ denote the set of all open subsets of $\R$. let $\mathcal{B}$ be the set of all open intervals of $\R$. Consider the one-to-one map $f$ of $X$ onto $\mathcal{B}$ defined by $f(\c{a,b}) = (a,b)$. Clearly $\vert X\vert  = \mathfrak{c}$, so $\vert \mathcal{B}\vert  = \mathfrak{c}$.

Now define $g : [\mathcal{B}]^\omega \to \mathcal{T}$ by:

$$
\begin{align*}
g(\lbrace B_i : i \in \omega\rbrace) = \bigcup_{i \in \omega}
\end{align*}
$$

By <a href="#lem4.6.A">Lemma 4.6.A</a>, $g$ is onto. Thus:

$$
\begin{align*}
\vert \mathcal{T}\vert  \leq \vert [\mathcal{B}]^\omega\vert  = \vert \mathcal{B}\vert ^{\aleph_0} = \mathfrak{c}^{\aleph_0} = \mathfrak{c}
\end{align*}
$$

On the other hand, we have$\vert \mathcal{T}\vert  \geq \vert \mathcal{B}\vert  = \mathfrak{c}$, so equality holds. 
$\square$

<a name="ex4.7"></a>
## Exercise 4.7.
<i>Solution.</i> We first show that the Cantor set $\C$ is closed. Let $x \in \R$, and write $x = \sum_{n=1}^\infty \frac{a_n}{3^n}$ where $a_n \in \lbrace 0,1,2\rbrace$. Suppose on the contrary that $a_N = 1$ for some $N$, and it's not the case that $a_n = 0$ for all $n > N$ or $a_n = 2$ for all $n > N$. We write:

$$
\begin{align*}
x = \sum_{n=0}^{N-1} \frac{a_n}{3^n} + \frac{1}{3^N} + s = \sum_{n=0}^{N-1} \frac{a_n}{3^n} + \frac{2}{3^N} - t
\end{align*}
$$

where $0 < s,t < \frac{1}{3^N}$. Now let $y = \sum_{n=1}^\infty \frac{b_n}{3^n} \in \C$. If $y \leq x$, then it can't be that $y > \sum_{n=1}^{N-1} \frac{a_n}{3^n} + \frac{1}{3^N}$, for otherwise we must have $b_N = 1$. Thus $y \leq \sum_{n=1}^{N-1} \frac{a_n}{3^n} + \frac{1}{3^N}$, hence $x - y \geq s$. By similar reasoning, if $y \geq x$ then $y - x \geq t$. Thus, $x$ is not a limit point of $\C$, so all points not in $\C$ are not limit points.

We now show that $\C$ has no isolated points. Fix $y = \sum_{n=1}^\infty \frac{b_n}{3^n} \in \C$. For any $\epsilon > 0$, let $N$ be large enough so that $\frac{2}{3^N} < \epsilon$. If $b_n = 2$ for some $n \geq N$, then $z := y - \frac{2}{3^n} \in \C$ and $\vert y - z\vert  < \epsilon$. Otherwise, $z := y + \frac{2}{3^N} \in \C$ and $\vert y - z\vert  < \epsilon$. Thus $y$ is not isolated. 
$\square$

<a name="ex4.8"></a>
## Exercise 4.8.
<i>Solution.</i> The proof of Theorem 4.5. may be repeated. We provide a similar proof that can also serve as an alternative proof to Theorem 4.5.

We shall define a one-to-one function $f$ with $\dom(f) = 2^{<\omega}$ and $f(s)$ is an open set for all $s \in \omega^{<\omega}$, with $f(s) \cap P \neq \emptyset$. We define this inductively.

Let $f(\emptyset) = (a,b)$. Suppose for all $s \in \omega^{<\omega}$ with $\length(s) = n$, $f(s)$ are defined such that $f(s) \cap P \neq \emptyset$, and $f(s_1) \cap f(s_2) = \emptyset$ for $s_1 \neq s_2$ of length $n$. Say $x \in f(s) \cap P$, and let $(c,d) \subseteq f(s)$ such that $x \in (c,d)$. Since $P$ is perfect, $x$ is a limit point so there exists $x_0,x_1 \in P \cap (c,d)$ such that $x_0 \neq x_1$ and $\vert x_0 - x\vert  > 0$, $\vert x_1 - x\vert  > 0$. We define $f(s^\frown(0)),f(s^\frown(1))$ as the open sets containing $x_0$ and $x_1$ respectively such that $x,x_1 \notin f(s^\frown(0))$ and $x,x_0 \notin f(s^\frown(1))$ (clearly such open sets exist). Note that if $s' \neq s$ and $\length(s') = n$, then since $f(s^\frown(i)) \subseteq f(s)$ we have $f(s^\frown(i)) \cap f(s'^\frown(i')) = \emptyset$ for $i,i' \in \lbrace 0,1\rbrace$.

Now for each $l \in 2^\omega$, let $X_l := \bigcap_{n=0}^\infty f(l\restrictedto n)$. $X_l$ is a nested intersection of bounded open sets, so it contains a single point $x_l \in X_l$. Then $\lbrace x_l : l \in 2^\omega\rbrace \subseteq P \cap (a,b)$, so $\vert P \cap (a,b)\vert  = \mathfrak{c}$. 
$\square$

<a name="ex4.9"></a>
## Exercise 4.9.
<i>Solution.</i> Let $x \in P_2 - P_1$. Since $x \notin P_1$ and $P_1$ is perfect, $x$ is isolated from $P_1$, i.e. there exists an open neighbourhood $(a,b) \ni x$ such that $(a,b) \cap P_1 = \emptyset$. Then $\emptyset \neq P_2 \cap (a,b) \subseteq P_2 - P_1$, and by <a href="#ex4.8">Exercise 4.8</a> $\vert P_2 \cap (a,b)\vert  = \mathfrak{c}$. Thus $\vert P_2 - P_1\vert  = \mathfrak{c}$. 
$\square$

<a name="ex4.10"></a>
## Exercise 4.10.
<i>Solution.</i> Since $P$ is closed, $P^\ast  \subseteq P$. On the other hand, for every $x \in P$ is a limit point, and hence a condensation point by <a href="#ex4.8">Exercise 4.8</a>, so $P \subseteq P^\ast $. 
$\square$

<a name="ex4.11"></a>
## Exercise 4.11.
<i>Solution.</i> Clearly if $P \subseteq F$ then $P^\ast  \subseteq F^\ast $, and $P = P^\ast $. 
$\square$

<a name="ex4.12"></a>
## Exercise 4.12.
<i>Solution.</i> As in the hint, for each $a \in F^\ast $, since every neighbourhood of $a$ has uncountably many points and $\vert F - P\vert  \leq \aleph_0$, must have that $a$ is a limit point of $P$. Since $P$ is closed, $a \in P$. 
$\square$

<a name="ex4.13"></a>
## Exercise 4.13.
<i>Solution.</i> This is an immediate consequence of <a href="#ex4.12">Exercise 4.12</a>. 
$\square$

<a name="ex4.14"></a>
## Exercise 4.14.
<i>Solution.</i> Note that we require Axiom of Choice to prove the Baire Category Theorem.

Suppose $\Q = \bigcap_{n=0}^\infty U_n$, where each $U_n$ is open. Since $\Q$ is dense, so is each $U_n$. Thus $\R - \Q = \bigcup_{n=0}^\infty (\R - U_n)$, where each $\R - U_n$ is closed nowhere dense. Clearly $\Q = \bigcup_{q \in \Q} \lbrace q\rbrace$ is also a countable union of closed nowhere dense sets, therefore $\R$ is a countable union of closed nowhere dense sets. This contradicts the Baire Category Theorem, which implies that $\R$ is not a countable union of closed nowhere dense sets. 
$\square$

<a name="ex4.15"></a>
## Exercise 4.15.
<i>Solution.</i> Let $X$ be a Polish space, and let $D$ denote the dense subset of $X$. We shall show that the function $F : X \to [0,1]^\omega$ in the hint (w.r.t. $D$) is one-to-one, and a homeomorphism to its image (under the subspace topology).

To see that $F$ is one-one, let $x,y \in X$ and suppose $x \neq y$. Let $d(x,y) = \delta$. Let $x_n \in B_{\frac{\delta}{3}}(x)$ (possible by denseness). Then $d(x,x_n) < \frac{\delta}{3}$ but $d(y,x_n) \geq d(y,x) - d(x,x_n) > \frac{2\delta}{3}$, so $F(x) \neq F(y)$.

Let $U \subseteq \lbrace 0,1\rbrace^\omega$ be open, and we wish to show that $F_{-1}(U)$ is open. Let $x \in F_{-1}(U)$, and let $\epsilon_0,\dots,\epsilon_n > 0$ be such that $\prod_{i<n} B_{\epsilon_i}(F(x)(i)) \times [0,1]^\omega \subseteq U$. Let $V := \bigcap_{i<n} B_{\epsilon_i}(x)$, which is open. If $y \in V$, then for $i < n$ we have:

$$
\begin{align*}
\vert d(y,x_i) - d(x,x_i)\vert  \leq d(y,x) < \epsilon_i \implies F(y)(i) \in B_{\epsilon_i}(F(x)(i))
\end{align*}
$$

Thus $F(y) \in U$, so $x \in V \subseteq F_{-1}(U)$. Hence $F_{-1}(U)$ is open.

Now let $V \subseteq X$ be open, and we wish to show that $F"(V) \subseteq F"(X)$ is open under the subspace topology. Let $f \in F"(V)$, and let $x \in V$ such that $F(x) = f$. Let $\epsilon > 0$ such that $B_\epsilon(x) \subseteq V$. WLOG suppose $x_0 \in B_{\frac{\epsilon}{3}}(x)$. Then we see that $f \in (B_{\frac{\epsilon}{3}}(f(0)) \times [0,1]^\omega) \cap F"(X) \subseteq F"(X)$, for if $y \in X$ is such that $F(y) \in B_\epsilon(f(0)) \times [0,1]^\omega$, then:

$$
\begin{align*}
d(x,y) \leq d(x,x_0) + d(x_0,y) \leq 2d(x,x_0) + \frac{\epsilon}{3} < \epsilon
\end{align*}
$$

Thus $y \in B_\epsilon(x) \subseteq V$, so $F"(V)$ is open.

It remains to show that $F"(X)$ is a $G_\delta$ subspace of $[0,1]^\omega$. We shall show that:

$$
\begin{align*}
F"(X) = \bigcap_{n=1}^\infty \bigcup_{x \in X} B_{\frac{1}{n}}(f(x)) =: Y
\end{align*}
$$

Clearly $F"(X) \subseteq Y$. Conversely, we see that $y \in Y$ precisely if $(\forall n > 0)(\exists x \in X) \, d(f(x),y) < \frac{1}{n}$. In other words, $y$ is in the closure of $F"(X)$. But since $F$ is a homeomorphism and $X$ is complete, $F"(X)$ is closed and therefore $y \in F"(X)$. 
$\square$