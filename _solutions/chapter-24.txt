---
title: "24)The Singular Cardinal Problem
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-24
excerpt: ""
---

{ % include commands.html % }

    <a name="ex24.1"></a>
## Exercise 24.1.
<i>Solution.</i> We first note that under this exercise's hypothesis, $\aleph_{\omega_1}$ is a strong limit cardinal (in particular, $2^{\aleph_1} < \aleph_{\omega_1}$) - indeed, let $\alpha < \omega_1$, and since stationary sets are unbounded there exists an $\alpha < \gamma < \omega_1$ such that $2^{\aleph_\alpha} \leq 2^{\aleph_\gamma} \leq \aleph_{\gamma+\beta} < \aleph_{\omega_1}$. Hence, $\aleph_{\omega_1}^{\aleph_1} = 2^{\aleph_{\omega_1}}$.

We note that if $\alpha < \omega_1$ is a limit ordinal, then $\cf(\alpha) = \omega$. Thus, for all limit ordinals such that $2^{\aleph_\alpha} \leq \aleph_{\alpha+\beta}$, we have that $\aleph_\alpha^{\aleph_0} \leq (2^{\aleph_\alpha})^{\aleph_0} \leq 2^{\aleph_\alpha} \leq \aleph_{\alpha+\beta}$. By <a href="#ex24.2">Exercise 24.2</a>, $2^{\aleph_{\omega_1}} = \aleph_{\omega_1}^{\aleph_1} \leq \aleph_{\omega_1+\beta}$, as desired. 
$\square$

<a name="ex24.2"></a>
## Exercise 24.2.
<i>Solution.</i> We note that in Lemma 24.3, if $\varphi$ takes constant value $\beta$, then clearly $\Vert \varphi\Vert  \geq \beta$. Thus, the ranks of the functions $\varphi : \omega_1 \to \omega_1$ is unbounded in $\omega_1$, and hence is the set $\omega_1$. In particular, for every $\beta < \omega_1$ there exists a function $\varphi : \omega_1 \to \omega_1$ such that $\Vert \varphi\Vert  = \beta$.

Assume that $\aleph_\alpha^{\aleph_0} = \aleph_{\alpha+\beta}$ for a stationary set of $\alpha < \omega_1$ (note that if $\alpha < \omega_1$ is limit, then $\cf(\alpha) = \omega$). For each $h : \omega_1 \to \aleph_{\omega_1}$, let $f_h$ be defined as in the proof of Lemma 8.14 from Lemma 8.15. Let $F := \lbrace f_h : h \in {\aleph_{\omega_1}}^{\omega_1}\rbrace$. Then $F$ is an almost disjoint family of functions, with $F \subseteq \prod_{\alpha<\omega_1} {\aleph_\alpha}^{\omega_1}$. By assumption, $\vert {\aleph_\alpha}^{\omega_1}\vert  \leq \aleph_{\alpha+\beta}$.

By <a href="https://clementyung.github.io/jech-solutions/chapter-5#ex5.19">Exercise 5.19</a>, for all $\alpha < \omega_1$ we have that $\aleph_\alpha^{\aleph_1} = \aleph_\alpha^{\aleph_0} \cdot 2^{\aleph_1}$. We have $2^{\aleph_1} < \aleph_{\omega_1}$ by hypothesis, and by the unboundedness of stationary set there exists $\alpha < \gamma < \omega_1$ such that $\aleph_\alpha^{\aleph_0} \leq \aleph_\gamma^{\aleph_0} \leq \aleph_{\gamma+\beta} < \aleph_{\omega_1}$. Thus, we may apply Lemma 24.3 with $\Vert \varphi\Vert  = \beta$ to get that that $\vert F\vert  \leq \aleph_{\omega_1 + \beta}$. Hence $\aleph_{\omega_1}^{\aleph_1} = \aleph_{\omega_1 + \beta}$, as desired. 
$\square$

<a name="ex24.3"></a>
## Exercise 24.3.
<i>Solution.</i> We note that <a href="#ex24.1">Exercise 24.1</a> can be easily generalised to all singular cardinals of uncountable cofinality (replace $\omega_1$ with $\kappa$). If $\kappa$ is singular, then $E^\kappa_\omega$ is a stationary subset of $\kappa$, so the statement follows directly from <a href="#ex24.1">Exercise 24.1</a>. 
$\square$

<a name="ex24.4"></a>
## Exercise 24.4.
<i>Solution.</i> The proof of this is verbatim to that of <a href="#ex24.1">Exercise 24.1</a>. In fact, we only require that $2^{\aleph_\alpha} \leq \aleph_{\alpha+\beta}$ for a stationary many $\alpha < \eta$. 
$\square$

<a name="ex24.5"></a>
## Exercise 24.5.
<i>Solution.</i> This is an immediate consequence of <a href="#ex24.7">Exercise 24.7</a>, as the hypothesis of this exercise implies the hypothesis of <a href="#ex24.7">Exercise 24.7</a> for stationarily many $\alpha < \omega_1$, which is sufficient for the statement to hold. Note that the hypothesis ensures that $\aleph_{\omega_1}$ is a strong limit cardinal, so that $2^{\aleph_{\omega_1}} = \aleph_{\omega_1}^{\aleph_1}$. 
$\square$

<a name="ex24.6"></a>
## Exercise 24.6.
<i>Solution.</i> Define a map $f : \omega_1 \to \omega_1$ by:

$$
\begin{align*}
f(\alpha) = \min\lbrace \beta < \omega_1 : 2^{\aleph_{\omega_1+\alpha}} \leq \aleph_{\omega_1+\alpha+\beta}\rbrace
\end{align*}
$$

By the hypothesis of this exercise, $f$ is regressive on $\omega_1$. Thus, there exists a stationary $S \subseteq \omega_1$ such that $f(\alpha) = \gamma$ for all $\alpha \in S$, where $\gamma < \omega_1$ is fixed. Let $S' := \lbrace \omega_1 + \alpha : \alpha \in S\rbrace$. Clearly $S' \subseteq \omega_1 + \omega_1$ is stationary, and $2^{\aleph_\alpha} \leq \aleph_{\alpha+\gamma}$ for all $\alpha \in S'$. By <a href="#ex24.4">Exercise 24.4</a>, this implies that $2^{\aleph_{\omega_1+\omega_1}} \leq \aleph_{\omega_1+\omega_1+\gamma} < \aleph_{\omega_1+\omega_1+\omega_1}$. 
$\square$

<a name="ex24.7"></a>
## Exercise 24.7.
<a name="lem24.7.A"></a>
<b>Lemma 24.7.A.</b> Fix $\beta < \omega_1$. If $\varphi : \omega_1 \to \omega_1$ is such that $\varphi(\alpha) \leq \beta$ on a stationary subset of $\omega_1$, then $\Vert \varphi\Vert  = \beta$.

<i>Proof.</i> Suppose the statement holds for $\gamma < \beta$. Let $\varphi$ be such that $\varphi(\alpha) \leq \beta$ on a stationary subset $S$. Let $\psi < \varphi$, so there exists a closed unbounded subset $C \subseteq \omega_1$ such that $\psi(\alpha) < \varphi(\alpha)$ for all $\alpha \in C$. Then $\psi(\alpha) < \beta$ on the stationary subset $S' := C \cap S \cap (\omega_1 - \beta)$. Furthermore, $\psi$ is regressive on $S'$, so by Fodor's Theorem there exists a stationary $S" \subseteq S'$ such that $\psi(\alpha) = \gamma < \beta$ for all $\alpha \in S"$. By induction hypothesis, $\Vert \psi\Vert  \leq \gamma < \beta$, so:

$$
\begin{align*}
\Vert \varphi\Vert  = \sup\lbrace \Vert \psi\Vert  + 1 : \psi < \varphi\rbrace \leq \beta
\end{align*}
$$
 
$\blacksquare$

<a name="lem24.7.B"></a>
<b>Lemma 24.7.B.</b> Let $\varphi : \omega_1 \to \omega_1$ be such that $\varphi(\alpha) = \alpha$ for all $\alpha$. Then $\Vert \varphi\Vert  = \omega_1$.

<i>Proof.</i> Let $\varphi_\beta : \omega_1 \to \omega_1$ be the function taking the constant value $\beta$. Clearly $\Vert \varphi_\beta\Vert  \geq \beta$ (in fact, $\Vert \varphi_\beta\Vert  = \beta$) and $\varphi_\beta < \varphi$ (as $\varphi_\beta(\alpha) < \varphi(\alpha)$ on a tail segment of $\omega_1$). Thus $\Vert \varphi\Vert  \geq \omega_1$. Conversely, suppose $\psi < \varphi$, so $\psi(\alpha) < \varphi(\alpha) = \alpha$ on a closed unbounded (in particular, stationary) subset of $\omega_1$. Then $\psi$ is regressive on a stationary subset of $\omega_1$, so by Fodor's Theorem it takes a constant value $\gamma < \alpha$ on a stationary subset of $\omega_1$. By <a href="#lem24.7.A">Lemma 24.7.A</a> again $\Vert \psi\Vert  \leq \gamma$, so $\Vert \varphi\Vert  \leq \omega_1$. 
$\blacksquare$

<i>Solution.</i> By repeating the proof <a href="#ex24.2">Exercise 24.2</a>, in which we instead apply Lemma 24.3 with $\varphi(\alpha) = \alpha$. We have $\Vert \varphi\Vert  = \omega_1$ by <a href="#lem24.7.B">Lemma 24.7.B</a>. Note that by the hypothesis, $\aleph_\alpha^{\aleph_1} = \aleph_\alpha^{\aleph_0} \cdot 2^{\aleph_1} < \aleph_{\omega_1}$. Thus, by Lemma 24.3 we have that if $\aleph_\alpha^{\aleph_0} \leq \aleph_{\alpha+\alpha}$ for all $\alpha < \omega_1$, then $\aleph_{\omega_1}^{\aleph_1} \leq \aleph_{\omega_1+\omega_1}$. Then repeat the proof of Lemma 8.15 to conclude that the assertion in the exercise holds. 
$\square$

<a name="ex24.8"></a>
## Exercise 24.8.
<i>Solution.</i> Note that we have to further assume that $\kappa$ is singular, as otherwise this would contradict Easton's Theorem 15.18. Under this additional assumption, the hypothesis of <a href="#ex24.9">Exercise 24.9</a> is fulfilled and so $2^\kappa = \kappa^{\cf(\kappa)} < \aleph_\gamma$. 
$\square$

<a name="ex24.9"></a>
## Exercise 24.9.
<i>Solution.</i> Using the same proof, Lemma 24.3 may be generalised to singular cardinals in the following manner:

<b>Theorem.</b> {\itshape Let $\aleph_\eta$ be a singular cardinal, and assume $\aleph_\alpha^{\cf(\eta)} < \aleph_\eta$ for all $\alpha < \eta$. Let $\varphi : \cf(\eta) \to \eta$ and let $F$ be an almost disjoint family of functions:

$$
\begin{align*}
F \subseteq \prod_{\alpha < \cf(\eta)} A_\alpha
\end{align*}
$$

such that:

$$
\begin{align*}
\vert A_\alpha\vert  \leq \aleph_{\alpha + \varphi(\alpha)}
\end{align*}
$$

for every $\alpha < \cf(\eta)$. Then $\vert F\vert  \leq \aleph_{\eta + \Vert \varphi\Vert }$.}

But since $\vert \lbrace \varphi : \cf(\eta) \to \eta\rbrace\vert  = \vert \eta\vert ^{\cf(\eta)}$, we clearly have that $\Vert \varphi\Vert  \leq \vert \eta\vert ^{\cf(\eta)}$. Thus $\vert \eta + \vert \eta\vert ^{\cf(\eta)}\vert  = \vert \eta\vert ^{\cf(\eta)}$, so $\eta + \vert \eta\vert ^{\cf(\eta)} < (\vert \eta\vert ^{\cf(\eta)})^+ =: \gamma$, as desired. 
$\square$

\section{Exercise 24.10. (IP)}
\begin{setup}[<a href="#ex24.10">Exercise 24.10</a>]
The next exercise uses the notation from Chapter 8. Let $\kappa$ be a regular uncountable cardinal, let $M_0 = \kappa$, $M_{\eta+1} = \Tr(M_\eta)$, $M_\eta = \bigcap_{\nu<\cf{\eta}} M_{\xi_\nu}$ or $M_\nu = \bigtriangle_{\nu<\kappa} M_{\xi_\nu}$ (if $\cf{\eta} = \kappa$) as long as $M_\eta$ is stationary.
\end{setup}

Let $f_\eta$, $\eta < \kappa^+$, be the canonical functions on $\kappa$. Let $S_\eta = \lbrace \alpha < \kappa : o(\alpha) = f_\eta(\alpha)\rbrace$. Show that $S_\eta = M_\eta - M_{\eta+1}$ mod $I_\NS$ and that $o(S) = \eta$ for every stationary $S \subseteq S_\eta$.

<a name="lem24.10.A"></a>
<b>Lemma 24.10.A.</b> Let $S,T$ be stationary subsets of some $\alpha$. Then:

$$
\begin{align*}
o(S \cup T) = \min\lbrace o(S),o(T)\rbrace
\end{align*}
$$

<i>Proof.</i> Suppose not. Let $S \cup T$ be a $<$-minimal counterexample. Then $o(S \cup T) = \alpha$, and $o(S),o(T) > \alpha$. There exist $X < S$, $Y < T$ both of order $\alpha$. Since $X \cup Y < S \cup T$, $o(X \cup Y) = \alpha$ by minimality of counterexample. But this implies that $o(S \cup T) > o(X \cup Y) = \alpha$, a contradiction. 
$\blacksquare$

<b>Definition.</b>. A <b>largest set of order $\alpha$</b> is a stationary set $M$ such that $o(M) = \alpha$, and if $S$ is a stationary set with $o(S) = \alpha$, then $S \subseteq M$ mod $I_\NS$.

<a name="lem24.10.B"></a>
<b>Lemma 24.10.B.</b> Let $E_\eta$ be the canonical stationary set of order $\eta$. Then $M := E_\eta \cup \Tr(E_\eta)$ is the largest stationary set of order $\eta$, and $E_\eta = M - \Tr(M)$.

<i>Proof.</i> We first show that $M$ is the largest set of order $\eta$ mod $I_{\NS}$. Now by <a href="#lem24.10.A">Lemma 24.10.A</a>, $o(M) = \min\lbrace o(E_\eta),o(\Tr(E_\eta))\rbrace = \eta$. Let $S$ be stationary of order $\eta$. Write $S = A \cup B$, where $A \subseteq E_\eta$ and $B \cap E_\eta = \emptyset$. By condition (i) of $E_\eta$, $o(A) = \eta$ and by condition (ii), $o(B) > \eta$. Therefore, by <a name="#8#lem8.13.E">Lemma 8.13.E</a> we have that $E_\eta < B$, i.e. $B \subseteq \Tr(E_\eta)$ mod $I_{\NS}$. Thus $A \cup B \subseteq E_\eta \cup \Tr(E_\eta) = M$, as desired.

We now show that $E_\eta = M - \Tr(M)$. Begin by observing that $o(\Tr(E_\eta)) > \eta$, so $E_\eta \cap \Tr(E_\eta)$ must be non-stationary - to see this, suppose it is stationary. By condition (i) of $E_\eta$, $o(E_\eta \cap \Tr(E_\eta)) = \eta$, yet $o(E_\eta \cap \Tr(E_\eta)) \geq o(\Tr(E_\eta)) > \eta$ by <a name="#8#lem8.13.B">Lemma 8.13.B</a>, a contradiction. Therefore, we have that $E_\eta = M - \Tr(E_\eta)$ mod $I_{\NS}$. It suffices to show that $\Tr(E_\eta) = \Tr(M)$.

Since $o(\Tr(M)) > \eta$, by <a name="#8#lem8.13.E">Lemma 8.13.E</a> we have that $E < \Tr(M)$, i.e. $\Tr(M) \subseteq \Tr(E)$. On the other hand, $E \subseteq M$ by <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.11(i)">Exercise 8.11(i)</a>, $\Tr(E) \subseteq \Tr(M)$. This completes the proof. 
$\blacksquare$

<a name="lem24.10.C"></a>
<b>Lemma 24.10.C.</b> Let $M$ be the largest stationary set of order $\eta$. Then for any stationary set $S$, we have $o(S) \geq \eta$ iff $S \subseteq M$ mod $I_\NS$.

<i>Proof.</i> <u>$\implies$</u>: If $o(S) > \eta$, then by <a name="#8#lem8.13.E">Lemma 8.13.E</a> we have that $S \subseteq \Tr(E_\eta) \subseteq M$ mod $I_\NS$ and if $o(S) = \eta$ then $S \subseteq M$ mod $I_\NS$ by definition of $M$.

<u>$\impliedby$</u> If $S \subseteq M = E_\eta \cup \Tr(E_\eta)$, then $S = A \cup B$ where $A \subseteq E_\eta$ and $B \subseteq \Tr(E_\eta)$ mod $I_\NS$ (as $E_\eta \cup \Tr(E_\eta))$ is non-stationary, as seen in the prove of <a href="#lem24.10.B">Lemma 24.10.B</a>). If $A$ is stationary, then $o(A) = \eta$ by condition (i) of $E_\eta$, and if $B$ is stationary then $o(B) \geq o(\Tr(E_\eta)) > \eta$. Therefore, by <a href="#lem24.10.A">Lemma 24.10.A</a> we have that $o(S) \geq \eta$. 
$\blacksquare$

<a name="lem24.10.D"></a>
<b>Lemma 24.10.D.</b> Let $\eta < \kappa^+$. There exists a closed unbounded subset $D \subseteq \kappa$ such that for all regular cardinals $\alpha \in D$, $f_\eta\restrictedto\alpha$ is the $f_\eta(\alpha)^\text{th}$ canonical function on $\alpha$ (up to $I_{\NS}$).

<i>Proof.</i> Let $\lbrace f_\eta : \eta < \kappa^+\rbrace$ be the canonical functions on $\kappa$ constructed in the way of the proof of Lemma 24.5. We refer to this construction as the <b>canonical construction</b>.

We induct on $\eta$. The base case $\eta = 0$ and the successor case are trivial. We split the case where $\eta$ is a limit ordinal to two cases.

Suppose $\cf(\eta) < \kappa$. Let $\lbrace \xi_\nu : \nu < \cf(\eta)\rbrace$ be a sequence converging to $\eta$. By the induction hypothesis, for each $\nu < \cf(\eta)$ there exists a closed unbounded set $C_\nu$ such that for all $\alpha \in C_\nu$, $f_{\xi_\nu}\restrictedto\alpha$ is the canonical function on $\alpha$ of norm $f_{\xi_\nu}(\alpha)$. Let $C := \bigcap_{\nu<\cf(\eta)} C_\nu$, where $C$ remains closed unbounded. Following the canonical construction, we have that $f_\eta(\alpha) = \sup_{\nu<\cf(\eta)} f_{\xi_\nu}(\alpha)$ for all $\alpha < \kappa$, which gives $f_\eta\restrictedto\alpha = \sup_{\nu<\eta} f_{\xi_\nu}\restrictedto\alpha$. This is consistent with the canonical construction. Furthermore, each $f_{\xi_\nu}\restrictedto\alpha$ is the $f_{\xi_\nu}(\alpha)^\text{th}$ canonical function on $\alpha$, so $f_\eta$ is the $\bb{\sup_{\nu<\cf(\eta)} f_{\xi_\nu}(\alpha)}^\text{th}$ canonical function on $\alpha$.

The case where $\cf(\eta) = \kappa$ is similar, but we replace $<\!\kappa$-intersections (supremums) with diagonal intersections (supremums). 
$\blacksquare$

<i>Solution.</i> We will proceed in two steps. Let $E_\eta$ be the canonical stationary set of order $\eta$. Since the set of all successor ordinals below $\kappa$ is non-stationary, we may amend the definition of $M_0$ to $M_0 := \Lim(\kappa)$, the set of all limit ordinals below $\kappa$, without any issues.

<b>Step 1 - Show that $E_\eta = M_\eta - M_{\eta+1}$</b>: We shall show that $M_\eta$ is in fact the largest set of order $\eta$ (it's clear from definition that the largest set of order $\eta$ is always unique up to $I_{\NS}$). Then the identity $E_\eta = M_\eta - M_{\eta+1}$ follows from <a href="#lem24.10.B">Lemma 24.10.B</a>.

We induct on $\eta$. Clearly $M_0 = \kappa$ is the largest set of order $0$. Suppose $M_\eta$ is the largest set of order $\eta$. Let $M$ be the largest set of order $\eta + 1$, so $M_{\eta+1} \subseteq M$ mod $I_\NS$ by <a href="#lem24.10.C">Lemma 24.10.C</a> (since $o(M_{\eta+1}) \geq o(M_\eta) + 1 = \eta + 1$). Conversely, since $o(M) > \eta$, we have that $M \subseteq \Tr(E_\eta)$ by <a name="#8#lem8.13.E">Lemma 8.13.E</a>. By <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.11(i)">Exercise 8.11(i)</a> and induction hypothesis, $E_\eta \subseteq M_\eta$ so $\Tr(E_\eta) \subseteq \Tr(M_\eta) = M_{\eta+1}$.

Now suppose $\eta$ is a limit ordinal, and let $M$ be the largest set of order $\eta$. Since $M_\eta \subseteq M_\nu$ for all $\nu < \eta$ and $o(M_\nu) = \nu$ by induction hypothesis, we have that $o(M_\eta) \geq \eta$, so $M_\eta \subseteq M$ mod $I_\NS$ by <a href="#lem24.10.C">Lemma 24.10.C</a>. Conversely, since $M$ is stationary and $o(M) = \eta$, we have that $M \subseteq M_\nu$ mod $I_\NS$ for all $\nu < \eta$ by induction hypothesis. By observing that $M_\eta$ is in fact the infimum of $\lbrace M_\nu : \nu < \eta\rbrace$ in the Boolean algebra $P(\kappa)/I_\NS$, we conclude that $M \subseteq M_\eta$ mod $I_\NS$. Hence $M_\eta$ is the largest set of order $\eta$.

<b>Step 2 - Show that $S_\eta = E_\eta$:</b> We induct on $\kappa$ By Step 1 and the identity $f_{\eta+1} = f_\eta + 1$, is suffices to show that for all $\eta$:

$$
\begin{align*}
M_\eta = \lbrace \alpha < \kappa : o(\alpha) \geq f_\eta(\alpha)\rbrace
\end{align*}
$$

We induct on $\eta < \kappa^+$. We first note that for $\eta < \kappa$, the canonical construction of $f_\eta$ dictates that $f_\eta(\alpha) = \eta$ for all $\alpha$. Thus, for $\eta < \kappa$ we wish to prove that $M_\eta = \lbrace \alpha < \kappa : o(\alpha) \geq \eta\rbrace$, which is easy to prove by induction. We also note that since the canonical construction of $f_\eta$ "coincides" with that of $M_\eta$ when $\eta < \kappa^+$ is a limit ordinal, the inductive step for limit ordinals is also straightforward. Thus we may focus our attention on when $\eta + 1 > \kappa$.

We first note that if $E_\eta$ is non-empty, then we must have $o(\kappa) > \eta \geq \kappa$, and is therefore Mahlo by <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.14">Exercise 8.14</a>. To prove the case for $M_{\eta+1}$, we wish to show that for almost all $\alpha \in M_\eta$, we have that:

$$
\begin{align*}
o(\alpha) > f_\nu(\alpha) \iff \lbrace \xi < \alpha : o(\xi) \geq f_\nu(\xi)\rbrace \text{ is stationary in $\alpha$}
\end{align*}
$$

By <a href="#lem24.10.D">Lemma 24.10.D</a>, there exists a closed unbounded subset $D \subseteq \kappa$ such that
 
$\square$

<b>Remark.</b>. The sets $S_\eta$ are the <b>canonical stationary sets</b> (of order $\eta$).

<b>Note.</b>. This definition coincides with the same definition presented in <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.13">Exercise 8.13</a>.

<a name="ex24.11"></a>
## Exercise 24.11.
<i>Solution.</i> In fact, given an arbitrary cardinal $\kappa$ it is easy to find a partial order of cofinality $\kappa$. We consider the partial order $(\kappa,<^\ast )$, where under $<^\ast $ every two elements in $\kappa$ are incomparable. Then the only cofinal subset of $\kappa$ under $<^\ast $ is $\kappa$ itself, so the cofinality of $(\kappa,<^\ast )$ is $\kappa$. 
$\square$

<a name="ex24.12"></a>
## Exercise 24.12.
<i>Solution.</i> The statement in the exercise is false as stated. This is because the lexicographical ordering on $\omega \times \omega_1$ is a linear ordering, and every linear order has true cofinality (as the whole set is itself a cofinal chain).

Instead, we shall show that if we define $<$ on $\omega \times \omega_1$ by:

$$
\begin{align*}
(\alpha,\beta) < (\gamma,\eta) \iff \alpha < \gamma \wedge \beta < \eta
\end{align*}
$$

then $(\omega \times \omega_1,<)$ has no true cofinality (note that $<$ is clearly a partial order). To see this, let $C \subseteq \omega \times \omega_1$ be a chain. Suppose $C = \lbrace (\alpha_i,\beta_i) : i < \vert C\vert \rbrace$ such that $i < j \implies (\alpha_i,\beta_i) < (\alpha_j,\beta_j)$. Then $\lbrace \alpha_i : i < \vert C\vert \rbrace$ is an infinite subset of $\omega$ of size $\vert C\vert $, so we must have $\vert C\vert  = \aleph_0$. Let $\beta := \sup_{i<\omega} \beta_i$. Then $(0,\beta+1) \not\leq (\alpha_i,\beta_i)$ for all $i < \omega$, as $\beta + 1 > \beta_i$. Hence every chain of $\omega \times \omega_1$ is not cofinal. 
$\square$

<a name="ex24.13"></a>
## Exercise 24.13.
<i>Solution.</i> Clearly $d$ is an upper bound, as $c_\gamma(\alpha) < d(\alpha)$ on a tail segment of $\omega_1$, and all bounded subsets of $\omega_1$ are non-stationary. Let $f$ be an upper bound of $\lbrace c_\gamma : \gamma < \omega_1\rbrace$, and suppose for a contradiction that $\lbrace \alpha < \omega_1 : f(\alpha) < d(\alpha)\rbrace \notin I$, i.e. it is stationary. Then $f$ is regressive on a stationary set, so by Fodor's theorem there exists some stationary subset $S$ such that $f$ takes a constant value $\gamma$ for all $\alpha \in S$. This means that $\lbrace \alpha < \omega_1 : c_\gamma(\alpha) \geq f(\alpha)\rbrace \notin I$, so $c \not<_I f$, contradicting that $f$ is an upper bound. Thus $d \leq_I f$ necessarily.

We now show that $d$ is not an exact upper bound. By Solovay's Theorem 8.10, there exists a partition $\lbrace S_\gamma : \gamma < \omega_1\rbrace$ of stationary subsets of $\omega_1$. Let $T_\gamma := S_\gamma - (\gamma + 1)$. Clearly $T_\gamma$ remains stationary. Define $g : \omega_1 \to \omega_1$ by stipulating that:

$$
\begin{align*}
g(\alpha) =
\begin{cases}
\gamma, &\text{if $\alpha \in T_\gamma$} \\
0, &\text{if $\alpha \notin T_\gamma$ for all $\gamma$}
\end{cases}
\end{align*}
$$

Since the $T_\gamma$'s are disjoint, $g$ is well-defined. We see that for any $\gamma$, we we have that $T_{\gamma+1} \subseteq \lbrace \alpha < \omega_1 : g(\alpha) > c_\gamma(\alpha)\rbrace$, so $g \not\leq_I c_\gamma$. To see that $g <_I d$, we have that:

$$
\begin{align*}
\lbrace \alpha < \omega_1 : g(\alpha) \geq \alpha\rbrace &= \lbrace \alpha < \omega_1 : (\exists \gamma \geq \alpha) \, \alpha \in T_\gamma\rbrace \\
&= \ss{\alpha < \omega_1 : \alpha \in \bigcup_{\gamma \geq \alpha} T_\gamma} \\
&= \bigcup_{\gamma < \omega_1} (\gamma + 1) \cap S_\gamma \\
&= \emptyset \in I
\end{align*}
$$

as desired. 
$\square$