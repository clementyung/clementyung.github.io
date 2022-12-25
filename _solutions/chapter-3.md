---
title: "3) Cardinal Numbers"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-3
excerpt: ""
---

{% include commands.html %}

<a name="ex3.1"></a>
## Exercise 3.1.
<a name="ex3.1(i)"></a>
### Exercise 3.1(i).
<i>Solution.</i> Let $X$ be a set with finite cardinality $\mod{X} = n$. We induct on $n$. If $n = 0$, then the only subset is $\emptyset$, which is finite. If $\mod{X} = n + 1$, then let $Y \subseteq X$. We consider two cases.
<ol>
<li> If $Y = X$, then since $X$ is finite, so is $Y$.</li>

<li> If $Y \subsetneq X$, then let $x_0 \in X - Y$. Then $Y \subseteq X - \lbrace x_0\rbrace$. By [Lemma 1.12.A](https://clementyung.github.io/jech-solutions/chapter-1#lem1.12.A), $\mod{X - \lbrace x_0\rbrace} = n$, so by induction hypothesis $Y$ is also finite.</li>
</ol> 
$\square$

<a name="ex3.1(ii)"></a>
### Exercise 3.1(ii).
<i>Solution.</i> First assume $A \cap B = \emptyset$. Suppose $\mod{A} = m$ and $\mod{B} = n$. First suppose $A \cap B = \emptyset$. Let $f : A \to m$ and $g : B \to n$ be bijections. Then define $h : A \sqcup B \to m + n$ by:

$$
\begin{align*}
h(x) :=
\begin{cases}
f(x), &\text{if $x \in A$} \\
g(x) + n, &\text{if $x \in B$}
\end{cases}
\end{align*}
$$

This is well-defined as $A \cap B = \emptyset$. It's easy to see that $h$ is a bijection.

For the general case, we observe that $A \cup B = A \cup (B - A)$, $A \cap (B - A) = \emptyset$, and $B - A \subseteq B$ so it is also finite by [Exercise 3.1(i)](#ex3.1(i)). 
$\square$

<a name="ex3.1(iii)"></a>
### Exercise 3.1(iii).
<i>Solution.</i> This follows from Lemma 3.3, which asserts that if $\mod{X} = n$ then $\mod{P(X)} = 2^n$, which is finite. 
$\square$

<a name="ex3.1(iv)"></a>
### Exercise 3.1(iv).
<i>Solution.</i> Let $X$ be a finite set and let $f : X \to Y$ be a mapping to some (not necessarily finite) set $Y$. Then, considering $f : X \to f"(X)$ (by adjusting the codomain), we obtain a bijection between $X$ and $f"(X)$. If $g : X \to n$ is a bijection, then $g \circ f^{-1} : f"(X) \to n$ is also a bijection, so $f"(X)$ is finite. 
$\square$

<a name="ex3.2"></a>
## Exercise 3.2.
<a name="ex3.2(i)"></a>
### Exercise 3.2(i).
<i>Solution.</i> Note that a set is at most countable iff $\mod{X} \leq \mod{\omega}$, iff there exists an injective mapping $X \to \omega$.

Let $X$ be a countable set, and let $Y \subseteq X$. Consider the inclusion map $i : Y \to X$, which is of course injective. Since $X$ is countably, there exists a bijective map $f : X \to \omega$. Then $f \circ i : Y \to \omega$ is an injective mapping, so $Y$ is at most countable. 
$\square$

<a name="ex3.2(ii)"></a>
### Exercise 3.2(ii).
<i>Solution.</i> Suppose $X_1,\dots,X_n$ are countable sets. Let $X := \bigcup_{i=1}^n X_i$. Since $X_1 \subseteq X$, $\mod{X_1} \leq \mod{X}$ so $\mod{X} \geq \aleph_0$. To finish the proof, we need to find an injective mapping $X \to \omega$, so $\mod{X} \leq \aleph_0$.

For each $i$, let $f_i : X_i \to \boldsymbol{N}$ be a bijection. Define $f : X \to \omega$ by stipulating that:

$$
\begin{align*}
f(x) = p_i^{f_i(x)}, \;\;\text{if $x \in X_i - \bigcup_{j < i} X_j$}
\end{align*}
$$

where $p_i$ denotes the $i^\text{th}$ smallest prime number. It's easy to see that, by fundamental theorem of arithmetic, $f$ is injective. 
$\square$

<a name="ex3.2(iii)"></a>
### Exercise 3.2(iii).
<i>Solution.</i> Let $X,Y$ be sets, $X$ countable, and let $f : X \to Y$ be a mapping. Let $g : \omega \to X$ be a bijection. Then $f \circ g : \omega \to Y$. Now define $h : Y \to \omega$ by stipulating that:

$$
\begin{align*}
h(y) := \min\lbrace n \in \omega : (g \circ f)(n) = y\rbrace
\end{align*}
$$

Then $h$ is well-defined as $\omega$ is well-ordered, and clearly $h$ is injective. Thus there exists an injective map from $Y$ to $\omega$, so it is at most countable. 
$\square$

<a name="ex3.3"></a>
## Exercise 3.3.
<i>Solution.</i> We shall show that the $f : \boldsymbol{N} \times \boldsymbol{N} \to \boldsymbol{N}$ in the hint is bijective.

<u>Injective:</u> Suppose $f(m_1,n_1) = f(m_2,n_2)$, so $2^{m_1}(2n_1 + 1) - 1 = 2^{m_2}(2n_2 + 1) - 1 \implies 2^{m_1}(2n_1 + 1) = 2^{m_2}(2n_2 + 1)$. Now the $2^{n_i}$'s are odd, so $\nu_2(2^{m_i}(2n_i + 1)) = m_i$ (the \hyperlink{https://en.wikipedia.org/wiki/P-adic\_order}{$p$-adic order}). By Fundamental Theorem of Arithmetic, we have that $m_1 = m_2$. This implies that $2n_1 + 1 = 2n_2 + 1$, which easily gives $n_1 = n_2$. Thus $(m_1,n_1) = (m_2,n_2)$.

<u>Surjective:</u> For any $N \in \boldsymbol{N}$, $N + 1$ is a positive integer, and by the Fundamental Theorem of Arithmetic we may write $N + 1 = 2^mN_2$ for some $m \in \boldsymbol{N}$ and $N_2 \in \boldsymbol{N}$, where $N_2$ is an odd integer. Then $N_2 = 2n + 1$ for some $n \in \boldsymbol{N}$, so $f(m,n) = 2^m(2n + 1) - 1 = N$. 
$\square$

<a name="ex3.4"></a>
## Exercise 3.4.
<a name="ex3.4(i)"></a>
### Exercise 3.4(i).
<i>Solution.</i> Let $\boldsymbol{N}^{<\omega}$ denote the set of finite sequences in $\boldsymbol{N}$. Define a map $f : \boldsymbol{N}^{<\omega} \to \boldsymbol{N}$ as follows: For each $s = \c{s(0),\dots,s(n-1)} \in \boldsymbol{N}^{<\omega}$, let:

$$
\begin{align*}
f(s) = p_1^{s(0)+1}\cdots p_n^{s(n-1)+1}
\end{align*}
$$

where $p_k$ is the $k^\text{th}$ smallest prime number. The injectivity of this map follows from the Fundamental Theorem of Arithmetic, so $\mod{\boldsymbol{N}^{<\omega}} \leq \mod{\boldsymbol{N}}$. On the other hand, the map $n \mapsto \c{n}$ is clearly an injective map $\boldsymbol{N} \to \boldsymbol{N}^{<\omega}$, so $\mod{\boldsymbol{N}^{<\omega}} \geq \mod{\boldsymbol{N}}$. By Cantor-Bernstein Theorem (Theorem 3.2), we have that $\mod{\boldsymbol{N}^{<\omega}} = \mod{\boldsymbol{N}}$, so $\boldsymbol{N}^{<\omega}$ is countably infinite. 
$\square$

<a name="ex3.4(ii)"></a>
### Exercise 3.4(ii).
<i>Solution.</i> WLOG we may show the statement for finite subsets of $\boldsymbol{N}$, the general case follows from establishing a bijection between $\boldsymbol{N}$ and the arbitrary countable set.

Clearly $\mod{\boldsymbol{N}} \leq \mod{[\boldsymbol{N}]^{<\omega}}$ by the injective map $n \mapsto \lbrace n\rbrace$. On the other hand, for each $\lbrace a_0,\dots,a_{n-1}\rbrace \in [\boldsymbol{N}]^{<\omega}$, where $a_0 < \cdots < a_{n-1}$, define the map from $[\boldsymbol{N}]^{<\omega}$ to $\boldsymbol{N}^{<\omega}$ by:

$$
\begin{align*}
\lbrace a_0,\dots,a_{n-1}\rbrace \mapsto \c{a_0,\dots,a_{n-1}}
\end{align*}
$$

Clearly this map is injective, so $\mod{[\boldsymbol{N}]^{<\omega}} \leq \mod{\boldsymbol{N}^{<\omega}}$. By Exercise [Exercise 3.4(i)](#ex3.4(i)), we have that $\mod{[\boldsymbol{N}]^{<\omega}} = \mod{\boldsymbol{N}}$, so $[\boldsymbol{N}]^{<\omega}$ is countable. 
$\square$

<a name="ex3.5"></a>
## Exercise 3.5.
<a name="lem3.5.A"></a>
<b>Lemma 3.5.A.</b> For all ordinals $\alpha$, we have $\alpha \leq \omega^\alpha$.

<i>Proof.</i> We induct on $\alpha$. For $\alpha = 0$ we have $\omega^0 = 1$. If $\beta \leq \omega^\beta$, then:

$$
\begin{align*}
\beta + 1 \leq \omega^\beta + 1 \leq \omega^\beta + \omega^\beta = \omega^\beta \cdot 2 \leq \omega^\beta \cdot \omega = \omega^{\beta+1}
\end{align*}
$$

If $\alpha$ is a limit ordinal, then:

$$
\begin{align*}
\alpha = \lim_{\beta \to \alpha} \beta \leq \lim_{\beta \to \alpha} \omega^\beta = \omega^\alpha
\end{align*}
$$
 
$\blacksquare$

<i>Solution.</i> For the first part, we induct on $\alpha$. For $\alpha = 0$, clearly $\Gamma(0 \times 0) = 0 \leq 1 = \omega^0$. If $\alpha > 0$ is a limit ordinal, then by continuity we have:

$$
\begin{align*}
\Gamma(\alpha \times \alpha) = \bigcup_{\beta<\alpha} \Gamma(\beta \times \beta) \leq \bigcup_{\beta<\alpha} \omega^\beta = \omega^\alpha
\end{align*}
$$

Now suppose $\alpha = \beta + 1$. Since $(\gamma,\delta) \in \beta \times \beta$ iff $(\gamma,\delta) < (0,\beta)$ (so $\Gamma(0,\beta) \leq \omega^\beta$), we have that:

$$
\begin{align*}
\Gamma(\alpha \times \alpha) - \Gamma(\beta \times \beta) = \underbrace{\lbrace (\gamma,\beta) : \gamma < \beta\rbrace}_{\text{order type $\beta$}} \cup \underbrace{\lbrace (\beta,\gamma) : \gamma \leq \beta\rbrace}_{\text{order type $\beta + 1$}}
\end{align*}
$$

Thus, this is of order type $\beta\cdot 2 + 1$, so by [Lemma 3.5.A](#lem3.5.A):

$$
\begin{align*}
\Gamma(\alpha \times \alpha) &= \Gamma(\beta + \beta) + \beta \cdot 2 + 1 \\
&\leq \omega^\beta + \beta + \beta + 1 \\
&\leq \omega^\beta + \omega^\beta + \omega^\beta + \omega^\beta \\
&= \omega^\beta \cdot 4 \\
&\leq \omega^\beta \cdot \omega \\
&= \omega^{\beta+1}
\end{align*}
$$

The second part of the exercise is false. However, it is true that the fixed points of $\gamma(\alpha) = \Gamma(\alpha \times \alpha)$ are precisely the <i>multiplicatively indecomposable</i> ordinals. See Exercise I.11.7 of \cite{kunen}. The notion of indecomposable ordinals introduced in [Exercise 2.13](https://clementyung.github.io/jech-solutions/chapter-2#ex2.13) is also called <i>additively indecomposable</i>.

We shall show that $\Gamma(\omega^2 \times \omega^2) > \omega^2$. To do this, it suffices to show that $\Gamma((\omega + \omega) \times (\omega + \omega)) \geq \omega^2$. For each $n \in \omega$, the set:

$$
\begin{align*}
\lbrace (\alpha, \omega + n) : \alpha < \omega + n\rbrace \cup \lbrace (\omega + n,\alpha) : \alpha \leq \omega + n\rbrace
\end{align*}
$$

is of order type  $(\omega + n) + (\omega + n + 1) = \omega \cdot 2 + n + 1$. Thus, it's easy to prove inductively that for each $n \in \omega$, we have $\Gamma((\omega + n) \times (\omega + n)) \geq \omega \cdot (2n + 1)$. Therefore:

$$
\begin{align*}
\Gamma((\omega + \omega) \times (\omega + \omega)) \geq \lim_{n \in \omega} \omega \cdot (2n + 1) = \omega^2
\end{align*}
$$
 
$\square$

<a name="ex3.6"></a>
## Exercise 3.6.
<a name="lem3.6.A"></a>
<b>Lemma 3.6.A.</b> Let $\alpha < \omega_\beta$ be an ordinal. Let $\alpha^{<\omega}$ be the set of all finite sequences of ordinals below $\alpha$. Then $\mod{\alpha^{<\omega}} < \kappa$.

<i>Proof.</i> Let $f : \alpha \to \mod{\alpha}$ be a bijection. By Theorem 3.5 we know that $\Gamma(\mod{\alpha} \times \mod{\alpha}) = \mod{\alpha}$. Thus, we obtain a choiceless bijection $g := f^{-1} \circ \Gamma \circ (f,f) : \alpha \times \alpha \to \alpha$. Let $g_2 := g$, and inductively define $g_n : \alpha^n \to \alpha$ by $g_n := (g_{n-1},g)$. With this, we may define $h : \alpha^{<\omega} \to \alpha \times \omega$ by:

$$
\begin{align*}
h(s) := (g_{\length(s)}(s),\length(s))
\end{align*}
$$

Then clearly $h$ is one-to-one, so we have:

$$
\begin{align*}
\mod{\alpha^{<\omega}} < \mod{\alpha \times }\omega\mod{ = }\alpha\mod{ \cdot \aleph_0 \leq }\alpha\mod{ < \omega_\beta
\end{align*}
$$
 
$\blacksquare$

<i>Solution.</i> We require the Axiom of Choice in this solution.

We first define a function $\height$ on finite sequences of ordinals, in which if $f$ is such a sequence then:

$$
\begin{align*}
\height(s) := \max\lbrace \length(s),\max\lbrace s(i) : i < \length(s)\rbrace\rbrace
\end{align*}
$$

We shall define an ordering as follows: Given two finite sequences of ordinals $s$ and $t$, we say that $s < t$ iff one of the following holds:
<ol>
<li> $\height(s) < \height(t)$.</li>

<li> $\height(s) = \height(t)$ and $\length(s) < \length(t)$.</li>

<li> $\height(s) = \height(t)$, $\length(s) = \length(t)$ and there exists some $k < \length(s)$ such that $s(k) < t(k)$, and $s(i) = t(i)$ for all $i < k$.</li>
</ol>
As an example, an initial segment of this ordering is as follows:

$$
\begin{gather*}
\emptyset < (0) < (1) < (2) < (0,0) < (0,1) < (0,2) < (1,0) < (1,1) < (1,2) \\
< (2,0) < (2,1) < (2,2) < (3) < (0,3) < (1,3) < (2,3) < (3,3) < (0,0,0) < \dots
\end{gather*}
$$

One can check that $<$ is a linear order (transitivity is the most tedious to check, but it can be done by considering cases). We first show that $<$ is a well-order. Let $X \subseteq \boldsymbol{\mathrm{ORD}}^{<\omega}$. Let $Y \subseteq X$ be the non-empty subset of all elements of $X$ of minimal height, then let $Z \subseteq Y$ be the non-empty subset of all elements of $Y$ of minimal length. Thus, all elements in $Z$ have equal height and length, and $(\forall z \in Z)(\forall x \in X - Z) \, z < x$. Thus, it suffices to show that $Z$ has a $<$-minimal element.

Suppose all elements of $Z$ has length $n$. For each $i < n$, let:
<ol>
<li> $Z_0 := \lbrace z \in Z : z(0) = \min\lbrace z'(0) : z' \in Z\rbrace\rbrace$.</li>

<li> $Z_i := \lbrace z \in Z_{i-1} : z(i) = \min\lbrace z'(i) : z' \in Z\rbrace\rbrace$.</li>
</ol>
By well-ordering of ordinals all of $Z_i$'s are non-empty. Let $z \in Z_{n-1}$. Then $z$ is the minimal element in $Z$ - otherwise, if $z' < z$, then since $\height(z) = \height(z')$ and $\length(z) = \length(z')$, we have that $z'(k) < z(k)$ for some $k < n$, and $z'(i) = z(i)$ for $i < k$. Since $z(i)$ is minimal for all $i$, we have that $z'(i)$ is minimal for all $i < k$, therefore $z' \in Z_{k-1}$. But $z \in Z_k$ and $z'(k) < z(k)$, contradicting minimality of $z(k)$.

Thus, we may denote $\Lambda(s)$ as the order type of the set of all finite sequences below $s$ under $<$. Let $\Lambda(\alpha^{<\omega}) := \Lambda((\alpha))$. $\Lambda(\omega_\alpha^{<\omega}) = \omega_\alpha$ for all $\alpha$. We first observe that $(\beta) < (\omega_\alpha)$ for all $\beta < \omega_\alpha$, so $\Lambda(\omega_\alpha^{<\omega}) \geq \omega_\alpha$. Now suppose for a contradiction that $\Lambda(\omega_\alpha^{<\omega}) > \omega_\alpha$. Let $s$ be the $<$-minimal sequence such that $\Lambda(s) = \omega_\alpha$. Let $\delta < \omega_\alpha$ such that $\delta > s(i)$ for all $i < \length(s)$. Then $\omega_\alpha \subseteq \Lambda(\delta^{<\omega})$. Now observe that $\Lambda(\delta^{<\omega}) \subseteq \delta^{<\omega}$, so $}\delta^{<\omega}\mod{ \geq \aleph_\alpha$. This contradicts [Lemma 3.6.A](#lem3.6.A). 
$\square$

<a name="ex3.7"></a>
## Exercise 3.7.
<i>Solution.</i> Let $f : \omega_\alpha \to B$ be an onto function. Define $g : B \to \omega_\alpha$ by stipulating that for $x \in B$, $g(x) = \min\lbrace f_{-1}(\lbrace x\rbrace)\rbrace$. This is well defined as for $x \neq y$, $f_{-1}(\lbrace x\rbrace)$ and $f_{-1}(\lbrace y\rbrace)$ are disjoint. They are also non-empty as $f$ is onto. Then $g$ is a one-to-one function on $B$ into $\omega_\alpha$, so $}B\mod{ \leq }\omega_\alpha\mod{ = \aleph_\alpha$. 
$\square$

<a name="ex3.8"></a>
## Exercise 3.8.
<i>Solution.</i> We note that by restricting the well-order in [Exercise 3.6](#ex3.6) to finite sequences of $\omega_\alpha$, we obtain a choiceless well-order in $\omega_\alpha^{<\omega}$, along with the order type $\Lambda$. Then $\Lambda^{-1}(\omega_\alpha) = \omega_\alpha^{<\omega}$, so $\omega_\alpha^{<\omega}$ is a projection of $\omega_\alpha$. Clearly the set of all finite subsets of $\omega_\alpha$ is a projection of $\omega_\alpha^{<\omega}$, so the set of all finite subsets of $\omega_\alpha$ is a projection of $\omega_\alpha$ itself. By [Exercise 3.7](#ex3.7), this set has cardinality $\leq \aleph_\alpha$. On the other hand, the map $\beta \mapsto \lbrace \beta\rbrace$ is a one-to-one function on $\omega_\alpha$ to this set, so it has cardinality $\geq \aleph_\alpha$. Thus equality follows. 
$\square$

<a name="ex3.9"></a>
## Exercise 3.9.
<i>Solution.</i> Consider the function $g$ in the hint. It suffices to show that the function $g$ defined in the hint is one-to-one. Suppose $X \neq Y$ and suppose $x \in X - Y$. If $f(a) = x$ where $a \in B$, when $a \in f_{-1}(X) - f_{-1}(Y)$, so $g(X) \neq g(Y)$. 
$\square$

<a name="ex3.10"></a>
## Exercise 3.10.
<i>Solution.</i> By the pairing function $\Gamma$ in Theorem 3.5 we have that $\omega_\alpha \times \omega_\alpha$ is a projection of $\omega_\alpha$, and therefore $P(\omega_\alpha \times \omega_\alpha)$ is a projection of $P(\omega_\alpha)$. Let $f$ be the function in the hint (and if $R$ is not a well-order, let $f(R) := 0$). We shall show that $\ran(f) = \omega_{\alpha+1}$.

<u>$\ran(f) \supseteq \omega_{\alpha+1</u>$:} Let $\beta < \omega_{\alpha+1}$. Then $}\beta\mod{ \leq \aleph_\alpha$, so there exists a one-to-one function $f : \beta \to \omega_\alpha$. Define a well-ordering $R \subseteq \omega_\alpha \times \omega_\alpha$ by:

$$
\begin{align*}
(\gamma,\delta) \in R \iff (\exists \xi < \beta)(\exists \zeta < \xi)(f(\zeta) = \gamma \wedge f(\xi) = \delta)
\end{align*}
$$

Then clearly $R$ is a well order of order type $\beta$.

<u>$\ran(f) \subseteq \omega_{\alpha+1</u>$:} Let $R$ be a well order and let $\beta = f(R)$. We may then define $g : \beta \to \omega_\alpha$ by having $g(\gamma) := \alpha_\gamma$, where $\alpha_\gamma$ is the $\gamma^\text{th}$ ordinal under the well order $R$. The well order of $R$ also implies that $g$ must be one-to-one, so $}\beta\mod{ \leq }\alpha\mod{ < \omega_{\alpha+1}$. Hence $\beta \in \omega_{\alpha+1}$. 
$\square$

<a name="ex3.11"></a>
## Exercise 3.11.
<i>Solution.</i> By Lemma 3.3, $\aleph_{\alpha+1} < 2^{\aleph_{\alpha+1}}$. By [Exercise 3.10](#ex3.10), $\omega_{\alpha+1}$is a projection of $P(\omega_\alpha)$, so by [Exercise 3.9](#ex3.9) we have that $}P(\omega_{\alpha+1})\mod{ \leq }P(P(\omega_\alpha))\mod{$, i.e. $2^{\aleph_{\alpha+1}} \leq 2^{2^{\aleph_\alpha}}$. Thus $\aleph_{\alpha+1} < 2^{2^{\aleph_\alpha}}$. 
$\square$

<a name="ex3.12"></a>
## Exercise 3.12.
<i>Solution.</i> There is a typo in the second statement: $\omega_\alpha$ is not the limit of $\c{\omega_\xi : \xi < \cf{\alpha}}$. Regardless, it's true that $\cf{\omega_\alpha} = \cf{\alpha}$. This follows from Lemma 3.7(ii) and $\omega_\alpha := \lim_{\xi\to\alpha} \omega_\xi$. 
$\square$

<a name="ex3.13"></a>
## Exercise 3.13.
<i>Solution.</i> We expand on the hint. Note that the mapping $f : \omega \times \alpha \to \omega_2$ is defined as:

$$
\begin{align*}
f(n,\beta) = \text{the $\beta^\text{th}$ element of $S_n$}
\end{align*}
$$

where if $\beta \geq \alpha_n$ then $f(n,\beta) := 0$. Now $}\omega \times \alpha\mod{ = \aleph_0 \cdot }\alpha\mod{ \leq \omega_1$, so $\alpha \times \omega$ is a projection of $\omega_1$. Composing these two maps implies that $\omega_2$ is a projection of $\omega_1$, a contradiction. 
$\square$

<a name="ex3.14"></a>
## Exercise 3.14.
<i>Solution.</i> If $S$ is D-infinite, let $f,X$ be as in the hint. We shall show that $i \neq j$ implies $x_i \neq x_j$ (so $\lbrace x_n : n < <\omega\rbrace$ is indeed a countably infinite subset). Suppose $x_i = x_j$ for some $i,j < \omega$. WLOG suppose $i \leq j$, and write $j = i + k$. Then $f^{(i+k)}(x_0) = f^{(i)}(x_0)$. Since $f$ is one-to-one, $x_0 = f^{(k)}(x_0)$. Since $f^{(k)}(x_0) \in S - X$ but $\ran(f) \subseteq X$, we must have $k = 0$. Thus $i = j$.

Conversely, suppose $S$ has a countable subset $X \subseteq S$. Let $f : X \to \omega$ be one-to-one and onto. We define $g : S \to S$ by:

$$
\begin{align*}
g(x) :=
\begin{cases}
x, &\text{if $x \in S - X$} \\
f^{-1}(f(x + 1)), &\text{if $x \in X$}
\end{cases}
\end{align*}
$$

Clearly $g$ is one-to-one. Furthermore, $\ran(g)$ is a proper subset of $S$ as $f^{-1}(0) \notin \ran(g)$. Thus $S$ is D-infinite. 
$\square$

<a name="ex3.15"></a>
## Exercise 3.15.
<a name="ex3.15(i)"></a>
### Exercise 3.15(i).
<i>Solution.</i> Suppose $A \cup B$ is D-infinite, so by [Exercise 3.14](#ex3.14) it contains a countable subset. Let $X \subseteq A \cup B$ be countable. Then $X = (X \cap A) \cup (X \cap B)$. By [Exercise 3.2(i)](#ex3.2(i)), $X \cap A$ and $X \cap B$ are at most countable. Since $A$ and $B$ are $D$-finite, they do not contain a countable subset. Thus, $X \cap A$ and $X \cap B$ are both finite. By [Exercise 3.1(ii)](#ex3.1(ii)), $X$ is finite, a contradiction.

Suppose $A \times B$ is D-infinite with $X \subseteq A \times B$ countable. Let:

$$
\begin{gather*}
X_A := \lbrace a \in A : (\exists b \in B) \, (a,b) \in X\rbrace \\
X_B := \lbrace b \in B : (\exists a \in A) \, (a,b) \in X\rbrace
\end{gather*}
$$

$X_A$ and $X_B$ are images under the mappings $(a,b) \mapsto a$ and $(a,b) \mapsto b$ of $X$ respectively, so by [Exercise 3.2(iii)](#ex3.2(iii)) they are both finite. But observe that $X \subseteq X_A \times X_B$, so by [Lemma 3.15(i).A](#lem3.15(i).A) and [Exercise 3.1(i)](#ex3.1(i)) $X$ is finite, a contradiction. 
$\square$

<a name="ex3.15(ii)"></a>
### Exercise 3.15(ii).
<i>Solution.</i> Let $A$ be a D-finite set and let $A'$ denote the set of all one-to-one sequences of elements of $A'$. Suppose $A'$ is D-infinite with $X \subseteq A'$ countable. Write $X = \lbrace s_i : i < \omega\rbrace$. Define $x_i \in A$ inductively as follows:
<ol>
<li> $x_0 := s_0(0)$.</li>

<li> $x_{n+1} := s_i(k)$, where $i$ is the least $i < \omega$ such that $\ran(s_i) \not\subseteq \lbrace x_j : j < i\rbrace$, and $k$ is the least $k < \length(s_i)$ such that $s_i(k) \notin \lbrace x_j : j < i\rbrace$.</li>
</ol>
If $x_n$ is well-defined for all $n$, then it forms a countable subset of $A$, a contradiction. To see that it is indeed well-defined, suppose not, so there exists a finite set $F$ and an $n$ such that for all $m \geq n$, $\ran(s_m) \subseteq F$. This implies that:

$$
\begin{align*}
\bigcup_{m < \omega} \ran(s_m) \subseteq \underbrace{F \cup \bigcup_{m < n} \ran(s_m)}_{\text{finite}}
\end{align*}
$$

Therefore $X \subseteq [F']^{<\omega}$ for some finite set $F'$. Thus, if $}F'\mod{ = N$, then since all sequences in $X$ are one-to-one, we have:

$$
\begin{align*}
X \subseteq \bigcup_{i \leq N} \prod_{j < i} F'
\end{align*}
$$

but RHS is finite by [Lemma 3.15(i).A](#lem3.15(i).A) and [Exercise 3.1(ii)](#ex3.1(ii)), a contradiction. 
$\square$

<a name="ex3.15(iii)"></a>
### Exercise 3.15(iii).
<i>Solution.</i> As in the hint, it suffices to show that $\lbrace X \subseteq A : }X\mod{ = n\rbrace$ is non-empty for each $n$, in which it's clear that they are pairwise unequal, so $P(P(A))$ is D-infinite.

We induct on $n$ that $S_n := \lbrace X \subseteq A : }X\mod{ = n\rbrace$ is non-empty. $S_0$ is non-empty as $\emptyset \in S_0$. If $S_n$ is non-empty, let $X \in S_n$. Since $X \subseteq A$ is finite and $A$ is infinite, we have $A - X \neq \emptyset$, so let $x \in A - X$. Then $}X \cup \lbrace x\rbrace| = n + 1$ by [Lemma 1.13.A](https://clementyung.github.io/jech-solutions/chapter-1#lem1.13.A), so $X \cup \lbrace x\rbrace \in S_{n+1}$, i.e. $S_{n+1}$ is non-empty. 
$\square$