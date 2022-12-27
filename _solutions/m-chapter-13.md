---
title: "13) Constructible Sets"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-13
excerpt: ""
---

{% include commands.html %}

<body>
<a name="ex13.1"></a><br/>
<h2>Exercise 13.1.</h2>
<i>Solution.</i> Let $Z \in \cl(M)$, the transitive closure of $M$ under the G&ouml;del operations. We induct on the complexity of $Z$ under the operations to show that:<br/>
<center><br/>
If $x \in^\ast  Z$ (i.e. there's a finite sequence $x \in x_1 \in \cdots \in x_n \in Z$), then $x \in \cl(M)$.<br/>
</center><br/>
Call this property (T). Note that if a set is transitive, then every element of this set satisfies this condition. Let $X,Y \in \cl(M)$:
<ol>
<li> If $Z = \lbrace X,Y\rbrace$, then immediately $Z \subseteq \cl(M)$, and satisfies the property (T).</li>
<li> If $Z = X \times Y \in \cl(M)$, let $z = (x,y) = \lbrace \lbrace x\rbrace,\lbrace x,y\rbrace\rbrace \in Z$. Then $x,y \in Z$ by IH on $X,Y \in \cl(M)$, so by $G_1$ we have that $\lbrace x\rbrace,\lbrace x,y\rbrace \in \cl(M)$. By $G_1$ again, $x = \lbrace \lbrace x\rbrace,\lbrace x,y\rbrace\rbrace \in \cl(M)$, so $Z \subseteq \cl(M)$. This also proves that property (T) is satisfied.</li>
<li> Since $\varepsilon(X,Y) \subseteq X \times Y$, this follows from (2).</li>
<li> If $X,Y \subseteq \cl(M)$ then immediately $Z = X - Y \subseteq X \subseteq \cl(M)$. Since $X$ satisfies property (T), so does $Z$.</li>
<li> If $X,Y \subseteq \cl(M)$ then immediately $Z = X \cap Y \subseteq X \subseteq \cl(M)$. Since $X$ satisfies property (T), so does $Z$.</li>
<li> If $Z = \bigcup X$, let $z \in^\ast  Z$. Then $z \in^\ast  y \in X$. By IH, $X$ satisfies the property (T), so $z \in \cl(M)$, hence $Z$ satisfies the property (T).</li>
<li> If $Z = \dom(X)$, let $z \in^\ast  Z$. Then $(z',y) = \lbrace \lbrace z'\rbrace,\lbrace z',y\rbrace\rbrace \in X$ for some $y$ and $z \in z'$ or $z = z'$. We see that $z' \in \lbrace z'\rbrace \in (z',y) \in X$, so by IH on $X$, $z \in \cl(M)$.</li>
<li>[(8-10)] Similar to that of (7).</li>
</ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex13.2"></a><br/>
<h2>Exercise 13.2.</h2>
<i>Solution.</i> Note that if $M = \emptyset$ then the assertion holds true vacuously, so assume otherwise. We induct on $\vert X\vert $. If $\vert X\vert  = 0$, then trivially $X \subseteq M$. Now assume the assertion holds for $\vert X\vert  = k$. Let $X = \lbrace x_1,\dots,x_{k+1}\rbrace \in M$.<br/>
<br/>
Now we observe that at least one of $x_i$ must be in $M$ - otherwise, we have $\func{ext}_\in(X) = \func{ext}_\in(\emptyset)$ (note that $\emptyset \in M$ necessary, as we may take any $Y \in M$ and we have $\emptyset = Y - Y \in M$). WLOG suppose $x_{k+1} \in M$, and we have that $\lbrace x_{k+1}\rbrace \in M$ by $G_1$, so $X - \lbrace x_{k+1}\rbrace = \lbrace x_1,\dots,x_n\rbrace \in M$. By IH, $x_i \in M$ for all $1 \leq i \leq n$, completing the proof.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.3"></a><br/>
<h2>Exercise 13.3.</h2>
<i>Solution.</i> An equivalent formulation of the problem is to show that if $G$ is a composition of G&ouml;del operations, then $\pi(G(X,Y)) = G(\pi(X),\pi(Y))$.<br/>
<br/>
Note that, as discussed in Theorem 13.9, closure under G&ouml;del operations guarantees us that $\in$ is well-founded in $M$. By Mostoswki's Collapsing Theorem, $\pi$ is an isomosphism between $M$ and its transitive collapse. By G&ouml;del's Normal Form Theorem (Theorem 13.4 and Lemma 13.7), every set in $M$ can be represented by a formula. That is, for all $X_1,\dots,X_n \in M$, there exists a $\Delta_0$ formula $\varphi$ such that:<br/>
$$
\begin{align*}<br/>
G(X_1,\dots,X_n) = \lbrace (u_1,\dots,u_n) : u_1 \in X_1,\dots,u_n \in X_n, \varphi(u_1,\dots,u_n)\rbrace<br/>
\end{align*}$$
Since $\pi$ is an isomorphism:<br/>
$$
\begin{align*}<br/>
\pi(G(X_1,\dots,X_n)) &= \lbrace (u_1,\dots,u_n) : u_1 \in \pi(X_1),\dots,u_n \in \pi(X_n), \varphi(u_1,\dots,u_n)\rbrace \\<br/>
&= G(\pi(X_1),\dots,\pi(X_n))<br/>
\end{align*}$$
as desired.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.4"></a><br/>
<h2>Exercise 13.4.</h2>
<i>Solution.</i> $G_8$ can be represented more simply - we show that $G_8(X) = \dom(G_{10}(G_9(X \times X)))$. Note that $G_9$ applies the permutation $(2,3)$ to all triples in the set, and $G_{10}$ applies the permutation $(1,2,3)$ to all triples in the set.<br/>
<br/>
Note that $(u,v,w) = ((u,v),w)$ by definition of ordered pairs, and:<br/>
$$
\begin{align*}<br/>
G_8(X) = G_8(X \cap \lbrace (u,v) : u,v \in V\rbrace)<br/>
\end{align*}$$
where $V$ is the universe (or the model we're working in).<br/>
$$
\begin{align*}<br/>
&\eqbreak \dom(G_{10}(G_9(X \times X))) \\<br/>
&= \dom(G_{10}(\lbrace (u,w,v) : (u,v,w) \in X \times X\rbrace)) \\<br/>
&= \dom(\lbrace (v,u,w) : (u,v,w) \in X \times X\rbrace) \\<br/>
&= \lbrace (v,u) : (\exists w \in X) \, (u,v,w) \in X \times X\rbrace<br/>
\end{align*}$$
It suffices to show that $X \cap \lbrace (u,v) : u,v \in V\rbrace = \lbrace (v,u) : (\exists w \in X) \, (u,v,w) \in X \times X\rbrace$. $\supseteq$ is immediate. Conversely, if $(u,v) \in X$, then $(u,v,(u,v)) \in X \times X$, which maps to $(u,v) \in X$ under the operation $\dom$.<br/>
<br/>
For $G_5$, we have:<br/>
$$
\begin{align*}<br/>
&\eqbreak G_5(X,Y) \\<br/>
&= X \cap Y \\<br/>
&= X \cup Y - ((X \cup Y - X) \cup (X \cup Y - Y)) \\<br/>
&= G_4(X \cup Y,G_4(X \cup Y,X) \cup G_4(X \cup Y,Y)) \\<br/>
&= G_4(G_6(G_1(X,Y)),G_6(G_1(G_4(G_6(G_1(X,Y)),X),G_4(G_6(G_1(X,Y)),Y))))<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.5"></a><br/>
<h2>Exercise 13.5.</h2>
<a name="lem13.5.A"></a><br/>
<b>Lemma 13.5.A.</b> The following are equivalent in $\mathsf{BG} \; - $ Comprehension:
<ol>
<li> $\forall X_1 \, \dots \, \forall X_n \, \exists Y \, Y = \lbrace x : \varphi(x,X_1,\dots,X_n)\rbrace$, where $\varphi$ is a formula in which only set variables are quantified.</li>
<li> $\forall X_1 \, \dots \, \forall X_n \, \exists Y \, Y = \lbrace (x_1,\dots,x_m) : \varphi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace$, where $\varphi$ is a formula in which only set variables are quantified.</li>
</ol>
<br/>
<i>Proof.</i> <u>(i) $\implies$ (ii):</u> Let $\varphi(x_1,\dots,x_m,y_1,\dots,y_n)$ be such a formula. Define a formula $\psi(x,y_1,\dots,y_n)$ by:<br/>
$$
\begin{align*}<br/>
\psi(x,y_1,\dots,y_m) \iff \exists x_1 \, \dots \, \exists x_n \, (x = (x_1,\dots,x_n) \wedge \varphi(x_1,\dots,x_m,y_1,\dots,y_n))<br/>
\end{align*}$$
By (i), for any classes $X_1,\dots,X_n$ there exists $Y$ such that $Y = \lbrace x : \psi(x,y_1,\dots,y_n)\rbrace$. Clearly $Y = \lbrace (x_1,\dots,x_m) : \varphi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace$, as desired.<br/>
<br/>
<u>(ii) $\implies$ (i):</u> Let $\varphi(x,y_1,\dots,y_n)$ be such a formula. By (ii) for any classes $X_1,\dots,X_n$ there exists a class $Y$ such that $Y = \lbrace (x) : \varphi(x,X_1,\dots,X_n)\rbrace$. By definition $(x) = \lbrace x\rbrace$, so $\bigcup Y = \lbrace x : \varphi(x,X_1,\dots,X_n)\rbrace$.<p align="right">$\blacksquare$</p><br/>
<br/>
<a name="lem13.5.B"></a><br/>
<b>Lemma 13.5.B.</b> If $\varphi(u_1,\dots,u_n)$ is a formula with only set variables quantified, then there is a composition $G$ of the operations $G_1,\dots,G_{10}$ above such that for all classes $X_1,\dots,X_n$, there exist classes $X,Y$ such that:<br/>
$$
\begin{align*}<br/>
G_i(X,Y) = \lbrace (x_1,\dots,x_m) : \varphi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace<br/>
\end{align*}$$
where $X = G^{(1)}(X_1,\dots,X_n)$ and $X = G^{(2)}(X_1,\dots,X_n)$ for some composition $G^{(1)},G^{(2)}$.<br/>
<br/>
<i>Proof.</i> Similar to the original Normal Form Theorem, suffices to consider only formulas of the form:
<ol>
<li> The only logical symbols in $\varphi$ are $\neg$, $\wedge$ and $\exists$ (quantified over sets).</li>
<li> $=$ does not occur.</li>
<li> The only occurrence of $\in$ is $x_i \in x_j$ for $i \neq j$, $x_i \in X_j$, or $X_i \in X_j$.</li>
<li> All existential formulas are of the form $\exists y \, \varphi(y,x,X_1,\dots,X_n)$.</li>
</ol>
We induct on the complexity of $\varphi$, assuming that the statement holds for all subformulas of $\varphi$.<br/>
<br/>
<b>Case I - $\varphi$ is atomic:</b> If $\varphi$ is of the form $x_i \in x_j$ where $i \neq j$, then the proof that this can be written in terms of the $G_i$'s is very much similar to the Case I of Normal Form Theorem. For instance, in the easy case of $x_1 \in x_2$, we have:<br/>
$$
\begin{align*}<br/>
\lbrace (x_1,\dots,x_m) : \varphi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace = G_3 \times V \times \dots \times V<br/>
\end{align*}$$
The use of $G_8,G_9$ and $G_{10}$ are needed to permutate the general case. If $\varphi$ is of the form $x_i \in X_j$, then:<br/>
$$
\begin{align*}<br/>
\lbrace (x_1,\dots,x_m) : \varphi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace = V \times \dots \times X_j \times \dots \times V<br/>
\end{align*}$$
where the $X_j$ is in the $i^\text{th}$ position. Finally, if $\varphi$ is of the form $X_i \in X_j$, then since none of the $x_i$ is not a free variables inside $\varphi$ we have that the set is either $V$ or empty ($\emptyset = V - V$).<br/>
<br/>
<b>Case II - $\varphi$ is a negation:</b> If $\varphi$ is $\neg\psi$, we have:<br/>
$$
\begin{gather*}<br/>
\lbrace (x_1,\dots,x_m) : \neg\psi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace \\<br/>
= \\<br/>
V \times \dots \times V - \lbrace (x_1,\dots,x_m) : \psi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace<br/>
\end{gather*}$$
<b>Case III - $\varphi$ is a conjunction:</b> If $\varphi$ is $\psi_1 \wedge \psi_2$, we have:<br/>
$$
\begin{gather*}<br/>
\lbrace (x_1,\dots,x_m) : (\psi_1 \cap \psi_2)(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace \\<br/>
= \\<br/>
\lbrace (x_1,\dots,x_m) : \psi_1(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace \cap \lbrace (x_1,\dots,x_m) : \psi_2(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace<br/>
\end{gather*}$$
<b>Case IV - $\varphi$ is existential:</b> Suppose $\varphi$ is $\exists y \, \psi(x_1,\dots,x_m,y,X_1,\dots,X_n)$ (see condition (iv)). Since $(x_1,\dots,x_m,y) = ((x_1,\dots,x_m),y)$, we have that:<br/>
$$
\begin{gather*}<br/>
\lbrace (x_1,\dots,x_m) : \exists y \, \psi(x_1,\dots,x_m,y,X_1,\dots,X_n)\rbrace \\<br/>
=\\<br/>
\dom(\lbrace (x_1,\dots,x_{m+1}) : \psi(x_1,\dots,x_m,x_{m+1},X_1,\dots,X_n)\rbrace)<br/>
\end{gather*}$$
<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Consider endowing $\mathsf{BG} \; - $Comprehension with the finite axiom schema:<br/>
$$
\begin{align*}<br/>
\forall X \, \forall Y \, \exists Z \, Z = G_i(X,Y)<br/>
\end{align*}$$
where the $G_i$'s are defined earlier in this exercise. Given a formula $\varphi$ in which only set variables are quantified, by <a href="#lem13.5.B">Lemma 13.5.B</a> let $G$ be a (finite) composition of operations such that:<br/>
$$
\begin{align*}<br/>
G(X,Y) = \lbrace (x_1,\dots,x_m) : \varphi(x_1,\dots,x_m,X_1,\dots,X_n)\rbrace<br/>
\end{align*}$$
We induct on the complexity of $G$. If $G = G_i$ for some $i$, then by the above axiom we immediately have $Z = G_i(X,Y)$ for some class $Z$. Otherwise, suppose $G(X,Y) = G_i(G^{(1)}(X',Y'),G^{(2)}(X",Y"))$ for some composition $G^{(1)},G^{(2)}$. By induction hypothesis, there exists classes $Z_1,Z_2$ such that $Z_1 = G^{(1)}(X',Y')$ and $Z_2 = G^{(2)}(X",Y")$. Then by the axiom again we have a class $Z$ such that $Z = G_i(Z_1,Z_2)$, which is the desired class. This implies the Axiom of Comprehension by <a href="#lem13.5.A">Lemma 13.5.A</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.6"></a><br/>
<h2>Exercise 13.6.</h2>
<i>Solution.</i> We first note that since $M$ is transitive, for all $X \in M$ we have $P^M(X) = P(X) \cap M$. Indeed:<br/>
$$
\begin{align*}<br/>
x \in P^M(X) &\iff (\forall y \in M)(y \in x \to y \in X) \\<br/>
&\iff x \in M \wedge \forall y \, (y \in x \to y \in X) && \text{as $M$ is transitive} \\<br/>
&\iff x \in M \wedge x \in P(X) \\<br/>
&\iff x \in M \cap P(X)<br/>
\end{align*}$$
We now prove the exercise by induction on $\alpha \in M$. Of course $V_0 = V_0^M = \emptyset$. If $\alpha$ is limit, then:<br/>
$$
\begin{align*}<br/>
V_\alpha^M = \bigcup_{\beta < \alpha} V_\beta^M = \bigcup_{\beta < \alpha} V_\beta \cap M = V_\alpha \cap M<br/>
\end{align*}$$
We now prove for the successor case. We first observe that:<br/>
$$
\begin{align*}<br/>
V_{\alpha+1}^M = P^M(V_\alpha^M) = P(V_\alpha \cap M) \cap M<br/>
\end{align*}$$
We shall show that $P(V_\alpha \cap M) \cap M = P(V_\alpha) \cap M$. $\subseteq$ is immediate. Conversely, if $x \in P(V_\alpha) \cap M$, then $x \in M$ and $x \subseteq V_\alpha$. Since $M$ is transitive, we have $x \subseteq M$, so $x \subseteq V_\alpha \cap M$. Thus $x \in P(V_\alpha \cap M)$. Therefore:<br/>
$$
\begin{align*}<br/>
V_{\alpha+1}^M = P(V_\alpha \cap M) \cap M = P(V_\alpha) \cap M = V_{\alpha+1} \cap M<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.7"></a><br/>
<h2>Exercise 13.7.</h2>
<i>Solution.</i> A $\Sigma_1$ formulation of "$X$ is finite" is:<br/>
$$
\begin{align*}<br/>
X \text{ is finite} \iff \exists f \, (f \text{ is a one-to-one function} \wedge \dom(f) = X \wedge \ran(f) \in \omega)<br/>
\end{align*}$$
Note that all sentences in the bracket are $\Delta_0$ by Lemma 12.10.<br/>
<br/>
For a $\Pi_1$ formulation, recall from <a href="https://clementyung.github.io/jech-solutions/chapter-1#ex1.12">Exercise 1.12</a> and <a href="https://clementyung.github.io/jech-solutions/chapter-1#ex1.13">Exercise 1.13</a> that a set is finite iff $T$-finite. Thus:<br/>
$$
\begin{align*}<br/>
X \text{ is finite} \iff \forall X \, (X \subseteq P(S) \to ((\exists x \in X)(\forall y \in X) \, y \subseteq x))<br/>
\end{align*}$$
Note that "$X \subseteq P(S)$" is $\Delta_0$, as:<br/>
$$
\begin{align*}<br/>
X \subseteq P(S) &\iff (\forall x \in X) \, x \subseteq S \\<br/>
&\iff (\forall x \in X)(\forall y \in x) \, y \in S<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.8"></a><br/>
<h2>Exercise 13.8.</h2>
<i>Solution.</i> We first observe that if $(P,<)$, $(Q,<)$ are two $\Delta_0$ linear orders, then the statement "$P$ and $Q$ are order-isomorphic" is $\Sigma_1$, as it can be formulated as:<br/>
$$
\begin{align*}<br/>
\exists f \, (f \text{ is a one-to-one and onto function} \wedge (\forall x \in P)(\forall y \in P)(x < y \iff f(x) < f(y)))<br/>
\end{align*}$$
Thus, given ordinals $\alpha,\beta$, we have:<br/>
$$
\begin{align*}<br/>
x = \alpha + \beta \iff x \text{ is an ordinal} \wedge \text{$(x,\in)$ is order-isomorphic to $(\alpha \times \lbrace 0\rbrace \cup \beta \times \lbrace 1\rbrace,<_\text{lex})$}<br/>
\end{align*}$$
and:<br/>
$$
\begin{align*}<br/>
x = \alpha \cdot \beta \iff x \text{ is an ordinal} \wedge \text{$(x,\in)$ is order-isomorphic to $(\alpha \times \beta,<_\text{lex})$}<br/>
\end{align*}$$
where $<_\text{lex}$ denotes the lexicographical order. This implies that $\alpha + \beta$ and $\alpha \cdot \beta$ are $\Sigma_1$. But observe that:<br/>
$$
\begin{align*}<br/>
x \in \dom(+) \iff x = (u,v) \wedge u \text{ is an ordinal} \wedge v \text{ is an ordinal}<br/>
\end{align*}$$
which is $\Delta_0$. By Lemma 13.10(vii), these two functions are in fact $\Delta_1$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.9"></a><br/>
<h2>Exercise 13.9.</h2>
<i>Solution.</i> Noting that $\max\lbrace \alpha,\beta\rbrace = \bigcup \lbrace \alpha,\beta\rbrace$, it's easy to see that the canonical well-ordering (3.12) is $\Delta_0$. We have:<br/>
$$
\begin{align*}<br/>
x = \Gamma(\alpha,\beta) \iff & x \text{ is an ordinal} \\<br/>
&\wedge \text{$(x,\in)$ is order-isomorphic to $(\lbrace (\xi,\eta) : (\xi,\eta) < (\alpha,\beta)\rbrace,<)$}<br/>
\end{align*}$$
so as we see in the proof of <a href="#ex13.8">Exercise 13.8</a>, $\Gamma$ is $\Sigma_1$. Again, as we see in the proof of <a href="#ex13.8">Exercise 13.8</a>, $\dom(\Gamma) = \boldsymbol{\mathrm{ORD}} \times \boldsymbol{\mathrm{ORD}}$, which is $\Delta_0$, so $\Gamma$ is $\Delta_1$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.10"></a><br/>
<h2>Exercise 13.10.</h2>
<i>Solution.</i> Recall that (and as a result of <a href="https://clementyung.github.io/jech-solutions/chapter-6#lem6.6(i).A">Lemma 6.6(i).A</a>), we have that $x \in \TC(S)$ iff there exists a sequence $x = x_0 \in x_1 \in \dots \in x_n$, and $x_n \in S$. Thus:<br/>
$$
\begin{align*}<br/>
x = \TC(S) \iff (&\forall y \in x) \, \exists f \, (f \text{ is a function} \\<br/>
&\wedge \dom(f) \in \omega \\<br/>
&\wedge f(0) = y \\<br/>
&\wedge f\bb{\bigcup\dom(f)} \in S \\<br/>
&\wedge (\forall n \in \dom(f))(n + 1 \in \dom(f) \to f(n) \in f(n+1)))<br/>
\end{align*}$$
Thus the function $\TC$ is $\Sigma_1$. We have $\dom(\TC) = V$ so by Lemma 13.10(vii), $\TC$ is $\Delta_1$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.11"></a><br/>
<h2>Exercise 13.11.</h2>
<a name="lem13.11.A"></a><br/>
<b>Lemma 13.11.A.</b> The function $\alpha \mapsto V_\alpha$ is $\Delta_1$.<br/>
<br/>
<i>Proof.</i> We have:<br/>
$$
\begin{align*}<br/>
x = V_\alpha \iff &\exists f \, (f \text{ is a function} \\<br/>
&\wedge \dom(f) = \alpha + 1 \\<br/>
&\wedge f(0) = \emptyset \\<br/>
&\wedge f(\alpha) = x \\<br/>
&\wedge (\forall \alpha \in \dom(f))(\alpha + 1 \in \dom(f) \to f(\alpha+1) = P(f(\alpha))) \\<br/>
&\wedge (\forall \alpha \in \dom(f))(\alpha \text{ is a limit ordinal} \to f(\alpha) = \bigcup_{\beta \in \alpha} f(\beta)))<br/>
\end{align*}$$
Thus the function is $\Sigma_1$. The domain of the function is $\boldsymbol{\mathrm{ORD}}$, which is $\Delta_0$, so by Lemma 13.10(vii) the function is $\Delta_1$.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> We have:<br/>
$$
\begin{align*}<br/>
\alpha = \rank(x) \iff x \in V_{\alpha+1} \wedge x \notin V_\alpha<br/>
\end{align*}$$
which is $\Delta_1$ by <a href="#lem13.11.A">Lemma 13.11.A</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.12"></a><br/>
<h2>Exercise 13.12.</h2>
<i>Solution.</i> We have $X$ is countable iff:<br/>
$$
\begin{align*}<br/>
\exists f \,(f \text{ is a one-to-one function} \wedge \dom(f) \in \omega \wedge \ran(f) = X)<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.13"></a><br/>
<h2>Exercise 13.13.</h2>
<i>Solution.</i> See <a href="https://clementyung.github.io/jech-solutions/chapter-12#ex12.6(i)">Exercise 12.6(i)</a> for that $\vert X\vert  \leq \vert Y\vert $ is $\Sigma_1$. Note that $\vert X\vert  = \vert Y\vert  \iff \vert X\vert  \leq \vert Y\vert  \wedge \vert Y\vert  \leq \vert X\vert $, so it's also $\Sigma_1$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.14"></a><br/>
<h2>Exercise 13.14.</h2>
<i>Solution.</i> As we see in the remark after Lemma 13.13, given a $\Delta_0$ formula $\varphi$ we have:<br/>
$$
\begin{align*}<br/>
\models_0 \varphi[a_1,\dots,a_k] \iff \varphi \in \Delta_0 \wedge \exists M \, (M \text{ is transitive} \wedge (M,\in) \models \varphi[a_1,\dots,a_k])<br/>
\end{align*}$$
This is allowed as $\Delta_0$ formulas are always absolute. Note that "$M$ is transitive" is $\Delta_0$ by Lemma 12.10. Furthermore, we have $(M,\in) \models \varphi[a_1,\dots,a_k] \iff \varphi^M[a_1,\dots,a_k]$, and the latter is always $\Delta_0$ as all the quantifiers are bounded. Finally, by $\varphi \in \Delta_0$ we mean "$\varphi$ is a $\Delta_0$ formula", which is $\Delta_0$ as $\Delta_0$ is here viewed as a countable set in the universe (under suitable encoding of formulas). Hence $\models_0$ is $\Sigma_1$.<br/>
<br/>
The same can also be done for $\Sigma_1$ (and hence $\Pi_1$ formulas): If $\exists y \, \varphi(x,y)$ holds, where $\varphi \in \Delta_0$, then let $M$ be a transitive set containing $x$, and we have that $(M,\in) \models \exists y \, \varphi(x,y)$. Thus $\models_1$ is also $\Sigma_1$.<br/>
<br/>
Now suppose $\models_n$ is $\Sigma_n$. Then, as written in the book, we have:<br/>
$$
\begin{align*}<br/>
\models_{n+1} (\exists x \, \varphi)[x,a_1,\dots,a_k] \iff \varphi \in \Pi_n \wedge \exists a \, (\neg\models_n (\neg\varphi)[a,a_1,\dots,a_k])<br/>
\end{align*}$$
so $\models_{n+1}$ is $\Sigma_{n+1}$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.15"></a><br/>
<h2>Exercise 13.15.</h2>
<i>Solution.</i> This follows from that $\Sigma_0 = \Delta_0$ formulas are absolute across all transitive sets by Lemma 12.9.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.16"></a><br/>
<h2>Exercise 13.16.</h2>
<i>Solution.</i> By the Reflection Principle there exists a set $M \supseteq M_0$ that reflects $\models_n$. Then for all $\Sigma_n$ formulas $\varphi$ we have $\models_n \varphi$ iff $(\models_n \varphi)^M$ iff $(M,\in) \models_n \varphi$, so $M \prec_{\Sigma_n} V$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.17"></a><br/>
<h2>Exercise 13.17.</h2>
<a name="lem13.17.A"></a><br/>
<b>Lemma 13.17.A.</b> Assume $V = L$. If $\kappa$ is an infinite cardinal, then $H_\kappa = L_\kappa$ (see <a href="https://clementyung.github.io/jech-solutions/chapter-12#ex12.13">Exercise 12.13</a> for definition of $H_\kappa$).<br/>
<br/>
<i>Proof.</i> Clearly $V_\omega = H_\omega = L_\omega$ (this does not require $V = L$). If $\kappa$ is limit, then $H_\kappa = \bigcup_{\lambda < \kappa} H_\lambda = \bigcup_{\lambda < \kappa} L_\lambda = L_\kappa$, so it remains to show the successor cardinal case.<br/>
<br/>
<u>$L_\kappa \subseteq H_\kappa$:</u> Let $X \in L_\kappa$, so $X \in L_\alpha$ for some ordinal $\alpha < \kappa$. Since $L_\alpha$ is transitive, we have $\TC(X) \subseteq L_\alpha$. By <a href="#ex13.19">Exercise 13.19</a>, we have that $\vert X\vert  \leq \vert L_\alpha\vert  = \vert \alpha\vert  < \kappa$, so $X \in H_\kappa$. We do not require $V = L$ here.<br/>
<br/>
<u>$H_\kappa \subseteq L_\kappa$:</u> Let $X \in H_\kappa$, and suppose $\kappa = \lambda^+$. Then $\vert \TC(X)\vert  \leq \lambda$. Since $V = L$, $X \in L_\delta$ for some $\delta$, so $\TC(\lbrace X\rbrace) \subseteq L_\delta$. Then $\vert \TC(\lbrace X\rbrace)\vert  \leq \vert L_\delta\vert  = \vert \delta\vert  \leq \lambda$, so by L&ouml;wenheim-Skolem Theorem there exists an elementary submodel $M \prec (L_\delta,\in)$ of size $\lambda$ such that $\TC(\lbrace X\rbrace) \subseteq M$. Let $M'$ be the transitive collapse of $M$. Since $\TC(\lbrace X\rbrace) \subseteq M$ and $\TC(\lbrace X\rbrace)$ is transitive, $\TC(\lbrace X\rbrace) \subseteq M'$. By G&ouml;del's Condensation Lemma, we have that $M' = L_\gamma$ for some ordinal $\gamma$. Since $\vert M\vert  = \vert \gamma\vert  = \lambda$, we have that $\gamma < \lambda^+$. Thus $X \in \TC(\lbrace X\rbrace) \subseteq L_\gamma \subseteq L_{\lambda^+}$.<p align="right">$\blacksquare$</p><br/>
<br/>
<a name="lem13.17.B"></a><br/>
<b>Lemma 13.17.B.</b> For regular uncountable cardinals $\kappa$, we have that:
<ol>
<li> $H_\kappa \models$ All sets are of cardinality $<\kappa$.</li>
<li> $L_{\kappa^L} \models$ All sets are of cardinality $<\kappa^L$.</li>
</ol>
<br/>
<i>Proof.</i> 
<ol>
<li> Let $X \in H_\kappa$, so $\vert \TC(X)\vert  < \kappa$. Let $\lambda < \kappa$ be a cardinal such that there exists a one-to-one function $f$ on $X$ into $\lambda$. But as we saw in the proof that $H_\kappa \models \AC$ in <a href="https://clementyung.github.io/jech-solutions/chapter-12#ex12.13">Exercise 12.13</a>, we in fact have $f \in H_\kappa$ (and that $\lambda \in H_\kappa$). Thus $H_\kappa \models \vert X\vert  < \lambda$.</li>
<li> By (i) and <a href="#lem13.17.A">Lemma 13.17.A</a>, we have that $L \models (L_{\kappa^L} \models$ All sets are of cardinality $<\kappa^L))$. But the sentence "$L_{\kappa^L} \models$ All sets are of cardinality $<\kappa^L$" is $\Delta_0$ (as all quantifiers are bounded), so it holds (in $V$).</li>
</ol><p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Let $X \in M$. Now $M \subseteq L_{\omega_1^L}$, so by <a href="#lem13.17.B">Lemma 13.17.B</a> there exists an $f \in (L_{\omega_1^L},\in)$ that is a one-to-one mapping of $\omega$ onto $X$ (note that $\omega^L = \omega$). Then $f$ is definable from $X$ in $L_{\omega_1^L}$, and since $M \prec L_{\omega_1^L}$ we have that $f$ is definable from $X$ in $M$. Thus $f \in M$, so $f(n) \in M$ for all $n$. Therefore $X \subseteq M$.<br/>
<br/>
By G&ouml;del's Condensation Lemma 13.17, $M = L_\alpha$ for some $\alpha < \omega_1$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.18"></a><br/>
<h2>Exercise 13.18.</h2>
<i>Solution.</i> Let $\gamma \in \omega_1^L \cap M$. Then again like the proof of <a href="#ex13.17">Exercise 13.17</a>, there exists an $f \in (L_{\omega_2^L},\in)$ that is a one-to-one mapping of $\omega$ onto $\gamma$. $f$ is definable from $\gamma$ in $L_{\omega_2}^L$, so it is also definable from $\gamma$ in $M$. Thus $\gamma \subseteq M$. Thus $\omega_1^L \cap M$ is a transitive set of ordinals, hence an ordinal (and of course $\alpha \leq \omega_1$, as $\omega_1^L \leq \omega_1$).<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.19"></a><br/>
<h2>Exercise 13.19.</h2>
<a name="lem13.19.A"></a><br/>
<b>Lemma 13.19.A.</b> Given an infinite set $M$, we have $\vert \func{def}(M)\vert  = \vert M\vert $.<br/>
<br/>
<i>Proof.</i> Clearly $\lbrace a\rbrace \in \func{def}(M)$ for all $a \in M$, so $\vert \func{def}(M)\vert  \geq \vert M\vert $, On the other hand, consider the following map on $[M]^{<\omega} \times \mathit{Form}$ as follows:<br/>
$$
\begin{align*}<br/>
((a_1,\dots,a_n),\varphi) \mapsto \lbrace x \in M : (M,\in) \models \varphi[x,a_1,\dots,a_n]\rbrace<br/>
\end{align*}$$
This map is onto by definition, so we have $\vert \func{def}(M)\vert  \leq \vert M\vert ^{<\omega} \cdot \aleph_0 = \vert M\vert $.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Note that since $\alpha \subseteq L_\alpha$, clearly $\vert L_\alpha\vert  \geq \vert \alpha\vert $. We prove the equality. We have $\vert L_\omega\vert  = \vert V_\omega\vert  = \omega$, and if $\alpha$ is a limit ordinal then:<br/>
$$
\begin{align*}<br/>
\vert L_\alpha\vert  = \mod{\bigcup_{\beta<\alpha} L_\beta} \leq \sum_{\beta < \alpha} \vert L_\beta\vert  = \vert \alpha\vert  \cdot \sup_{\beta < \alpha} \vert \beta\vert  = \vert \alpha\vert <br/>
\end{align*}$$
For the successor case, we have by <a href="#lem13.19.A">Lemma 13.19.A</a> that $\vert L_{\alpha+1}\vert  = \vert L_\alpha\vert  = \vert \alpha\vert  = \vert \alpha + 1\vert $.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.20"></a><br/>
<h2>Exercise 13.20.</h2>
<i>Solution.</i> We work in $L$. Since $X \subseteq \alpha$, we have that $\TC(X)$ is an ordinal and $\TC(X) \leq \alpha$. Let $\beta := \vert \alpha\vert ^+$, so $\vert \TC(X)\vert  \leq \vert \alpha\vert  < \beta$. Therefore $X \in H_\beta$, but $H_\beta = L_\beta$ by <a href="#lem13.17.A">Lemma 13.17.A</a>, so the assertion follows.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.21"></a><br/>
<h2>Exercise 13.21.</h2>
<i>Solution.</i> For $X \in L$, we let $o(X)$ denote the order-type of $X$ under the canonical well-ordering $<$.<br/>
<br/>
We note that $P(\omega) \cap L \subseteq L_{\omega_1^L}$ by <a href="#ex13.20">Exercise 13.20</a>. This implies that $P(\omega) \cap L \in L_{\omega_1^L + 1}$, as:<br/>
$$
\begin{align*}<br/>
P(\omega) \cap L = \lbrace x \in L_{\omega_1^L} : &(\exists \varphi \in \mathit{Form})(\exists \alpha < \omega_1) \\<br/>
&(\exists a_1,\dots,a_n \in L_\alpha)(y \in x \leftrightarrow (L_\alpha,\in) \models \varphi[y,a_1,\dots,a_n])\rbrace<br/>
\end{align*}$$
Note that $\mathit{Form} \in L_{\omega+1}$ as the G&ouml;del numbering of formulas may be done without parameters.<br/>
<br/>
Since there is a definable (without parameters) function from $P(\omega)$ onto $\R$, we have that $\R \cap L \in L_{\omega_1^L+1}$. By Lemma 13.19, we have that $L_{\omega_1^L+\omega}$ witnesses the order-type of $\R^L$, so $o(\R^L) \in L_{\omega_1^L+\omega}$. But since for all $\alpha < \omega_1$ there exists $x \in \R^L$ such that $x \notin L_\alpha$ (since $L$ thinks that $L_\alpha$ is countable but $P^L(x)$ is uncountable), so $o(\R^L)$ must be an unbounded subset of an ordinal of uncountable cofinality. Therefore $o(\R^L) = \omega_1^L$. necessarily.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.22"></a><br/>
<h2>Exercise 13.22.</h2>
<i>Solution.</i> This follows from <a href="#lem13.17.A">Lemma 13.17.A</a> and <a href="https://clementyung.github.io/jech-solutions/chapter-12#ex12.13">Exercise 12.13</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.23"></a><br/>
<h2>Exercise 13.23.</h2>
<a name="lem13.23.A"></a><br/>
<b>Lemma 13.23.A.</b> If $\kappa = \beth_\kappa$, then $V_\kappa = H_\kappa$.<br/>
<br/>
<i>Proof.</i> Suppose $\rank(x) = \alpha < \kappa$. Then $\TC(\lbrace x\rbrace) \subseteq V_\alpha$, so $\vert \TC(\lbrace x\rbrace)\vert  \leq \vert V_\alpha\vert  = \beth_\alpha < \beth_\kappa = \kappa$. Conversely, if $\vert \TC(\lbrace x\rbrace)\vert  < \kappa$, then $\vert \lbrace \rank(z) : z \in \TC(\lbrace x\rbrace)\rbrace\vert  < \kappa$. But $\lbrace \rank(z) : z \in \TC(\lbrace x\rbrace)\rbrace$ is an ordinal (say $\alpha$), so $\rank(x) \leq \alpha + 1 < \kappa$. Thus $x \in V_\kappa$ (this converse direction holds for all cardinals).<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Note that $V_\kappa^L = V_\kappa \cap L$ by <a href="#ex13.6">Exercise 13.6</a>. By <a name="#6#lem6.3.A">Lemma 6.3.A</a>, <a href="#lem13.17.A">Lemma 13.17.A</a> and <a href="#lem13.23.A">Lemma 13.23.A</a>, we have that $V_\kappa^L = H_\kappa^L = L_\kappa^L = L_\kappa$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.24"></a><br/>
<h2>Exercise 13.24.</h2>
<i>Solution.</i> As in the hint and Lemma 13.19, we have that $h_\varphi$ is well defined for all formulas $\varphi$. Given $X \subseteq L_\delta$, let $M \prec (L_\delta,\in)$ be the Skolem hull of $X$. We shall show that if $N \prec (L_\delta,\in)$ and $X \subseteq N$, then $M \subseteq N$.<br/>
<br/>
Let $a \in M$. If $a \in X$, then $a \in N$ as $X \subseteq N$. Otherwise, $a = h_\varphi(x_1,\dots,x_n)$ for some $x_1,\dots,x_n \in X$. Thus:<br/>
$$
\begin{align*}<br/>
M \models \exists x \, (x \text{ is the $<_\delta$-least element such that } \varphi[x,x_1,\dots,x_n]))<br/>
\end{align*}$$
Since $M$ is elementarily equivalent to $N$, we have that $N$ satisfies the same formula. Since such an $x$ is unique, which is $a$, we have that $a \in N$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.25"></a><br/>
<h2>Exercise 13.25.</h2>
<i>Solution.</i> Let $\c{S_\alpha : \alpha < \omega_1}$ be a $\diamondsuit$-sequence, and define $S_X$, $\F$ as in the hint. Then $S_X$ is stationary for all $X \subseteq \omega_1$. Given $X,Y \subseteq \omega_1$, if $S_X \cap S_Y$ is unbounded, then in particular we have $\lbrace \alpha : X \cap \alpha = Y \cap \alpha\rbrace$ is unbounded, so $X = Y$. Therefore, if $S_X \neq S_Y$ (so $X \neq Y$), we have that $S_X \cap S_Y$ is a bounded subset of $\omega_1$, therefore at most countable. This also implies that $\vert \F\vert  = 2^{\aleph_1}$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.26"></a><br/>
<h2>Exercise 13.26.</h2>
<a name="lem13.26.A"></a><br/>
<b>Lemma 13.26.A.</b> Suppose $V = L[A]$ and $\kappa$ is the least cardinal such that $A \subseteq L_\kappa[A]$. Then for cardinals $\lambda$, we have $2^\lambda = \lambda^+$.<br/>
<br/>
<i>Proof.</i> We first note that the proof for <a href="#lem13.19.A">Lemma 13.19.A</a> can be repeated with $\func{def}(M)$ replaced with $\func{def}_A(M)$. Thus, <a href="#ex13.19">Exercise 13.19</a> holds for $L[A]$. Note also that $L_\alpha[A]$ is transitive for all $\alpha$ - $L_0[A]$ is trivially transitive, and if $L_\alpha[A]$ is transitive then given $X \in L_{\alpha+1}[A]$ and $x \in X$ (note that $x \in L_\alpha[A]$), we have $x = \lbrace y \in L_{\alpha+1}[A] : y \in x\rbrace \in L_{\alpha+1}[A]$.<br/>
<br/>
Let $X \in P(\lambda) \cap L[A]$, so $X \in L_\alpha[A]$ for some ordinal $\alpha \geq \lambda$. By L&ouml;wenheim Skolem Theorem we obtain an elementary submodel $M \prec L[A]$ such that $\lambda \subseteq M$, $A \subseteq M$, $\vert M\vert  = \lambda$. By the relativised version of Condensation Lemma, if $M'$ is the transitive collapse of $M$ then $M'= L_\gamma[\pi(A \cap M)]$ for some $\gamma$. But $\TC(\lbrace A\rbrace) \subseteq M$ so $\pi(A \cap M) = A$. Thus $A \in L_\gamma[A] \subseteq L_{\lambda^+}[A]$ (note that $\vert \gamma\vert  = \lambda$), so $P(\lambda) \cap L[A] \subseteq L_{\lambda^+}[A]$.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> We note that since $\omega_1 \subseteq L_{\omega_1}$, by <a href="#lem13.26.A">Lemma 13.26.A</a> we have that $2^\lambda = \lambda^+$ for $\lambda \geq \aleph_1$. Thus, to show that $\GCH$ holds it remains to show that $\CH$ holds.<br/>
<br/>
Let $X \subseteq \omega$, so $X \in L_{\omega+1}[A]$. Let $M \prec L_{\omega_1}[A]$ such that $\TC(\lbrace X\rbrace) \subseteq M$ and $M$ is countable. Then its transitive collapse $M' = L_\alpha[A \cap M]$, but since $A \cap M$ is a countable subset of ordinals $< \omega_1$, there exists a countable ordinal $\xi$ such that $M' = L_\alpha[A \cap \xi]$. We have $X \in M'$, and since $A \cap \xi \in L[A]$ we have that $L_\alpha[A \cap \xi] \subseteq L_\alpha[A] \subseteq L_{\omega_1}[A]$. Thus $P(\omega) \subseteq L_{\omega_1}[A]$ so $\CH$ holds.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.27"></a><br/>
<h2>Exercise 13.27.</h2>
<a name="lem13.27.A"></a><br/>
<b>Lemma 13.27.A.</b> If $B \in L[A]$ then $L[B] \subseteq L[A]$.<br/>
<br/>
<i>Proof.</i> Let $\alpha$ be the least ordinal such that $B \in L_\alpha[A]$. Then by transfinite induction, we see that $L_{\omega+\beta}[B] \subseteq L_{\alpha+\beta}[A]$ for all ordinals $\beta$, so $L[B] \subseteq L[A]$.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Assume $V = L[X]$ and $X \in L[X]$. Let $(\theta,E)$, where $\theta$ is an ordinal and $E \subseteq \theta \times \theta$ is a relation such that $(\theta,E)$ is isomorphic to $\TC(\lbrace X\rbrace)$. Let $A = \Gamma"(E) \subseteq \boldsymbol{\mathrm{ORD}}$. We note that $\Gamma$ is a mapping definable without parameters, so $\Gamma \in L$.<br/>
<br/>
We now show that $L[A] = L[X]$. We see that $\theta,E \in L[X]$, $\Gamma \in L \subseteq L[X]$ so $A = \Gamma"(E) \in L[X]$. Therefore $L[A] \subseteq L[X]$ by \ref{lem13.27.A}. Conversely, since $E = \Gamma_{-1}(A) \in L[A]$, we have $\theta = \dom(E) \cup \ran(E) \in L[A]$. Since $E$ is a well-founded relation, in $L[A]$ there exists a transitive set $Y$ such that $(\theta,E)$ is isomorphic to $(Y,\in)$.<br/>
<br/>
<b>Claim.</b>. The transitive set $Y$ is unique.<br/>
<br/>
<i>Proof.</i> Suppose $Y'$ is another transitive set such that $(\theta,E)$ is isomorphic to $(Y',\in)$. Let $f : Y \to \theta$ and $g : Y' \to \theta$ be the isomorphisms. For each ordinal $\alpha$, let $Y_\alpha := \lbrace x \in Y : \rank(x) = \alpha\rbrace$, and similarly for $Y_\alpha'$. We shall induct on $\alpha$ that $Y_\alpha = Y_\alpha'$, and $f\restrictedto Y_\alpha = g\restrictedto Y_\alpha'$.
<ol>
<li> $Y_0 = \emptyset = Y_0'$, and trivially $f\restrictedto Y_0 = g\restrictedto Y_0'$.</li>
<li> Suppose $Y_\alpha = Y_\alpha'$ and $f\restrictedto Y_\alpha = g\restrictedto Y_\alpha'$. Let $x \in Y_{\alpha+1}$, and since $Y$ is transitive we have $x \subseteq Y_\alpha$ (since $y \in x \implies \rank(y) < \rank(x) = \alpha$). Let:<br/>
$$
\begin{align*}<br/>
x' := \lbrace (g \circ f^{-1})(y) : y \in x\rbrace \in Y'<br/>
\end{align*}$$
But since $\rank(y) = \alpha$ for all $y \in x$, and rank is preserved between isomorphisms, we have that $(g \circ f^{-1})(y) = y$ for all $y \in x$. Thus $x' = x$, and since $\rank(x) = \alpha + 1$ we have $x \in Y_{\alpha+1}$. Therefore $Y_{\alpha+1} \subseteq Y_{\alpha+1}$, and by symmetry of argument we have that equality holds.</li>
<li> If $\alpha$ is limit, we have $Y_\alpha = \bigcup_{\beta<\alpha} Y_\beta = \bigcup_{\beta<\alpha} Y_\beta' = Y_\alpha'$.</li></ol>
Therefore, if $\rank(Y) = \alpha$, then $Y = \bigcup_{\beta<\alpha} Y_\beta = \bigcup_{\beta<\alpha} Y_\beta' = Y'$.<p align="right">$\blacksquare$</p><br/>
Note that the claim above is a theorem in $L[X]$ (recall we assume $V = L[X]$), not $L[A]$. But in $L[X]$ we already know that $(\TC(\lbrace X\rbrace),\in)$ is isomorphic to $(\theta,E)$, so we must have $\TC(\lbrace X\rbrace) = Y \in L[A]$. Finally, since $X$ is the element of $\TC(\lbrace X\rbrace)$ of the largest rank, we have that $X \in L[A]$. Therefore $L[X] \subseteq L[A]$.<br/>
<br/>
We have thus proved that $L[X] \models (L[X] = L[A])$. But since relative constructibility is $\Delta_1$ and hence absolute we have:<br/>
$$
\begin{align*}<br/>
L[X] = L^{L[X]}[X] = L^{L[X]}[A] = L[A]<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.28"></a><br/>
<h2>Exercise 13.28.</h2>
<i>Solution.</i> Let $f : \omega \to \alpha$ be one-to-one and onto. Define $W \subseteq \omega \times \omega$ by stipulating that $n \, W \, m$ iff $f(n) \in f(m)$. Then $W$ is a well-ordering of order-type $\alpha$. Since "$W$ is a well-ordering of order-type $\alpha$" is $\Delta_0$ relative to $\alpha$, we have that $L[W] \models$ "$W$ is a well-ordering of order-type $\alpha$", so $L[W] \models \alpha$ is countable.<br/>
<br/>
Let $A = \Gamma(W) \subseteq \omega$, where $\Gamma$ is the canonical well-ordering of $\boldsymbol{\mathrm{ORD}}^2$ (recall that $\Gamma(\omega_\alpha \times \omega_\alpha) = \omega_\alpha$ for all ordinals $\alpha$). Since $\Gamma$ is definable without parameters, we have that $A \in L[W]$ and $W \in L[A]$. Thus $L[A] = L[W]$. Note that $\AC$ is not used in this proof.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.29"></a><br/>
<h2>Exercise 13.29.</h2>
<i>Solution.</i> By <a href="#ex13.28">Exercise 13.28</a> we may let $A \subseteq \omega$ be such that $\alpha$ is countable in $L[A]$. For $\alpha \leq \beta < \omega_1$, $L \models$ there exists a one-to-one function $f$ from $\beta$ onto $\alpha$. Since $L \subseteq L[A]$, it follows that $\beta$ is countable in $L[A]$ for all $\alpha \leq \beta < \omega_1$. Of course if $\beta < \alpha$ then $\beta$ is countable in $L[A]$, so $\omega_1^{L[A]} \leq \sup_{\alpha<\omega_1} \alpha = \omega_1$. Note that $\AC$ is not used in this proof.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.30"></a><br/>
<h2>Exercise 13.30.</h2>
<i>Solution.</i> By <a href="#ex13.28">Exercise 13.28</a>, for each $\alpha < \omega_1$ there exists $A_\alpha \subseteq \omega$ such that $\alpha$ is countable in $L[A_\alpha]$. Let $F$ be the function $\alpha \mapsto A_\alpha$ (this is a choice function, so $\AC$ is required), and let $A = \bigcup_{\alpha < \omega_1} \lbrace \alpha\rbrace \times F(\alpha) \subseteq \omega_1 \times \omega_1$. Then $L[A_\alpha] \subset L[A]$, and since "$X$ is countable" is $\Sigma_1$ (see <a href="#ex13.12">Exercise 13.12</a>) hence upward absolute, $\alpha$ is countable in $L[A]$. Thus $\omega_1^{L[A]} = \omega_1$.<br/>
<br/>
To ensure that $A \subseteq \omega_1$, we simply consider the canonical well-ordering $\Gamma$ on $\omega_1 \times \omega_1$. Then $L[\Gamma(A)] = L[A]$, as we argued in <a href="#ex13.29">Exercise 13.29</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.31"></a><br/>
<h2>Exercise 13.31.</h2>
<i>Solution.</i> Since $L \models \GCH$, we have that in $L$, $\omega_2$ is inaccessible iff it is a regular limit cardinal (weakly inaccessible). By Lemma 13.13, "$\alpha$ is a regular cardinal" is $\Pi_1$, so we have that $\omega_2$ is a regular cardinal in $L$. Therefore, if $\omega_2$ is not inaccessible in $L$, then $\omega_2$ is a successor cardinal in $L$.<br/>
<br/>
Let $\alpha < \omega_2$ be an ordinal such that $\omega_2 = \alpha^+$ in $L$. By repeating the proof in <a href="#ex13.28">Exercise 13.28</a>, one may obtain an $A \subseteq \omega_1$ such that $\vert \alpha\vert  = \omega_1^{L[A]}$ in $L[A]$. By <a href="#ex13.30">Exercise 13.30</a>, one obtain another $B \subseteq \omega_1$ such that $\omega_1 = \omega_1^{L[B]}$ ($\AC$ is used here). Thus we have that $\omega_1^{L[A \times B]} = \omega_1$ and $\omega_2^{L[A \times B]} = \omega_2$. Now convert $A \times B \subseteq \omega_1 \times \omega_1$ to a subset of $\omega_1$ using the canonical well-ordering $\Gamma$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.32"></a><br/>
<h2>Exercise 13.32.</h2>
<i>Solution.</i> Given a fixed ordinal $\alpha$, for $\beta \leq \alpha$ we observe that $\func{def}_A(L_\beta[A]) = \func{def}_{A \cap L_\alpha[A]}(L_\beta[A])$, so we have that $L_\beta[A] = L_\beta[A \cap L_\alpha[A]]$ (see also the proof of Lemma 13.23). Thus for any ordinal $\alpha$ we have:<br/>
$$
\begin{align*}<br/>
L[A] &= \bigcup_{\alpha \in \boldsymbol{\mathrm{ORD}}} L_\alpha[A] \\<br/>
&= \bigcup_{\alpha \in \boldsymbol{\mathrm{ORD}}} L_\alpha[A \cap L_\alpha[A]] \\<br/>
&= \bigcup_{\alpha \in \boldsymbol{\mathrm{ORD}}} L_\alpha[\bar{A} \cap L_\alpha[A]] \\<br/>
&= \bigcup_{\alpha \in \boldsymbol{\mathrm{ORD}}} L_\alpha[\bar{A}] \\<br/>
&= L[\bar{A}]<br/>
\end{align*}$$
We first show that $L[A]$ is an inner model of $\ZF$. By Theorem 13.9, it suffices to show that it is closed under G&ouml;del operations and is almost universal. Closure under G&ouml;del operations follow immediately from the way $L[A]$ is constructed (see (13.20), (13.21) and (13.22)). For almost universality, given a set $X \subseteq M$ let $\alpha := \sup\lbrace \min\lbrace \beta \in \boldsymbol{\mathrm{ORD}} : x \in L_\beta[A]\rbrace : x \in X\rbrace$. Then clearly $X \subseteq L_{\alpha+1}[A]$ and $L_{\alpha+1}[A] \in L[A]$.<br/>
<br/>
$L[A]$ satisfies $\AC$ because we may define a global well-ordering $<_{L[A]}$ similar to $<_L$ in Theorem 13.18. Indeed, for ordinals $\alpha$ we let:<br/>
$$
\begin{gather*}<br/>
W_0^\alpha := L_\alpha[A] \cup \lbrace L_\alpha[A]\rbrace \cup \lbrace A \cap L_\alpha[A]\rbrace \\<br/>
W_{n+1}^\alpha := \lbrace G_i(X,Y) : X,Y \in W_n^\alpha, i = 1,\dots,10\rbrace<br/>
\end{gather*}$$
and the remaining steps are verbatim to that of $<_L$.<br/>
<br/>
Finally, suppose $M$ is another inner model of $\ZF$ such that $V_\alpha^M \cap A \in M$ for all $\alpha$. Of course $L[A]$ is one such model as $A \cap L[A] \in L[A]$. We show inductively that $L_\alpha[A] \in M$ for all $\alpha \geq \omega$. Since all finite sets are $\Delta_0$ and $M$ is an inner model, we have $L_\omega[A] = V_\omega = V_\omega^M \in M$. If $\alpha$ is a limit ordinal, then we have that $L_\alpha^M[A] \in M$ and $L_\alpha^M[A] = \bigcup_{\beta<\alpha} L_\beta^M[A] = \bigcup_{\beta<\alpha} L_\beta[A] = L_\alpha[A]$. Now suppose $L_\alpha[A] \in M$. By Theorem 13.9, $M$ is closed under G&ouml;del operations. Since $A \cap V_\alpha^M \in M$ and clearly $L_\alpha[A] \subseteq V_\alpha^M$, we have that $A \cap L_\alpha[A] \in M$. Thus:<br/>
$$
\begin{align*}<br/>
L_{\alpha+1}[A] = \func{def}_A(L_\alpha[A]) = \cl(L_\alpha[A] \cup \lbrace L_\alpha[A]\rbrace \cup \lbrace A \cap L_\alpha[A]\rbrace) \cap P(L_\alpha[A]) \in M<br/>
\end{align*}$$
Therefore $L[A] \subseteq M$ by transitivity of $M$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.33"></a><br/>
<h2>Exercise 13.33.</h2>
<i>Solution.</i> By <a href="#lem13.33.A">Lemma 13.33.A</a>, there exists a global well-order on $V$. This yields a one-to-one correspondence between $V$ and $\boldsymbol{\mathrm{ORD}}$, so there exists a class relation $E$ such that $(V,\in)$ is isomorphic to $(\boldsymbol{\mathrm{ORD}},E)$. Let $A := \Gamma"(E)$. Following the same argument in <a href="#ex13.27">Exercise 13.27</a>, we observe that $V = L[A]$ - indeed, since $L[A]$ witnesses the class $A$ (as $L[A]$ contains all the ordinals) and $\Gamma$ is definable without parameters, we obtain a transitive class $W \subseteq L[A]$ such that $(W,\in)$ is isomorphic to $(\boldsymbol{\mathrm{ORD}},E)$ in $L[A]$. But the uniqueness of $W$ (witnessed in $V$) implies that we must have $V = W$, so $V = L[A]$ necessarily.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.34"></a><br/>
<h2>Exercise 13.34.</h2>
<i>Solution.</i> Define a cumulative hierarchy as follows:
<ol>
<li> $L_0(M,X) := \emptyset$.</li>
<li> $L_{\alpha+1}(M,X) := \func{def}_{M \cup \lbrace X\rbrace}(L_\alpha(M,X)) \cup ((M \cup \lbrace X\rbrace) \cap V_\alpha)$.</li>
<li> $L_\alpha(M,X) := \bigcup_{\beta<\alpha} L_\beta(M,X)$, if $\alpha$ is  limit.</li>
<li> $L(M,X) := \bigcup_{\alpha \in \boldsymbol{\mathrm{ORD}}} L_\alpha(M,X)$.</li>
</ol>
Clearly $M \subseteq L(M,X)$ as $V_\alpha^M = V_\alpha \cap M \subseteq L_\alpha(M,X)$ for all $\alpha$, and if $X \in V_\alpha$ then $X \in L_\alpha(M,X)$. The proof that $L(M,X)$ is closed under G&ouml;del operations and is almost universal is almost identical to that of $L[A]$ and $L(A)$ (see also <a href="#ex13.32">Exercise 13.32</a>). Thus, $L(M,X)$ is an inner model of $\ZF$. Finally, if $N$ is a transitive model of $\ZF$ such that $N$ contains $M$ as a subclass (so $M \cap V_\alpha \in N$ for all $\alpha$) and $X \in N$, then since $N$ is closed under G&ouml;del operations one may prove by transfinite induction that $L_\alpha(M,X) \in N$ for all ordinals $\alpha$. Thus $L(M,X)$ is indeed the least such model.<br/>
<br/>
Now suppose further that $M \models \AC$. We shall show that $L_\alpha(M,X)$ has a well-ordering $<_\alpha$ for all $\alpha$, so since $L(M,X)$ is transitive it implies that every set is well-orderable. $L_0(M,X) = \emptyset$ is no problem, and if $\alpha$ is limit we let $<_\alpha \; := \bigcup_{\beta<\alpha} <_\beta$. Now suppose $<_\alpha$ is well-defined. Let:<br/>
$$
\begin{gather*}<br/>
W_0^\alpha := L_\alpha(M,X) \cup \lbrace L_\alpha(M,X)\rbrace \cup \lbrace (M \cap \lbrace X\rbrace) \cap L_\alpha(M,X)\rbrace \\<br/>
W_{n+1}^\alpha := \lbrace G_i(X,Y) : X,Y \in W_n^\alpha, i = 1,\dots,10\rbrace<br/>
\end{gather*}$$
We define $<_{\alpha+1}'$ in the same way as (13.15) (which is an end-extension of $<_\alpha$). Now since $M \cap V_\alpha = V_\alpha^M \in M$ and $M \models \AC$, there exists a well-order in $M \subseteq L(M,X)$, $<_\alpha"$, on $M \cap V_\alpha$. Thus, we may define $<_{\alpha+1}$ by having $<_\alpha"$ end-extending $v_{\alpha+1}'$, then setting $X$ as the last element if $X \in L_{\alpha+1}(M,X) - L_\alpha(M,X)$. Then $<_{\alpha+1}$ is easily seen to be a well-order of $L_{\alpha+1}(M,X)$. Note that this does not imply that $L(M,X)$ satisfies Axiom of Global Choice, but if we further assume that $M$ satisfies Axiom of Global Choice, then so does $L(M,X)$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.35"></a><br/>
<h2>Exercise 13.35.</h2>
<i>Solution.</i> We first note that if $X$ is a set and $X \in \OD$, then $X \subseteq V_\beta$ for some $\beta$. Thus we may write $X = \lbrace u \in V_\beta : \varphi^{V_\beta}(u,\alpha)\rbrace$ (note that using the canonical well-ordering, we may replace $\varphi(u,\alpha_1,\dots,\alpha_n)$ with just $\varphi(u,\alpha)$ - see also <a name="#3#lem3.6.A">Lemma 3.6.A</a>). Let $\gamma := \Gamma(\beta,\alpha)$. Now $X \in V_{\gamma+1}$, and so we have that $X = \lbrace u \in V_{\gamma+1} : \psi(u,\gamma)\rbrace$ for some formulas $\psi$, as $\alpha,\beta$ may be obtained from $\gamma$ using $\Gamma$, which is definable without parameters. But observe further that $\gamma$ is the largest ordinal in $V_{\gamma+1}$, so $\gamma \in V_{\gamma+1}$ is also definable without parameters in $V_{\gamma+1}$. Thus $X$ is definable in $V_{\gamma+1}$ without parameters.<br/>
<br/>
Conversely, suppose $X$ is definable in some $V_\gamma$, so $X = \lbrace u \in V_\gamma : \varphi(u)\rbrace$ for some formula $\varphi$. Let $\psi(u,\gamma)$ denote the formula that $\varphi(u)$ and $\rank(u) < \gamma$. Then $X = \lbrace u : \psi(u,\gamma)\rbrace$, so $X \in OD$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.36"></a><br/>
<h2>Exercise 13.36.</h2>
<i>Solution.</i> Suppose $F = \lbrace (\alpha,x) : \varphi(\alpha,x)\rbrace$ for some formula $\varphi$. Let $x \in \ran(F)$. If $x = F(\alpha)$, we shall show that:<br/>
$$
\begin{align*}<br/>
x = \lbrace y : \exists z \, (\varphi(\alpha,z) \wedge y \in z)\rbrace<br/>
\end{align*}$$
If $y \in x$, then since $\varphi[\alpha,x]$ we have in particular that $\exists z \, (\varphi(\alpha,z) \wedge y \in z)$. Conversely, suppose $y \in z$ for some $z$ such that $\varphi[\alpha,z]$. But since $F$ is a function, there exists a unique set $z$ such that $y \in z and$ $\varphi[\alpha,z]$. Since we know that $\varphi[\alpha,x]$, we have that $z = x$ necessarily. Thus $y \in x$. Therefore $x$ is ordinal definable (with parameter $\alpha$).<br/>
<br/>
The latter assertion follows immediately: If $M$ is a class with a definable one-to-one correspondence $F : \boldsymbol{\mathrm{ORD}} \to M$, then $M = \ran(F) \subseteq OD$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex13.37"></a><br/>
<h2>Exercise 13.37.</h2>
<i>Solution.</i> Let $M$ be a transitive model of $\ZF$ such that there exists a definable one-to-one correspondence with the class of all ordinals. By <a href="#ex13.36">Exercise 13.36</a>, we have $M \subseteq OD$. But since $M$ is transitive, for all $x \in M$ we have $\TC(\lbrace x\rbrace) \subseteq M \subseteq OD$. Thus $x \in HOD$, so we have in fact that $M \subseteq HOD$.<p align="right">$\square$</p>
</body>