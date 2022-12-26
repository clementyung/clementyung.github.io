---
title: "17) Large Cardinals
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-17
excerpt: ""
---

{ % include commands.html % }

<a name="ex17.1"></a>
## Exercise 17.1.
<i>Solution.</i> The hint basically solves the problem, we just need to make sure that indeed $f_i \ni^\ast  f_{i+1}$ for all $i \in \omega$. In other words:

$$
\begin{align*}
\lbrace x \in \omega : f_i(x) > f_{i+1}(x)\rbrace \in U
\end{align*}
$$

Let $N_i = \lbrace n \in \omega : n \geq i\rbrace$. By construction, we have $N_{i+1} \subseteq \lbrace x \in \omega : f_i(x) > f_{i+1}(x)\rbrace$. Since $U$ is a non-principal ultrafilter and $\omega - N_{i+1}$ is finite, we have that $N_{i+1} \in U$. Then $\lbrace x \in \omega : f_i(x) > f_{i+1}(x)\rbrace \in U$, as desired. 
$\square$

<a name="ex17.2"></a>
## Exercise 17.2.
<i>Solution.</i> We shall show, from the functions defined in the hint, that we have $f_0 \ni^\ast  f_1 \ni^\ast  \cdots$. This is because:

$$
\begin{align*}
\lbrace x \in \omega : f_k(x) \in f_{k+1}(x)\rbrace = \bigcup_{n \geq k} X_k \in U
\end{align*}
$$

as $X_0,\dots,X_{k-1} \notin U \implies \bigcup_{i=0}^{k-1} X_i \notin U$. 
$\square$

<a name="ex17.3"></a>
## Exercise 17.3.
<i>Solution.</i> Suppose $\alpha = [f]$ where $f : S \to V$. By \L o\'{s}' Theorem, we have that:
\begin{center}
$\alpha$ is an ordinal $\iff$ $\lbrace x \in S : f(x) \text{ is an ordinal}\rbrace \in U$
\end{center}
Thus, $f$ is not an ordinal on a measure zero subset of $S$, and we may adjust it to obtain a $g : S \to \boldsymbol{\mathrm{ORD}}$ such that $[f] = [g]$. More explicitly:

$$
\begin{align*}
g(x) =
\begin{cases}
f(x), &\text{if $f(x)$ is an ordinal} \\
0, &\text{otherwise}
\end{cases}
\end{align*}
$$
 
$\square$

% <b>Remark.</b>. %     Well-foundedness is "used" in this exercise in the sense that if $\Ult$ is not well-founded (ill-founded), it doesn't make sense to discuss about ordinals in $\Ult$ - this is because if it is ill-founded, it must contain a decreasing chain of ordinals. See \hyperlink{https://math.stackexchange.com/questions/4214944/does-non-well-foundedness-of-a-model-imply-a-decreasing-sequence-of-ordinals-j/4214950\#4214950}{this MSE post}.
% 

<a name="ex17.4"></a>
## Exercise 17.4.
<i>Solution.</i> It suffices to show that $j_U$ is an isomorphism before the transitive collapse of $\Ult_U(V)$, so $\pi \circ j_U$ will be the identity mapping, where $\pi$ is the transitive collapse. The inverse $j_U^{-1} : \Ult \to V$ is defined by:

$$
\begin{align*}
j_U^{-1}([f]) = f(x_0)
\end{align*}
$$

We verify that this map is indeed the inverse of $j_U$. Indeed:

$$
\begin{align*}
j_U^{-1} \circ j_U(a) = j_U^{-1}([c_a]) = c_a(x_0) = a
\end{align*}
$$

On the other hand:

$$
\begin{align*}
j_U \circ j_U^{-1}([f]) = j_U(f(x_0)) = [c_{f(x_0)}]
\end{align*}
$$

But then:

$$
\begin{align*}
c_{f(x_0)}(x_0) = f(x_0) \implies \lbrace x \in S : c_{f(x_0)}(x) = f(x)\rbrace \in U \implies [c_{f(x_0)}] = [f]
\end{align*}
$$

so the inverse is indeed well-defined. We now show that $j_U^{-1}$ is an elementary embedding. We see that $j_U^{-1}$ preserves
equality as:

$$
\begin{align*}
\Ult \models [f] = [g]  &\iff \lbrace x \in S : V \models f(x) = g(x)\rbrace \in U \\
&\iff V \models f(x_0) = g(x_0) \\
&\iff V \models j_U^{-1}([f]) = j_U^{-1}([g])
\end{align*}
$$

and similarly for $\in$. 
$\square$

<a name="ex17.5"></a>
## Exercise 17.5.
<i>Solution.</i> Let $\lbrace X_\alpha : \alpha < \lambda\rbrace$ and $f$ be as in the hint. Clearly $[f] < [c_\lambda] = j_U(\lambda)$. On the other hand, we observe that for each $\mu < \lambda$, we have:

$$
\begin{align*}
\lbrace x \in S : \mu \in f(x)\rbrace = \bigcup_{\alpha > \mu} X_\alpha =  S - \bigcup_{\alpha \leq \mu} X_\alpha
\end{align*}
$$

Since $X_\alpha$ is of measure $0$ and $U$ is $\lambda$-complete, $\bigcup_{\alpha \leq \mu} X_\alpha$ remains measure $0$, so $\lbrace x \in S : \mu \in f(x)\rbrace \in U$. In other words, $\lambda \leq [f]$. 
$\square$

<a name="ex17.6"></a>
## Exercise 17.6.
<i>Solution.</i> Assume $j$ is non-trivial, for otherwise equality is immediate. If $x \in M$, then for some $\alpha \in \boldsymbol{\mathrm{ORD}}$ we have $x \in V_\alpha \subseteq V_{j(\alpha)} = j(V_\alpha)$. On the other hand, if $x \in j(V_\alpha)$ for some $\alpha \in \boldsymbol{\mathrm{ORD}}$, then since $M$ is transitive we have that $j(V_\alpha) \subseteq M$ so $x \in M$. 
$\square$

<a name="ex17.7"></a>
## Exercise 17.7.
<i>Solution.</i> We first note that $\kappa \in j(\kappa)$, so $\kappa \in j(X) \cap j(\kappa) = j(X \cap \kappa)$. Since the ultrafilter induced by $j$ is normal, it contains all closed unbounded subsets of $\kappa$, so $\kappa \in j(C)$ for all closed unbounded $C \subseteq \kappa$. Thus, $\kappa \in j(X \cap \kappa) \cap j(C) = j((X \cap \kappa) \cap C)$. In other words $(X \cap \kappa) \cap C$ is non-empty, so $X \cap \kappa$ is stationary (hence $\kappa \in M(X)$). 
$\square$

<a name="ex17.8"></a>
## Exercise 17.8.
<i>Solution.</i> Suppose $M$ contains all subsets of $\lambda$. Then the set $G$ in the proof of Theorem 17.7 is well-defined in $M$. By applying Lemma 17.8 in $M$, we obtain an $s \in G^\omega$ such that $(jF)(s) = \kappa$. Then proceed to obtain a contradiction as in the last paragraph of the proof. 
$\square$

<a name="ex17.9"></a>
## Exercise 17.9.
<i>Solution.</i> The hint basically solves the problem, but the last statement should be $((2^\kappa)^+)^M \leq j_D(\kappa)$, as $((2^\kappa)^+)^M \leq ((2^\kappa)^M)^+$ and $(2^\kappa)^M < j_D(\kappa) \implies ((2^\kappa)^M)^+ < j_D(\kappa)$. 
$\square$

<a name="ex17.10"></a>
## Exercise 17.10.
<i>Solution.</i> We expand on the hint. We note that if $d$ is the diagonal function, then:

$$
\begin{align*}
[f] < [d] &\iff \lbrace \alpha < \kappa : f(\alpha) < d(\alpha)\rbrace \in U \\
&\iff \lbrace \alpha < \kappa : f(\alpha) < \alpha\rbrace \in U \\
&\iff \text{$f$ is regressive on some $X \in U$}
\end{align*}
$$

<u>$\implies$:</u> Suppose $U$ extends the closed unbounded filter. Let $f : \kappa \to \kappa$ such that $f$ is regressive on some $X \in U$. Since $X \cap C \neq \emptyset$ for all closed unbounded $C$ (as $C \in U$), $X$ is stationary. By Fodor's Theorem 8.7, there exists a stationary $Y \subseteq X$ such that $f$ takes a constant value $\gamma$ on $Y$. But since $Y$ is unbounded and $f$ is monotone, we have that $f(\alpha) \neq \gamma$ on a bounded set. Thus, $f$ is constant almost everywhere.

<u>$\impliedby$:</u> Suppose $C \notin U$ for some closed unbounded $C$. Define the function $f : \kappa \to \kappa$ by stipulating that $f(\alpha) = \sup(C \cap \alpha)$. Clearly $f$ is nonconstant monotone as $C$ is unbounded. Furthermore, $f$ is regressive on $\kappa - C \in U$ - clearly $\sup(C \cap \alpha) \leq \alpha$. If $\sup(C \cap \alpha) = \alpha$, then since $C$ is closed, we must have $\alpha \in C$. Thus, if $\alpha \notin C$ then $\sup(C \cap \alpha) < \alpha$. Hence $[f] < [d]$ in $\Ult_U$. 
$\square$

<a name="ex17.11"></a>
## Exercise 17.11.
<i>Solution.</i> For $[f]_D,[g]_D \in \Ult_D(V)$, we have:

$$
\begin{align*}
[f]_D \in [g]_D &\iff \lbrace \alpha < \kappa : f(\alpha) \in g(\alpha)\rbrace \in D \\
&\iff h_{-1}(\lbrace \alpha < \kappa : f(\alpha) \in g(\alpha)\rbrace) \in U \\
&\iff \lbrace \alpha < \kappa : f(h(\alpha)) \in g(h(\alpha))\rbrace \in U \\
&\iff [f \circ h]_U \in [g \circ h]_U
\end{align*}
$$

One can do similarly for $[f]_D = [g]_D$. 
$\square$

<a name="ex17.12"></a>
## Exercise 17.12.
<i>Solution.</i> Let $\varphi(x)$ be a formula, with one free variables $x$, denoting that "$x = \aleph_\alpha$ for some ordinal $\alpha$ $\wedge$ $2^{\aleph_\alpha} \leq \aleph_{\alpha+\beta}$". We first note that since $[d]_D = \kappa$, we have:

$$
\begin{align*}
M \models \varphi(\kappa) &\iff M \models\varphi([d]) \\
&\iff \lbrace \alpha < \kappa : \varphi(d(\alpha))\rbrace \in D \\
&\iff \lbrace \alpha < \kappa : \varphi(\alpha)\rbrace \in D
\end{align*}
$$

Since $\lbrace \aleph_\alpha : 2^{\aleph_\alpha} \leq \aleph_{\alpha+\beta}\rbrace \in D$, we have that $M \models 2^{\aleph_\kappa} \leq \aleph_{\kappa+\beta}$, i.e. $(2^{\aleph_\kappa})^M \leq (\aleph_{\kappa+\beta})^M$. We shall show that $2^{\aleph_\kappa} \leq \aleph_{\kappa+\beta}$.

As per the hint, let $f : \kappa \to \boldsymbol{\mathrm{ORD}}$ be such that $f(\aleph_\alpha) = \aleph_{\alpha+\beta}$. We note that if we can show that $[f]_D = (\aleph_{\kappa+\beta})^M$ (since $\beta < \kappa$, $j(\beta) = \beta$). By Lemma 17.9(iii), we have that $2^{\aleph_\kappa} = 2^\kappa = (2^\kappa)^M \leq (2^{\aleph_\kappa})^M$ (as $\kappa$ is inaccessible). Since $M \subseteq V$ we have $(\aleph_{\kappa+\beta})^M \leq \aleph_{\kappa+\beta}$. Thus:

$$
\begin{align*}
2^{\aleph_\kappa} \leq (2^{\aleph_\kappa})^M \leq (\aleph_{\kappa+\beta})^M \leq \aleph_{\kappa+\beta}
\end{align*}
$$

Thus, it remains to show $[f]_D = (\aleph_{\kappa+\beta})^M$. Indeed:

$$
\begin{align*}
[f]_D = (\aleph_{\kappa + \beta})^M &\iff M \models [f]_D = \aleph_{[d]_D + \beta} \\
&\iff \lbrace \alpha < \kappa : f(\alpha) = \aleph_{d(\alpha) + \beta}\rbrace \in D \\
&\iff \lbrace \alpha < \kappa : \aleph_{\alpha+\beta} = \aleph_{\alpha + \beta}\rbrace \in D \\
&\iff \kappa \in D
\end{align*}
$$

in which the last statement is clearly true. 
$\square$

<a name="ex17.13"></a>
## Exercise 17.13.
<i>Solution.</i> Similar to the proof of <a href="#ex17.12">Exercise 17.12</a>, we first have $M \models 2^{\aleph_\kappa} < \aleph_{\kappa+\kappa}$, then using $[f]_D = (\aleph_{\kappa+\kappa})^M$ we have that $(\aleph_{\kappa+\kappa})^M \leq \aleph_{\kappa+\kappa}$. 
$\square$

<a name="ex17.14"></a>
## Exercise 17.14.
<i>Solution.</i> By elementarity, we have:

$$
\begin{align*}
\lambda = \aleph_{\kappa+\kappa} \implies j(\lambda) = j(\aleph_{\kappa+\kappa}) = (\aleph_{j(\kappa) + j(\kappa)})^M \leq \aleph_{j(\kappa) + j(\kappa)}
\end{align*}
$$

(Note that $j$ respects $+$ by elementarity) Now $\cf(\lambda) = \cf(\kappa + \kappa) = \cf(\kappa)$, so by Lemma 17.12 we have that $2^\lambda < j(\lambda)$. Now $j(\kappa) < (2^\kappa)^+$ by Lemma 17.9(iii), and since $\vert j(\kappa) + j(\kappa)\vert  = j(\kappa)$ we have that $j(\kappa) + j(\kappa) < (2^\kappa)^+$. Thus, $2^\lambda < \aleph_{j(\kappa) + j(\kappa)} \leq \aleph_{(2^\kappa)^+}$. 
$\square$

<a name="ex17.15"></a>
## Exercise 17.15.
<a name="lem17.15.A"></a>
<b>Lemma 17.15.A.</b> For any ordinal $\alpha \geq \kappa$, we have $j(\alpha) \leq \vert \alpha\vert ^\kappa$.

<i>Proof.</i> Consider the map (in $V$) $e : \alpha^\kappa \to j(\alpha)$ by $e(f) := [f]_D$. This is a well-defined map, as:

$$
\begin{align*}
[f]_D \in j(\alpha) &\iff [f]_D \iff [c_\alpha]_D \\
&\iff \lbrace \beta < \kappa : f(\beta) \in c_\alpha(\beta)\rbrace \in D \\
&\iff \lbrace \beta < \kappa : f(\beta) \in \alpha\rbrace \in D
\end{align*}
$$

Furthermore, every $\gamma < j(\alpha)$ is $[g]_D$ for some $g \in \alpha^\kappa$, so $e$ is onto. Thus, $j(\alpha) < \vert \alpha^\kappa\vert  = \vert \alpha\vert ^\kappa$ (as $\alpha \geq \kappa$). 
$\blacksquare$

<i>Solution.</i> Again by Lemma 17.12 we have $2^\lambda < j(\lambda)$. By elementarity of $j$, $j(\lambda) = (\aleph_{j(\alpha)})^M \leq \aleph_{j(\alpha)}$. Note that $\lambda \neq \kappa$, for otherwise by inaccessibility we have $\lambda = \aleph_\lambda$ (so $\kappa < \lambda$).

We first note that since $\cf(\alpha) = \kappa$ we have $\alpha \geq \kappa$. Thus, by <a href="#lem17.15.A">Lemma 17.15.A</a> we have that:

$$
\begin{align*}
j(\alpha) \leq \vert \alpha\vert ^\kappa < (\vert \alpha\vert ^\kappa)^+
\end{align*}
$$

On the other hand, since $\alpha < \lambda$ and $\lambda$ is a strong limit, we have that $\alpha^\kappa \leq 2^{\max\lbrace \alpha,\kappa\rbrace} < \lambda$. Thus, $j(\alpha) < \lambda$, so $2^\lambda < j(\lambda) \leq \aleph_{j(\alpha)} < \aleph_\lambda$. 
$\square$

<a name="ex17.16"></a>
## Exercise 17.16.
<i>Solution.</i> Let $C,C^M$ be the class of all fixed points of $\aleph$ in the models $V,M$ respectively. Since $M \subseteq V$, we have that $\aleph_\alpha^M \leq \aleph_\alpha$ for all ordinals $\alpha$, which gives the inequality $\alpha \leq \aleph_\alpha^M \leq \aleph_\alpha$. This implies that all fixed points in $V$ must also be fixed points in $M$, i.e. $C \subseteq C^M$. Thus, $(\Phi(\alpha))^M \leq \Phi(\alpha)$ for all ordinals $\alpha$.

Now again by Lemma 17.12, we have that $2^\lambda < j(\lambda)$. Thus:

$$
\begin{align*}
2^\lambda < j(\lambda) = j(\Phi(\kappa + \kappa)) = \Phi^M(j(\kappa + \kappa)) \leq \Phi(j(\kappa + \kappa))
\end{align*}
$$

Now $j(\kappa + \kappa) = j(\kappa) + j(\kappa)$, so $\vert j(\kappa + \kappa)\vert  = \vert j(\kappa)\vert $. By Lemma 17.9(iii), we have that $\vert j(\kappa)\vert  = j(\kappa) < (2^\kappa)^+$. Since $(2^\kappa)^+$ is a cardinal, this implies that $j(\kappa + \kappa) < (2^\kappa)^+$. Thus:

$$
\begin{align*}
\Phi(j(\kappa + \kappa)) < \Phi((2^\kappa)^+)
\end{align*}
$$

as desired. 
$\square$

<a name="ex17.17"></a>
## Exercise 17.17.
<i>Solution.</i> Fix $S \subseteq \Sigma$ such that $\vert S\vert  \leq \lambda$. Let $A \subseteq \kappa$ be the set of all ordinals such that for each $\alpha \in A$, the constant $c_\alpha$ appears in some sentence in $S$. Note that we have $\vert A\vert  \leq \lambda$, so by some order-preserving bijection we may assume $A = \mu$ for some cardinal $\mu < \lambda$.

We interpret each $c_\alpha$ by the ordinal $\alpha$, $<$ by the linear order of ordinals, and the function symbol $f_x$ by stipulating that for $\alpha,\beta,\gamma < \mu$, we have:

$$
\begin{align*}
R(x,y,z) \iff \otp(x - z) = y
\end{align*}
$$

Clearly (a) and (b) are satisfied. If $\beta < \alpha$, then $\otp(\alpha - \beta)$ is a well-defined ordinal $<\alpha$, say $\gamma$, in which then $R(\alpha,\gamma,\beta)$ holds. Thus $z < x \to \exists y \, R(x,y,z)$ is always satisfied. We also have $\gamma < \lambda$, so $R(x,y,z) \to \bigvee_{\xi<\lambda} (y = c_\xi)$ is satisfied. Finally, for ordinals $\gamma$ we observe that $f_\alpha(\gamma) = \alpha + \gamma$, so $f_x$ is a well-defined function on $\mu$ for all $x \in \mu$. Therefore $(\mu,<,f_x,\lbrace \alpha : \alpha < \lambda\rbrace)$ is a model of $S$.

Now suppose $\Sigma$ has a model $\A$. On one hand, we have that $\dom(f_\kappa) \subseteq \lbrace c_\xi : \xi < \lambda\rbrace$, so $\vert \dom(f_\kappa)\vert  \leq \lambda$. On the other hand, we have $\lbrace c_\xi : \xi < \kappa\rbrace \subseteq \ran(f_\kappa)$, so $\vert \ran(f_\kappa)\vert  \geq \kappa$. This implies that $\kappa \leq \lambda$, which is not possible. 
$\square$

<a name="ex17.18"></a>
## Exercise 17.18.
<i>Solution.</i> Jech's hint is ambiguous, so we present the proof in Kanamori's <i>The Higher Infinite</i>. Consider appending the language $\L_{\kappa,\omega}$ with non-logical symbols $<$, $c$ and $c_\alpha$ for $\alpha < \kappa$. Let $\Sigma$ be a set consisting of the following sentences:
<ol>
<li> $<$ is a linear order..</li>
<li> $\bigvee_{\alpha \in A} \bigvee_{\beta < \alpha} \, x = c_\beta$.</li>

<li> For each $\alpha < \kappa$, $c \neq c_\alpha$ (call each of these statements $\varphi_\alpha$)..</li></ol>
Note that $\vert \Sigma\vert  = \kappa$. Clearly $\Sigma$ does not have a model, as statements (ii) and (iii) contradict (and $A$ is cofinal). On the other hand, if $S \subseteq \Sigma$ and $\varphi_\alpha \notin S$ for some $\alpha < \kappa$, then we may interpret these sentences by:
<ol>
<li> $\A = \kappa$.</li>

<li> Interpret each symbol $c_\beta$ by the ordinal $\beta$..</li>
<li> Interpret $c$ by the ordinal $\alpha$.</li>

<li> $c_\alpha < c_\beta$ iff $\alpha < \beta$..</li></ol>
which gives us a model $(\kappa,<,\lbrace \alpha : \alpha < \kappa\rbrace)$ of $S$. 
$\square$

<a name="ex17.19"></a>
## Exercise 17.19.
<a name="lem17.19.A"></a>
<b>Lemma 17.19.A.</b> Let $\mathcal{A} \subseteq \mathcal{B}$ with $\vert \mathcal{A}\vert  < \kappa$. There exists a map $f : \mathcal{A} \to \mathcal{B}$ such that:
<ol>
<li> For all $X \in \mathcal{A}$, $f(X) = X$ or $f(X) = \kappa - X$.</li>

<li> $\bigcap \ran(f) \neq \emptyset$..</li></ol>

<i>Proof.</i> Let $\lambda := \vert \mathcal{A}\vert $. Let $\F$ be the set of all functions $f : \mathcal{A} \to \mathcal{B}$ such that $f(X) = X$ or $f(X) = \kappa - X$ for all $X \in \mathcal{A}$. Clearly $\vert \F\vert  = 2^\lambda$, and $2^\lambda < \kappa$ as $\kappa$ is inaccessible. Furthermore, we observe that $\bigcup_{f \in \F} \bigcap \ran(f) = \kappa$ - to see this, fix $\alpha \in \kappa$. Define $f : \mathcal{A} \to \mathcal{B}$ by stipulating that $f(X) = X$ if $\alpha \in X$, and $f(X) = \kappa - X$ otherwise (so $\alpha \in \kappa - X$). Then $\alpha \in \bigcap \ran(f)$.

Therefore, we have in particular that $\bigcap \ran(f) \neq \emptyset$ for some $f \in \F$, as desired. 
$\blacksquare$

<a name="lem17.19.B"></a>
<b>Lemma 17.19.B.</b> Let $F$ be a $\kappa$-complete filter over a $\kappa$-complete algebra $(\mathcal{B},\subseteq)$ of subsets of $\kappa$. Let $\mathcal{A} \subseteq \mathcal{B}$ such that $\vert \mathcal{A}\vert  < \kappa$. Then there exists a $\kappa$-complete filter $F' \supseteq F$ such that for all $X \in \mathcal{A}$, $X \in F'$ or $\kappa - X \in F'$.

<i>Proof.</i> Assume WLOG that for all $X \in \mathcal{A}$, $X \notin F$ and $\kappa - X \notin F$. By <a href="#lem17.19.A">Lemma 17.19.A</a>, let $f : \mathcal{A} \to \mathcal{B}$ be such that $f(X) = X$ or $f(X) = \kappa - X$ for all $X \in \mathcal{A}$, and $W := \bigcap\ran(f) \neq \emptyset$. Then $W \notin F$, so by <a name="#7#lem7.24.A">Lemma 7.24.A</a> there exists a filter $F' \supseteq F$ such that $W \in F'$.

To see that $F'$ is $\kappa$-complete, let $\mathcal{A}' \subseteq F'$ such that $\vert \mathcal{A}'\vert  < \kappa$. Then for each $Y \in \mathcal{A}'$, we have that $Y \supseteq Y' \cap W$ for some $Y' \in F$. Since $F$ is $\kappa$-complete, $T := \bigcap_{Y \in \mathcal{A}'} Y' \in F$. Then $\bigcap\mathcal{A} \supseteq T \cap W \in F'$, so $F'$ is $\kappa$-complete. 
$\blacksquare$

<i>Solution.</i> It suffices to show that a model exists for all $S \subseteq \Sigma$ such that:
<ol>
<li> $S$ contains $\neg U(c_\emptyset)$.</li>

<li> $S$ contains $U(c_X) \to U(c_Y)$ for all $X,Y \in \mathcal{B}$ such that $X \subseteq Y$..</li>
<li> $S$ contains $U(c_X)$ for all $X \in F$.</li>

<li> $S$ contains $\bigwedge_{X \in \mathcal{A}} U(c_X) \to U\bb{c_{\bigcap \mathcal{A}}}$ for all $\mathcal{A} \subseteq \mathcal{B}$ such that $\vert \mathcal{A}\vert  < \kappa$..</li>
<li> Let $\mathcal{C}$ be the set of all $X \in \mathcal{B}$ such that $S$ contains $U(c_X) \vee U(c_{\kappa - X})$. Then $\vert \mathcal{C}\vert  < \kappa$.</li>
</ol>
By interpreting $U(c_X)$ as $X \in U$, it suffices to find a $\kappa$-complete filter $U \supseteq F$ (satisfying (i)-(iv)) such that for all $X \in \mathcal{C}$, $X \in U$ or $\kappa - X \in U$. But this follows from <a href="#lem17.19.B">Lemma 17.19.B</a>. 
$\square$

<a name="ex17.20"></a>
## Exercise 17.20.
<a name="lem17.20.A"></a>
<b>Lemma 17.20.A.</b> Suppose $\kappa$ is inaccessible. Let $A \subseteq \kappa$ such that $\vert A\vert  = \kappa$. Let $\mathcal{B}$ be the $\kappa$-complete algebra generated by $A$. Then $\vert \mathcal{B}\vert  = \kappa$.

<i>Proof.</i> Clearly $\vert \mathcal{B}\vert  \geq \kappa$. On the other hand, we note that for each $y \in \mathcal{B}$, there exists a sequence $\c{x_{\alpha,\beta} : \alpha < \lambda, \beta < f(\alpha)}$, where $\lambda < \kappa$ and $f : \lambda \to \kappa$, such that:

$$
\begin{align*}
y = \bigcup_{\alpha < \lambda} \bigcap_{\beta < f(\alpha)} x_{\alpha,\beta}
\end{align*}
$$

Thus, it suffices to count the number of such sequences. For each $\lambda < \kappa$ and fixed $f : \lambda \to \kappa$, since $\kappa$ is regular we have that $f$ is bounded. Thus, there are $\leq \kappa$ assignments to elements of $A$ into the sequence $\c{x_{\alpha,\beta} : \alpha < \lambda, \beta < f(\alpha)}$ (with $\lambda,f$ fixed). Thus, the total number of elements of $\mathcal{B}$ is $\sum_{\lambda < \kappa} \kappa \cdot \kappa^\lambda \leq \kappa$. 
$\blacksquare$

<i>Solution.</i> As in Lemma 10.18 we show that $\kappa$ has the tree property. Let $(T,<)$ be a tree of height $\kappa$ with levels of size $\kappa$. Since $\kappa$ is inaccessible, $\vert T\vert  = \kappa^{<\kappa} = \kappa$, so we may assume WLOG that $T = \kappa$. For each $s \in T$, let:

$$
\begin{align*}
O_s := \lbrace t \in T : t \leq s\rbrace
\end{align*}
$$

Let $\mathcal{B}$ be the $\kappa$-complete algebra generated by $\lbrace O_s : s \in T\rbrace \cup \lbrace \lbrace s\rbrace : s \in T\rbrace$. By <a href="#lem17.20.A">Lemma 17.20.A</a>, $\vert \mathcal{B}\vert  = \kappa$. Let $F$ be the set of all subsets $X$ of $T$ such that $\vert T - X\vert  < \kappa$. Since $\kappa$ is regular, $F$ is a $\kappa$-complete filter on $T$. By assumption, there exists a $\kappa$-complete ultrafilter $U$ extending $F$. Note that $U$ is clearly nonprincipal.

We now construct a cofinal branch $\c{s_\alpha : \alpha < \kappa}$ such that $s_\alpha \in T(\alpha)$ and $O_{s_\alpha} \in U$ for all $\alpha$. Let $s_0$ be the root of $T$. Note that $O_{s_0} = T \in U$. Suppose $s_\alpha$ is defined. Let $S_\alpha := \lbrace t \in T : t \in T(\alpha + 1) \wedge t \leq s_\alpha\rbrace$. Observe that $O_s = \lbrace s_\alpha\rbrace \cup \bigcup_{t \in S_\alpha} O_t$. Since $T$ is a $\kappa$-tree, $\vert S_\alpha\vert  < \kappa$. Thus, by the $\kappa$-completeness of $U$, $O_t \in U$ for some $t \in S_\alpha$. Let $s_{\alpha+1}$ be this $t$.

If $\alpha$ is a limit ordinal, then by $\kappa$-completeness of $U$ we have that $\bigcap_{\beta < \alpha} O_{s_\beta} \in U$. It's easy to see that:

$$
\begin{align*}
\bigcap_{\beta < \alpha} O_{s_\beta} = \bigcup_{t \in T(\alpha) \cap \bigcap_{\beta < \alpha} O_{s_\beta}} O_t
\end{align*}
$$

Since $T$ is a $\kappa$-tree, $\mod{T(\alpha) \cap \bigcap_{\beta < \alpha} O_{s_\beta}} < \kappa$, so by $\kappa$-completeness of $U$ we have $O_t \in U$ for some $t \in T(\alpha) \cap \bigcap_{\beta < \alpha} O_{s_\beta}$. Let $s_\alpha$ be this $t$. 
$\square$

<a name="ex17.21"></a>
## Exercise 17.21.
<i>Solution.</i> Define a coloring $f : [\kappa]^2 \to 2$ by stipulating that:

$$
\begin{align*}
f(\lbrace \alpha,\beta\rbrace) =
\begin{cases}
0, &\text{if $\alpha < \beta$} \\
1, &\text{if $\alpha > \beta$}
\end{cases}
\end{align*}
$$

Since $\kappa \to (\kappa)_2^2$, there exists a $H \subseteq \kappa$ such that $f$ takes a constant value in $[H]^\kappa$. If the constant value is $0$, then $H$ is well-ordered by $<$. Otherwise, it is conversely well-ordered by $>$. 
$\square$

<a name="ex17.22"></a>
## Exercise 17.22.
<i>Solution.</i> The statement in the hint is clearly $\Sigma_1^2$ with respect to $(V_\kappa,\in)$. If the least measurable cardinal is $\Sigma_1^2$-indescribable, then there exists an $\alpha < \kappa$ such that:

$$
\begin{align*}
(V_\alpha, \in) \models \exists U \, (\text{$U$ is an $\alpha$-complete nonprincipal ultrafilter on } \alpha)
\end{align*}
$$

which contradicts the minimality of $\kappa$. 
$\square$

<a name="ex17.23"></a>
## Exercise 17.23.
<i>Solution.</i> We fill in the details in the hint.
<ol>
<li> Each of the $M_n$'s exists by L\"{o}wenheim-Skolem theorem..</li>
<li> We induct on $n$ that $\vert M_n\vert  < \kappa$ and $\alpha_n < \kappa$. Clearly $\vert M_0\vert  = \aleph_0 < \kappa$. If $\vert M_n\vert  < \kappa$, then $\alpha_n \geq \sup\lbrace \rank(x) + 1 : x \in M_n\rbrace$. Since $\vert M_n\vert  < \kappa$ and $\kappa$ is regular, we may choose $\alpha_n < \kappa$. Since $\alpha_n < \kappa$, we have $\vert V_{\alpha_n}\vert  = \beth_{\alpha_n} < \beth_\kappa = \kappa$ (see <a name="#6#lem6.3.A">Lemma 6.3.A</a>).</li>

<li> By regularity of $\kappa$ again, we have $\alpha = \lim_{n\to\omega} \alpha_n < \kappa$..</li>
<li> Clearly $\bigcup_{n<\omega} V_{\alpha_n} = \bigcup_{n<\omega} M_n$. The proof that $V_\alpha \prec (V_\kappa,\in,U)$ is almost verbatim to that of <a name="#12#lem12.12.A">Lemma 12.12.A</a>, which completes the proof.</li>
</ol> 
$\square$

<a name="ex17.24"></a>
## Exercise 17.24.
<i>Solution.</i> The hint solves the problem, with the only non-trivial part being the assertion $\sat(B) = \kappa$. Note also that the proof applies to $\lambda$-generated complete Boolean algebras of cardinality $\kappa$, for any $\lambda < \kappa$.

Suppose for a contradiction that $\sat(B) = \lambda < \kappa$. Let $A \subseteq B$ be a countable set of generators. By the infinite version of <a href="https://clementyung.github.io/jech-solutions/chapter-7#ex7.18">Exercise 7.18</a>, for each $x \in B$ we have that $x = \sum X$, where for all $y \in A$ we have that $y = \prod_{a \in X} A_a$ where $A_a \subseteq A$. By <a name="#15#lem15.35.A">Lemma 15.35.A</a>, we may assume that $\vert X\vert  < \lambda$ for all $x \in B$. By counting elements we see clearly that $\vert B\vert  \leq 2^\lambda \cdot 2^{\aleph_0} < \kappa$, a contradiction. 
$\square$

<a name="ex17.25"></a>
## Exercise 17.25.
<i>Solution.</i> This follows from Lemma 17.32, by considering the embedding $j : V \to \Ult_D(V)$, where $D$ is a $\kappa$-complete normal measure on $\kappa$. We expand on the fact that $A_\kappa$ is stationary.

Since $A_\kappa \subseteq \kappa$ and $\kappa$ is the least ordinal moved, we have that $j(A_\kappa) \cap \kappa = A_\kappa$. Since $D$ is normal we have $\kappa = [d]$. Then:

$$
\begin{align*}
\Ult_D(V) \models j(A_\kappa) \cap \kappa = A_\kappa &\iff \Ult_D(V) \models [c_{A_\kappa}]_D \cap [d]_D = A_{[d]_D} \\
&\iff \lbrace \alpha < \kappa : c_{A_\kappa}(\alpha) \cap d(\alpha) = A_{d(\alpha)}\rbrace \in U \\
&\iff \lbrace \alpha < \kappa : A_\kappa \cap \alpha = A_\alpha\rbrace \in U
\end{align*}
$$

Thus, $\lbrace \alpha < \kappa : A_\kappa \cap \alpha = A_\alpha\rbrace$. Since $D$ extends the closed unbounded filter of $\kappa$ (Lemma 8.11), $\lbrace \alpha < \kappa : A_\kappa \cap \alpha = A_\alpha\rbrace$ is stationary. 
$\square$

<a name="ex17.26"></a>
## Exercise 17.26.
<i>Solution.</i> We note that if $X$ is stationary and $X = Y \sqcup Z$, then either $Y$ or $Z$ is stationary - otherwise, if $C_Y,C_Z$ are closed unbounded sets such that $Y \cap C_Y = Z \cap C_Z = \emptyset$, then $X \cap (C_Y \cap C_Z) = \emptyset$, a contradiction.

It remains to show that $f$ is homogeneous on both $[S \cap A]^2$ and $[S - A]^2$. Let $\lbrace \beta,\gamma\rbrace \in [S \cap A]^2$ with $\beta < \gamma$. Then $\beta \in A \cap \gamma = A_\gamma$ (as $\gamma \in S$), so $f(\lbrace \beta,\gamma\rbrace) = 1$. Now let $\lbrace \beta,\gamma\rbrace \in [S - A]^2$ with $\beta < \gamma$. Again $A \cap \gamma = A_\gamma$, but $\beta \notin A$ so $f(\lbrace \beta,\gamma\rbrace) = 0$. 
$\square$

<a name="ex17.27"></a>
## Exercise 17.27.
<i>Solution.</i> Let $\c{A_\alpha : \alpha < \kappa}$ be a sequence of sets in $L$ such that $A_\alpha \subseteq \alpha$ for all $\alpha$. Since $\kappa$ is ineffable, there exists a set $A \subseteq \kappa$ such that $S := \lbrace \alpha < \kappa : A \cap \alpha = A_\alpha\rbrace$ on a stationary set. Since $S$ is unbounded, it implies that $A \cap \beta = A_\alpha \cap \beta$ for some $\beta \in S$, so $A \cap \beta \in L$ for all $\beta < \kappa$. By Lemma 17.21, $A \in L$.

This implies that $S \in L$ as well. Since $L$ contains all ordinals, the closed unbounded property of a set is absolute between $V$ and $L$. Thus, the stationary property of a set is downward absolute from $V$ to $L$, so $S$ is stationary in $L$. Hence $\kappa$ is ineffable in $L$. 
$\square$

<a name="ex17.28"></a>
## Exercise 17.28.
<i>Solution.</i> We first note that Rowbottom's Theorem 17.27 may be repeated with $L$ replaced with $L[x]$ for all $x \subseteq \omega$. The main point to note is that G\"{o}del's Condensation Lemma holds for $L[x]$, since clearly $\pi(x) = x$. Other facts about $L$ used in the proof may be trivially lifted to $L[x]$.

Now let $\alpha < \omega_1$ be a countable ordinal such that $\alpha$ is a cardinal in $L$. By <a href="https://clementyung.github.io/jech-solutions/chapter-13#ex13.28">Exercise 13.28</a>, there exists some $x \subseteq \omega$ such that $\alpha$ is a countable ordinal in $L[x]$. Let $f \in L[x]$ be a one-to-one correspondence between $\alpha$ and $\omega$. Define $F : P^L(\alpha) \to P^{L[x]}(\omega)$ by stipulating that $y \mapsto f"(y)$. Then $F$ is one-to-one, so we have that (in $V$) $\vert P^L(\alpha)\vert  \leq \vert P^{L[x]}(\omega)\vert $. Since $P^{L[x]}(\omega)$ is countable by above (modified version of Theorem 17.27), we conclude that (in $V$) $P^L(\alpha)$ is countable. In other words, there does not exist a one-to-one map on $\aleph_1$ into $P^L(\alpha)$. Thus for all $\alpha < \kappa$, we have that $(2^\alpha)^L < \aleph_1$, so $\aleph_1$ is inaccessible in $L$. 
$\square$

<a name="ex17.29"></a>
## Exercise 17.29.
<i>Solution.</i> The hint solves the problem. Note that the sentence that asserts "$(V_\kappa,\in,U) \models \sigma$" can indeed by made first order in $M$, by taking higher ranks above $V_\kappa$. 
$\square$

<a name="ex17.30"></a>
## Exercise 17.30.
<i>Solution.</i> By definition $\eta_\omega$ is the least cardinal $\kappa$ satisfying $\kappa \to (\omega)^{<\omega}$. Note that $[\kappa]^{<\omega} \subseteq V_\kappa$. Since $\eta_\omega$ is inaccessible, we have $\cf(\kappa) > \omega$ so this partition property may be expressed as:

$$
\begin{align*}
(\forall X \subseteq [\kappa]^{<\omega})(\exists \alpha \in \kappa)(\exists H \in P(\alpha))(\forall n \in \omega)([H]^n \subseteq X \vee [H]^n \subseteq \kappa - X)
\end{align*}
$$

Then this is a $\Pi_1^1$ statement in the model $(V_\kappa,\in,[\kappa]^{<\omega})$, and it does not reflect to any smaller models $(V_\alpha,\in,[\alpha]^{<\omega})$ by minimality. 
$\square$

<a name="ex17.31"></a>
## Exercise 17.31.
<i>Solution.</i> This hint is confusing and there are probably some errors. A suggested, amended hint would be to replace "$h_n$ is $n$-ary" with "$h_n$ is $k(n)$-ary, where $k(n) \leq n$ for all $n$", and for $x \in [\kappa]^n$, we instead define:

$$
\begin{align*}
F(x_1,\dots,x_n) := h_n(x_1,\dots,x_{k(n)})
\end{align*}
$$

In this case, it is clear that the Skolem functions can be arranged this way.

<u>$\implies$:</u> As in the hint let $(H,<,F_1,F_2,\dots)$ be a proper elementary submodel of $(\kappa,<,F_1,F_2,\dots)$. Then in particular we have $F_1"([H]^n) \subseteq H$ for all $n$, so $F"([H]^{<\omega}) \subseteq H$, which omits a value of $\kappa$.

<u>$\impliedby$:</u> We shall show that $(F"(H),\dots) \prec \A$. By <a name="#12#lem12.12.B">Lemma 12.12.B</a> it suffices to show that for all existential formulas $\exists y \, \varphi(x,y)$, if $\A \models \exists y \, \varphi(x,y)$ and $x \in F"(H)$. then $(F"(H),\dots) \models \exists y \, \varphi(x,y)$. We note that since $\lbrace h_n : n < \omega\rbrace$ is closed under composition, $F"(H) \subseteq H$. Thus if $\phi(x) \equiv \exists y \, \varphi(x,y)$ then $h_\phi(x) \in F"(H) \subseteq H$, so $(F"(H),\dots) \models \phi(x)$. 
$\square$

<a name="ex17.32"></a>
## Exercise 17.32.
<i>Solution.</i> Let $\B = (B,f\restrictedto B) \prec \A$ be an elementary submodel such that $n \notin B$ for some $n \in B$. Then $n + 1 \notin B$, for otherwise $f(n + 1) = n \in B$. Inductively, one may prove that $m \notin B$ for all $n \geq B$. This implies that $B$ is finite, so $\A$ has no countable proper elementary submodel. 
$\square$

<a name="ex17.33"></a>
## Exercise 17.33.
<i>Solution.</i> The hint solves the first problem. Note that if $\alpha$ is the $\lambda^\text{th}$ element, then $\vert B \cap \alpha\vert  = \lambda$, so $\vert f_\alpha(B \cap \alpha)\vert  = \lambda$ as $f_\alpha$ is one-to-one.

For the second part, let $f$ be a nondecreasing function of $\kappa$ onto $\lambda$. Let $\A = (\kappa,\lambda,<,R)$, where $R(\alpha,\beta)$ if and only if $f(\alpha) = \beta$. Let $(B,B \cap \lambda,<,R \cap B^2) \prec \A$ with $\vert B\vert  = \kappa$. Let $g : \lambda \to \kappa$ be a cofinal function, and for each $\alpha \in \lambda$ let $\beta_\alpha$ be the least element in $B \cap \kappa$ such that $f(\beta_\alpha) \geq \alpha$ (which exists as $\vert B\vert  = \kappa$). Then $\lbrace f(\beta_\alpha) : \alpha < \lambda\rbrace \subseteq B \cap \lambda$ is unbounded in $\lambda$, and since $\lambda$ is regular, $\vert B \cap \lambda\vert  = \lambda$. Thus $\kappa$ is not Rowbottom. 
$\square$