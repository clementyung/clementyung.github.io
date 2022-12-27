---
title: "3) Cardinal Numbers"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-3
excerpt: ""
---

{% include commands.html %}

<body>
<a name="ex3.1"></a><br/>
<h2>Exercise 3.1.</h2>
<a name="ex3.1(i)"></a><br/>
<h3>Exercise 3.1(i).</h3>
A subset of a finite set is finite.<br/>
<br/>
<i>Solution.</i> Let $X$ be a set with finite cardinality $\vert X\vert  = n$. We induct on $n$. If $n = 0$, then the only subset is $\emptyset$, which is finite. If $\vert X\vert  = n + 1$, then let $Y \subseteq X$. We consider two cases.
<ol>
<li> If $Y = X$, then since $X$ is finite, so is $Y$.</li>
<li> If $Y \subsetneq X$, then let $x_0 \in X - Y$. Then $Y \subseteq X - \lbrace x_0\rbrace$. By <a name="#1#lem1.12.A">Lemma 1.12.A</a>, $\vert X - \lbrace x_0\rbrace\vert  = n$, so by induction hypothesis $Y$ is also finite.</li>
</ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex3.1(ii)"></a><br/>
<h3>Exercise 3.1(ii).</h3>
The union of a finite set of finite sets is finite.<br/>
<br/>
<i>Solution.</i> First assume $A \cap B = \emptyset$. Suppose $\vert A\vert  = m$ and $\vert B\vert  = n$. First suppose $A \cap B = \emptyset$. Let $f : A \to m$ and $g : B \to n$ be bijections. Then define $h : A \sqcup B \to m + n$ by:<br/>
$$
\begin{align*}<br/>
h(x) :=<br/>
\begin{cases}<br/>
f(x), &\text{if $x \in A$} \\<br/>
g(x) + n, &\text{if $x \in B$}<br/>
\end{cases}<br/>
\end{align*}$$
This is well-defined as $A \cap B = \emptyset$. It's easy to see that $h$ is a bijection.<br/>
<br/>
For the general case, we observe that $A \cup B = A \cup (B - A)$, $A \cap (B - A) = \emptyset$, and $B - A \subseteq B$ so it is also finite by <a href="#ex3.1(i)">Exercise 3.1(i)</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.1(iii)"></a><br/>
<h3>Exercise 3.1(iii).</h3>
The power set of a finite set is finite.<br/>
<br/>
<i>Solution.</i> This follows from Lemma 3.3, which asserts that if $\vert X\vert  = n$ then $\vert P(X)\vert  = 2^n$, which is finite.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.1(iv)"></a><br/>
<h3>Exercise 3.1(iv).</h3>
The image of a finite set (under a mapping) is finite.<br/>
<br/>
<i>Solution.</i> Let $X$ be a finite set and let $f : X \to Y$ be a mapping to some (not necessarily finite) set $Y$. Then, considering $f : X \to f"(X)$ (by adjusting the codomain), we obtain a bijection between $X$ and $f"(X)$. If $g : X \to n$ is a bijection, then $g \circ f^{-1} : f"(X) \to n$ is also a bijection, so $f"(X)$ is finite.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.2"></a><br/>
<h2>Exercise 3.2.</h2>
<a name="ex3.2(i)"></a><br/>
<h3>Exercise 3.2(i).</h3>
A subset of a countable set is at most countable.<br/>
<br/>
<i>Solution.</i> Note that a set is at most countable iff $\vert X\vert  \leq \vert \omega\vert $, iff there exists an injective mapping $X \to \omega$.<br/>
<br/>
Let $X$ be a countable set, and let $Y \subseteq X$. Consider the inclusion map $i : Y \to X$, which is of course injective. Since $X$ is countably, there exists a bijective map $f : X \to \omega$. Then $f \circ i : Y \to \omega$ is an injective mapping, so $Y$ is at most countable.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.2(ii)"></a><br/>
<h3>Exercise 3.2(ii).</h3>
The union of a finite set of countable sets is countable.<br/>
<br/>
<i>Solution.</i> Suppose $X_1,\dots,X_n$ are countable sets. Let $X := \bigcup_{i=1}^n X_i$. Since $X_1 \subseteq X$, $\vert X_1\vert  \leq \vert X\vert $ so $\vert X\vert  \geq \aleph_0$. To finish the proof, we need to find an injective mapping $X \to \omega$, so $\vert X\vert  \leq \aleph_0$.<br/>
<br/>
For each $i$, let $f_i : X_i \to \boldsymbol{N}$ be a bijection. Define $f : X \to \omega$ by stipulating that:<br/>
$$
\begin{align*}<br/>
f(x) = p_i^{f_i(x)}, \;\;\text{if $x \in X_i - \bigcup_{j < i} X_j$}<br/>
\end{align*}$$
where $p_i$ denotes the $i^\text{th}$ smallest prime number. It's easy to see that, by fundamental theorem of arithmetic, $f$ is injective.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.2(iii)"></a><br/>
<h3>Exercise 3.2(iii).</h3>
The image of a countable set (under a mapping) is at most countable.<br/>
<br/>
<i>Solution.</i> Let $X,Y$ be sets, $X$ countable, and let $f : X \to Y$ be a mapping. Let $g : \omega \to X$ be a bijection. Then $f \circ g : \omega \to Y$. Now define $h : Y \to \omega$ by stipulating that:<br/>
$$
\begin{align*}<br/>
h(y) := \min\lbrace n \in \omega : (g \circ f)(n) = y\rbrace<br/>
\end{align*}$$
Then $h$ is well-defined as $\omega$ is well-ordered, and clearly $h$ is injective. Thus there exists an injective map from $Y$ to $\omega$, so it is at most countable.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.3"></a><br/>
<h2>Exercise 3.3.</h2>
<i>Solution.</i> We shall show that the $f : \boldsymbol{N} \times \boldsymbol{N} \to \boldsymbol{N}$ in the hint is bijective.<br/>
<br/>
<u>Injective:</u> Suppose $f(m_1,n_1) = f(m_2,n_2)$, so $2^{m_1}(2n_1 + 1) - 1 = 2^{m_2}(2n_2 + 1) - 1 \implies 2^{m_1}(2n_1 + 1) = 2^{m_2}(2n_2 + 1)$. Now the $2^{n_i}$'s are odd, so $\nu_2(2^{m_i}(2n_i + 1)) = m_i$ (the \hyperlink{https://en.wikipedia.org/wiki/P-adic\_order}{$p$-adic order}). By Fundamental Theorem of Arithmetic, we have that $m_1 = m_2$. This implies that $2n_1 + 1 = 2n_2 + 1$, which easily gives $n_1 = n_2$. Thus $(m_1,n_1) = (m_2,n_2)$.<br/>
<br/>
<u>Surjective:</u> For any $N \in \boldsymbol{N}$, $N + 1$ is a positive integer, and by the Fundamental Theorem of Arithmetic we may write $N + 1 = 2^mN_2$ for some $m \in \boldsymbol{N}$ and $N_2 \in \boldsymbol{N}$, where $N_2$ is an odd integer. Then $N_2 = 2n + 1$ for some $n \in \boldsymbol{N}$, so $f(m,n) = 2^m(2n + 1) - 1 = N$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.4"></a><br/>
<h2>Exercise 3.4.</h2>
<a name="ex3.4(i)"></a><br/>
<h3>Exercise 3.4(i).</h3>
The set of all finite sequences in $\boldsymbol{N}$ is countable.<br/>
<br/>
<i>Solution.</i> Let $\boldsymbol{N}^{<\omega}$ denote the set of finite sequences in $\boldsymbol{N}$. Define a map $f : \boldsymbol{N}^{<\omega} \to \boldsymbol{N}$ as follows: For each $s = \c{s(0),\dots,s(n-1)} \in \boldsymbol{N}^{<\omega}$, let:<br/>
$$
\begin{align*}<br/>
f(s) = p_1^{s(0)+1}\cdots p_n^{s(n-1)+1}<br/>
\end{align*}$$
where $p_k$ is the $k^\text{th}$ smallest prime number. The injectivity of this map follows from the Fundamental Theorem of Arithmetic, so $\vert \boldsymbol{N}^{<\omega}\vert  \leq \vert \boldsymbol{N}\vert $. On the other hand, the map $n \mapsto \c{n}$ is clearly an injective map $\boldsymbol{N} \to \boldsymbol{N}^{<\omega}$, so $\vert \boldsymbol{N}^{<\omega}\vert  \geq \vert \boldsymbol{N}\vert $. By Cantor-Bernstein Theorem (Theorem 3.2), we have that $\vert \boldsymbol{N}^{<\omega}\vert  = \vert \boldsymbol{N}\vert $, so $\boldsymbol{N}^{<\omega}$ is countably infinite.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.4(ii)"></a><br/>
<h3>Exercise 3.4(ii).</h3>
The set of all finite subsets of a countable set is countable.<br/>
<br/>
<i>Solution.</i> WLOG we may show the statement for finite subsets of $\boldsymbol{N}$, the general case follows from establishing a bijection between $\boldsymbol{N}$ and the arbitrary countable set.<br/>
<br/>
Clearly $\vert \boldsymbol{N}\vert  \leq \vert [\boldsymbol{N}]^{<\omega}\vert $ by the injective map $n \mapsto \lbrace n\rbrace$. On the other hand, for each $\lbrace a_0,\dots,a_{n-1}\rbrace \in [\boldsymbol{N}]^{<\omega}$, where $a_0 < \cdots < a_{n-1}$, define the map from $[\boldsymbol{N}]^{<\omega}$ to $\boldsymbol{N}^{<\omega}$ by:<br/>
$$
\begin{align*}<br/>
\lbrace a_0,\dots,a_{n-1}\rbrace \mapsto \c{a_0,\dots,a_{n-1}}<br/>
\end{align*}$$
Clearly this map is injective, so $\vert [\boldsymbol{N}]^{<\omega}\vert  \leq \vert \boldsymbol{N}^{<\omega}\vert $. By Exercise <a href="#ex3.4(i)">Exercise 3.4(i)</a>, we have that $\vert [\boldsymbol{N}]^{<\omega}\vert  = \vert \boldsymbol{N}\vert $, so $[\boldsymbol{N}]^{<\omega}$ is countable.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.5"></a><br/>
<h2>Exercise 3.5.</h2>
<a name="lem3.5.A"></a><br/>
<b>Lemma 3.5.A.</b> For all ordinals $\alpha$, we have $\alpha \leq \omega^\alpha$.<br/>
<br/>
<i>Proof.</i> We induct on $\alpha$. For $\alpha = 0$ we have $\omega^0 = 1$. If $\beta \leq \omega^\beta$, then:<br/>
$$
\begin{align*}<br/>
\beta + 1 \leq \omega^\beta + 1 \leq \omega^\beta + \omega^\beta = \omega^\beta \cdot 2 \leq \omega^\beta \cdot \omega = \omega^{\beta+1}<br/>
\end{align*}$$
If $\alpha$ is a limit ordinal, then:<br/>
$$
\begin{align*}<br/>
\alpha = \lim_{\beta \to \alpha} \beta \leq \lim_{\beta \to \alpha} \omega^\beta = \omega^\alpha<br/>
\end{align*}$$
<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> For the first part, we induct on $\alpha$. For $\alpha = 0$, clearly $\Gamma(0 \times 0) = 0 \leq 1 = \omega^0$. If $\alpha > 0$ is a limit ordinal, then by continuity we have:<br/>
$$
\begin{align*}<br/>
\Gamma(\alpha \times \alpha) = \bigcup_{\beta<\alpha} \Gamma(\beta \times \beta) \leq \bigcup_{\beta<\alpha} \omega^\beta = \omega^\alpha<br/>
\end{align*}$$
Now suppose $\alpha = \beta + 1$. Since $(\gamma,\delta) \in \beta \times \beta$ iff $(\gamma,\delta) < (0,\beta)$ (so $\Gamma(0,\beta) \leq \omega^\beta$), we have that:<br/>
$$
\begin{align*}<br/>
\Gamma(\alpha \times \alpha) - \Gamma(\beta \times \beta) = \underbrace{\lbrace (\gamma,\beta) : \gamma < \beta\rbrace}_{\text{order type $\beta$}} \cup \underbrace{\lbrace (\beta,\gamma) : \gamma \leq \beta\rbrace}_{\text{order type $\beta + 1$}}<br/>
\end{align*}$$
Thus, this is of order type $\beta\cdot 2 + 1$, so by <a href="#lem3.5.A">Lemma 3.5.A</a>:<br/>
$$
\begin{align*}<br/>
\Gamma(\alpha \times \alpha) &= \Gamma(\beta + \beta) + \beta \cdot 2 + 1 \\<br/>
&\leq \omega^\beta + \beta + \beta + 1 \\<br/>
&\leq \omega^\beta + \omega^\beta + \omega^\beta + \omega^\beta \\<br/>
&= \omega^\beta \cdot 4 \\<br/>
&\leq \omega^\beta \cdot \omega \\<br/>
&= \omega^{\beta+1}<br/>
\end{align*}$$
The second part of the exercise is false. However, it is true that the fixed points of $\gamma(\alpha) = \Gamma(\alpha \times \alpha)$ are precisely the <i>multiplicatively indecomposable</i> ordinals. See Exercise I.11.7 of Kunen's <i>Set Theory</i>. The notion of indecomposable ordinals introduced in <a href="https://clementyung.github.io/jech-solutions/chapter-2#ex2.13">Exercise 2.13</a> is also called <i>additively indecomposable</i>.<br/>
<br/>
We shall show that $\Gamma(\omega^2 \times \omega^2) > \omega^2$. To do this, it suffices to show that $\Gamma((\omega + \omega) \times (\omega + \omega)) \geq \omega^2$. For each $n \in \omega$, the set:<br/>
$$
\begin{align*}<br/>
\lbrace (\alpha, \omega + n) : \alpha < \omega + n\rbrace \cup \lbrace (\omega + n,\alpha) : \alpha \leq \omega + n\rbrace<br/>
\end{align*}$$
is of order type  $(\omega + n) + (\omega + n + 1) = \omega \cdot 2 + n + 1$. Thus, it's easy to prove inductively that for each $n \in \omega$, we have $\Gamma((\omega + n) \times (\omega + n)) \geq \omega \cdot (2n + 1)$. Therefore:<br/>
$$
\begin{align*}<br/>
\Gamma((\omega + \omega) \times (\omega + \omega)) \geq \lim_{n \in \omega} \omega \cdot (2n + 1) = \omega^2<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.6"></a><br/>
<h2>Exercise 3.6.</h2>
<a name="lem3.6.A"></a><br/>
<b>Lemma 3.6.A.</b> Let $\alpha < \omega_\beta$ be an ordinal. Let $\alpha^{<\omega}$ be the set of all finite sequences of ordinals below $\alpha$. Then $\vert \alpha^{<\omega}\vert  < \kappa$.<br/>
<br/>
<i>Proof.</i> Let $f : \alpha \to \vert \alpha\vert $ be a bijection. By Theorem 3.5 we know that $\Gamma(\vert \alpha\vert  \times \vert \alpha\vert ) = \vert \alpha\vert $. Thus, we obtain a choiceless bijection $g := f^{-1} \circ \Gamma \circ (f,f) : \alpha \times \alpha \to \alpha$. Let $g_2 := g$, and inductively define $g_n : \alpha^n \to \alpha$ by $g_n := (g_{n-1},g)$. With this, we may define $h : \alpha^{<\omega} \to \alpha \times \omega$ by:<br/>
$$
\begin{align*}<br/>
h(s) := (g_{\length(s)}(s),\length(s))<br/>
\end{align*}$$
Then clearly $h$ is one-to-one, so we have:<br/>
$$
\begin{align*}<br/>
\vert \alpha^{<\omega}\vert  < \vert \alpha \times \vert \omega\vert  = \vert \alpha\vert  \cdot \aleph_0 \leq \vert \alpha\vert  < \omega_\beta<br/>
\end{align*}$$
<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> We require the Axiom of Choice in this solution.<br/>
<br/>
We first define a function $\height$ on finite sequences of ordinals, in which if $f$ is such a sequence then:<br/>
$$
\begin{align*}<br/>
\height(s) := \max\lbrace \length(s),\max\lbrace s(i) : i < \length(s)\rbrace\rbrace<br/>
\end{align*}$$
We shall define an ordering as follows: Given two finite sequences of ordinals $s$ and $t$, we say that $s < t$ iff one of the following holds:
<ol>
<li> $\height(s) < \height(t)$.</li>
<li> $\height(s) = \height(t)$ and $\length(s) < \length(t)$.</li>
<li> $\height(s) = \height(t)$, $\length(s) = \length(t)$ and there exists some $k < \length(s)$ such that $s(k) < t(k)$, and $s(i) = t(i)$ for all $i < k$.</li></ol>
As an example, an initial segment of this ordering is as follows:<br/>
$$
\begin{gather*}<br/>
\emptyset < (0) < (1) < (2) < (0,0) < (0,1) < (0,2) < (1,0) < (1,1) < (1,2) \\<br/>
< (2,0) < (2,1) < (2,2) < (3) < (0,3) < (1,3) < (2,3) < (3,3) < (0,0,0) < \dots<br/>
\end{gather*}$$
One can check that $<$ is a linear order (transitivity is the most tedious to check, but it can be done by considering cases). We first show that $<$ is a well-order. Let $X \subseteq \boldsymbol{\mathrm{ORD}}^{<\omega}$. Let $Y \subseteq X$ be the non-empty subset of all elements of $X$ of minimal height, then let $Z \subseteq Y$ be the non-empty subset of all elements of $Y$ of minimal length. Thus, all elements in $Z$ have equal height and length, and $(\forall z \in Z)(\forall x \in X - Z) \, z < x$. Thus, it suffices to show that $Z$ has a $<$-minimal element.<br/>
<br/>
Suppose all elements of $Z$ has length $n$. For each $i < n$, let:
<ol>
<li> $Z_0 := \lbrace z \in Z : z(0) = \min\lbrace z'(0) : z' \in Z\rbrace\rbrace$.</li>
<li> $Z_i := \lbrace z \in Z_{i-1} : z(i) = \min\lbrace z'(i) : z' \in Z\rbrace\rbrace$.</li></ol>
By well-ordering of ordinals all of $Z_i$'s are non-empty. Let $z \in Z_{n-1}$. Then $z$ is the minimal element in $Z$ - otherwise, if $z' < z$, then since $\height(z) = \height(z')$ and $\length(z) = \length(z')$, we have that $z'(k) < z(k)$ for some $k < n$, and $z'(i) = z(i)$ for $i < k$. Since $z(i)$ is minimal for all $i$, we have that $z'(i)$ is minimal for all $i < k$, therefore $z' \in Z_{k-1}$. But $z \in Z_k$ and $z'(k) < z(k)$, contradicting minimality of $z(k)$.<br/>
<br/>
Thus, we may denote $\Lambda(s)$ as the order type of the set of all finite sequences below $s$ under $<$. Let $\Lambda(\alpha^{<\omega}) := \Lambda((\alpha))$. $\Lambda(\omega_\alpha^{<\omega}) = \omega_\alpha$ for all $\alpha$. We first observe that $(\beta) < (\omega_\alpha)$ for all $\beta < \omega_\alpha$, so $\Lambda(\omega_\alpha^{<\omega}) \geq \omega_\alpha$. Now suppose for a contradiction that $\Lambda(\omega_\alpha^{<\omega}) > \omega_\alpha$. Let $s$ be the $<$-minimal sequence such that $\Lambda(s) = \omega_\alpha$. Let $\delta < \omega_\alpha$ such that $\delta > s(i)$ for all $i < \length(s)$. Then $\omega_\alpha \subseteq \Lambda(\delta^{<\omega})$. Now observe that $\Lambda(\delta^{<\omega}) \subseteq \delta^{<\omega}$, so $\vert \delta^{<\omega}\vert  \geq \aleph_\alpha$. This contradicts <a href="#lem3.6.A">Lemma 3.6.A</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.7"></a><br/>
<h2>Exercise 3.7.</h2>
<i>Solution.</i> Let $f : \omega_\alpha \to B$ be an onto function. Define $g : B \to \omega_\alpha$ by stipulating that for $x \in B$, $g(x) = \min\lbrace f_{-1}(\lbrace x\rbrace)\rbrace$. This is well defined as for $x \neq y$, $f_{-1}(\lbrace x\rbrace)$ and $f_{-1}(\lbrace y\rbrace)$ are disjoint. They are also non-empty as $f$ is onto. Then $g$ is a one-to-one function on $B$ into $\omega_\alpha$, so $\vert B\vert  \leq \vert \omega_\alpha\vert  = \aleph_\alpha$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.8"></a><br/>
<h2>Exercise 3.8.</h2>
<i>Solution.</i> We note that by restricting the well-order in <a href="#ex3.6">Exercise 3.6</a> to finite sequences of $\omega_\alpha$, we obtain a choiceless well-order in $\omega_\alpha^{<\omega}$, along with the order type $\Lambda$. Then $\Lambda^{-1}(\omega_\alpha) = \omega_\alpha^{<\omega}$, so $\omega_\alpha^{<\omega}$ is a projection of $\omega_\alpha$. Clearly the set of all finite subsets of $\omega_\alpha$ is a projection of $\omega_\alpha^{<\omega}$, so the set of all finite subsets of $\omega_\alpha$ is a projection of $\omega_\alpha$ itself. By <a href="#ex3.7">Exercise 3.7</a>, this set has cardinality $\leq \aleph_\alpha$. On the other hand, the map $\beta \mapsto \lbrace \beta\rbrace$ is a one-to-one function on $\omega_\alpha$ to this set, so it has cardinality $\geq \aleph_\alpha$. Thus equality follows.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.9"></a><br/>
<h2>Exercise 3.9.</h2>
<i>Solution.</i> Consider the function $g$ in the hint. It suffices to show that the function $g$ defined in the hint is one-to-one. Suppose $X \neq Y$ and suppose $x \in X - Y$. If $f(a) = x$ where $a \in B$, when $a \in f_{-1}(X) - f_{-1}(Y)$, so $g(X) \neq g(Y)$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.10"></a><br/>
<h2>Exercise 3.10.</h2>
<i>Solution.</i> By the pairing function $\Gamma$ in Theorem 3.5 we have that $\omega_\alpha \times \omega_\alpha$ is a projection of $\omega_\alpha$, and therefore $P(\omega_\alpha \times \omega_\alpha)$ is a projection of $P(\omega_\alpha)$. Let $f$ be the function in the hint (and if $R$ is not a well-order, let $f(R) := 0$). We shall show that $\ran(f) = \omega_{\alpha+1}$.<br/>
<br/>
<u>$\ran(f) \supseteq \omega_{\alpha+1}$:</u> Let $\beta < \omega_{\alpha+1}$. Then $\vert \beta\vert  \leq \aleph_\alpha$, so there exists a one-to-one function $f : \beta \to \omega_\alpha$. Define a well-ordering $R \subseteq \omega_\alpha \times \omega_\alpha$ by:<br/>
$$
\begin{align*}<br/>
(\gamma,\delta) \in R \iff (\exists \xi < \beta)(\exists \zeta < \xi)(f(\zeta) = \gamma \wedge f(\xi) = \delta)<br/>
\end{align*}$$
Then clearly $R$ is a well order of order type $\beta$.<br/>
<br/>
<u>$\ran(f) \subseteq \omega_{\alpha+1}$:</u> Let $R$ be a well order and let $\beta = f(R)$. We may then define $g : \beta \to \omega_\alpha$ by having $g(\gamma) := \alpha_\gamma$, where $\alpha_\gamma$ is the $\gamma^\text{th}$ ordinal under the well order $R$. The well order of $R$ also implies that $g$ must be one-to-one, so $\vert \beta\vert  \leq \vert \alpha\vert  < \omega_{\alpha+1}$. Hence $\beta \in \omega_{\alpha+1}$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.11"></a><br/>
<h2>Exercise 3.11.</h2>
<i>Solution.</i> By Lemma 3.3, $\aleph_{\alpha+1} < 2^{\aleph_{\alpha+1}}$. By <a href="#ex3.10">Exercise 3.10</a>, $\omega_{\alpha+1}$is a projection of $P(\omega_\alpha)$, so by <a href="#ex3.9">Exercise 3.9</a> we have that $\vert P(\omega_{\alpha+1})\vert  \leq \vert P(P(\omega_\alpha))\vert $, i.e. $2^{\aleph_{\alpha+1}} \leq 2^{2^{\aleph_\alpha}}$. Thus $\aleph_{\alpha+1} < 2^{2^{\aleph_\alpha}}$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.12"></a><br/>
<h2>Exercise 3.12.</h2>
<i>Solution.</i> There is a typo in the second statement: $\omega_\alpha$ is not the limit of $\c{\omega_\xi : \xi < \cf{\alpha}}$. Regardless, it's true that $\cf{\omega_\alpha} = \cf{\alpha}$. This follows from Lemma 3.7(ii) and $\omega_\alpha := \lim_{\xi\to\alpha} \omega_\xi$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.13"></a><br/>
<h2>Exercise 3.13.</h2>
<i>Solution.</i> We expand on the hint. Note that the mapping $f : \omega \times \alpha \to \omega_2$ is defined as:<br/>
$$
\begin{align*}<br/>
f(n,\beta) = \text{the $\beta^\text{th}$ element of $S_n$}<br/>
\end{align*}$$
where if $\beta \geq \alpha_n$ then $f(n,\beta) := 0$. Now $\vert \omega \times \alpha\vert  = \aleph_0 \cdot \vert \alpha\vert  \leq \omega_1$, so $\alpha \times \omega$ is a projection of $\omega_1$. Composing these two maps implies that $\omega_2$ is a projection of $\omega_1$, a contradiction.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.14"></a><br/>
<h2>Exercise 3.14.</h2>
<i>Solution.</i> If $S$ is D-infinite, let $f,X$ be as in the hint. We shall show that $i \neq j$ implies $x_i \neq x_j$ (so $\lbrace x_n : n < <\omega\rbrace$ is indeed a countably infinite subset). Suppose $x_i = x_j$ for some $i,j < \omega$. WLOG suppose $i \leq j$, and write $j = i + k$. Then $f^{(i+k)}(x_0) = f^{(i)}(x_0)$. Since $f$ is one-to-one, $x_0 = f^{(k)}(x_0)$. Since $f^{(k)}(x_0) \in S - X$ but $\ran(f) \subseteq X$, we must have $k = 0$. Thus $i = j$.<br/>
<br/>
Conversely, suppose $S$ has a countable subset $X \subseteq S$. Let $f : X \to \omega$ be one-to-one and onto. We define $g : S \to S$ by:<br/>
$$
\begin{align*}<br/>
g(x) :=<br/>
\begin{cases}<br/>
x, &\text{if $x \in S - X$} \\<br/>
f^{-1}(f(x + 1)), &\text{if $x \in X$}<br/>
\end{cases}<br/>
\end{align*}$$
Clearly $g$ is one-to-one. Furthermore, $\ran(g)$ is a proper subset of $S$ as $f^{-1}(0) \notin \ran(g)$. Thus $S$ is D-infinite.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.15"></a><br/>
<h2>Exercise 3.15.</h2>
<a name="ex3.15(i)"></a><br/>
<h3>Exercise 3.15(i).</h3>
If $A$ and $B$ are D-finite, then $A \cup B$ and $A \times B$ are D-finite.<br/>
<br/>
\begin{lemma}{3.15(i).A}<br/>
\label{lem3.15(i).A}<br/>
If $A$ and $B$ are finite, $A \times B$ is finite.<br/>
<br/>
<i>Proof.</i> $A \cup B$ is finite by <a href="#ex3.1(ii)">Exercise 3.1(ii)</a>, so $P(P(A \cup B))$ is finite by <a href="#ex3.1(iii)">Exercise 3.1(iii)</a>. Observe that $A \times B \subseteq P(P(A \cup B))$, so by <a href="#ex3.1(i)">Exercise 3.1(i)</a> $A \times B$ is finite,<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Suppose $A \cup B$ is D-infinite, so by <a href="#ex3.14">Exercise 3.14</a> it contains a countable subset. Let $X \subseteq A \cup B$ be countable. Then $X = (X \cap A) \cup (X \cap B)$. By <a href="#ex3.2(i)">Exercise 3.2(i)</a>, $X \cap A$ and $X \cap B$ are at most countable. Since $A$ and $B$ are $D$-finite, they do not contain a countable subset. Thus, $X \cap A$ and $X \cap B$ are both finite. By <a href="#ex3.1(ii)">Exercise 3.1(ii)</a>, $X$ is finite, a contradiction.<br/>
<br/>
Suppose $A \times B$ is D-infinite with $X \subseteq A \times B$ countable. Let:<br/>
$$
\begin{gather*}<br/>
X_A := \lbrace a \in A : (\exists b \in B) \, (a,b) \in X\rbrace \\<br/>
X_B := \lbrace b \in B : (\exists a \in A) \, (a,b) \in X\rbrace<br/>
\end{gather*}$$
$X_A$ and $X_B$ are images under the mappings $(a,b) \mapsto a$ and $(a,b) \mapsto b$ of $X$ respectively, so by <a href="#ex3.2(iii)">Exercise 3.2(iii)</a> they are both finite. But observe that $X \subseteq X_A \times X_B$, so by <a href="#lem3.15(i).A">Lemma 3.15(i).A</a> and <a href="#ex3.1(i)">Exercise 3.1(i)</a> $X$ is finite, a contradiction.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.15(ii)"></a><br/>
<h3>Exercise 3.15(ii).</h3>
The set of all finite one-to-one sequences in a D-finite set is D-finite.<br/>
<br/>
<i>Solution.</i> Let $A$ be a D-finite set and let $A'$ denote the set of all one-to-one sequences of elements of $A'$. Suppose $A'$ is D-infinite with $X \subseteq A'$ countable. Write $X = \lbrace s_i : i < \omega\rbrace$. Define $x_i \in A$ inductively as follows:
<ol>
<li> $x_0 := s_0(0)$.</li>
<li> $x_{n+1} := s_i(k)$, where $i$ is the least $i < \omega$ such that $\ran(s_i) \not\subseteq \lbrace x_j : j < i\rbrace$, and $k$ is the least $k < \length(s_i)$ such that $s_i(k) \notin \lbrace x_j : j < i\rbrace$.</li></ol>
If $x_n$ is well-defined for all $n$, then it forms a countable subset of $A$, a contradiction. To see that it is indeed well-defined, suppose not, so there exists a finite set $F$ and an $n$ such that for all $m \geq n$, $\ran(s_m) \subseteq F$. This implies that:<br/>
$$
\begin{align*}<br/>
\bigcup_{m < \omega} \ran(s_m) \subseteq \underbrace{F \cup \bigcup_{m < n} \ran(s_m)}_{\text{finite}}<br/>
\end{align*}$$
Therefore $X \subseteq [F']^{<\omega}$ for some finite set $F'$. Thus, if $\vert F'\vert  = N$, then since all sequences in $X$ are one-to-one, we have:<br/>
$$
\begin{align*}<br/>
X \subseteq \bigcup_{i \leq N} \prod_{j < i} F'<br/>
\end{align*}$$
but RHS is finite by <a href="#lem3.15(i).A">Lemma 3.15(i).A</a> and <a href="#ex3.1(ii)">Exercise 3.1(ii)</a>, a contradiction.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.15(iii)"></a><br/>
<h3>Exercise 3.15(iii).</h3>
The union of a disjoint D-finite family of D-finite sets is D-finite.<br/>
<br/>
<i>Solution.</i> Let $I$ be D-finite, and for each $i \in I$ let $A_i$ be a D-finite set such that $i \neq j \implies A_i \cap A_j = \emptyset$. Let $A := \bigsqcup_{i \in I} A_i$. Suppose $A$ is D-infinite with a countable subset $X \subseteq A$. Write $X = \lbrace x_i : i < \omega\rbrace$.<br/>
<br/>
Define $Y = \lbrace y_i : i < \omega\rbrace \subseteq X$ inductively as follows:
<ol>
<li> $y_0 := x_0$. Let $i_0 \in I$ be the unique element of $I$ such that $y_0 \in A_{i_0}$. This $i_0$ is well-defined, as the set $\lbrace i \in I : x_0 \in i\rbrace$ is singleton.</li>
<li> Let $y_n \in X$ be such that $y_n \notin \bigcup_{k < n} A_{i_k}$. Such a $y_n$ exists, for otherwise we have that $X \subseteq \bigcup_{k < n} A_{i_k}$. RHS is a finite union of D-finite set, which is D-finite by <a href="#ex3.15(i)">Exercise 3.15(i)</a>, a contradiction. Let $i_n \in I$ be (unique) such that $y_n \in A_{i_n}$.</li>
</ol>
In particular, this gives us $I' := \lbrace i_k : k < \omega\rbrace \subseteq I$, contradicting that $I$ is D-finite.<p align="right">$\square$</p><br/>
<br/>
<a name="ex3.16"></a><br/>
<h2>Exercise 3.16.</h2>
<i>Solution.</i> As in the hint, it suffices to show that $\lbrace X \subseteq A : \vert X\vert  = n\rbrace$ is non-empty for each $n$, in which it's clear that they are pairwise unequal, so $P(P(A))$ is D-infinite.<br/>
<br/>
We induct on $n$ that $S_n := \lbrace X \subseteq A : \vert X\vert  = n\rbrace$ is non-empty. $S_0$ is non-empty as $\emptyset \in S_0$. If $S_n$ is non-empty, let $X \in S_n$. Since $X \subseteq A$ is finite and $A$ is infinite, we have $A - X \neq \emptyset$, so let $x \in A - X$. Then $\vert X \cup \lbrace x\rbrace\vert  = n + 1$ by <a name="#1#lem1.13.A">Lemma 1.13.A</a>, so $X \cup \lbrace x\rbrace \in S_{n+1}$, i.e. $S_{n+1}$ is non-empty.<p align="right">$\square$</p>\n</body>