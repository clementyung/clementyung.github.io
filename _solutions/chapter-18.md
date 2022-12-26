---
title: "18) Large Cardinals and $L$
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-18
excerpt: ""
---

{ % include commands.html % }

<a name="ex18.1"></a>
## Exercise 18.1.
<i>Solution.</i> By Lemma 17.29, we have that $\kappa \to (\alpha)_{2^{\aleph_0}}^{<\omega}$, so by Lemma 17.24, $(\L_\kappa,\in)$ has a set of indiscernibles of order-type $\omega_1$. By Lemma 18.17, this implies that there exists a remarkable model, and hence $0^\sharp$ exists. 
$\square$

<b>Remark.</b>. In fact, by Theorem 9.19 of Kanamori's <i>The Higher Infinite</i>, if such a cardinal exists then $x^\sharp$ exists for all $x \subseteq \omega$.

<a name="ex18.2"></a>
## Exercise 18.2.
<i>Solution.</i> The hint basically settles the problem, with the exception that $M[G]$ is not an inner model of $M$. However, the proof of Lemma 18.19 actually allows us to use the equivalence "$0^\sharp$ exists iff $0^\sharp \in M$" for transitive models of $\ZF$ such that $\omega_1 \subseteq M[G]$. See Corollary 14.12 of Kanamori's <i>The Higher Infinite</i>. 
$\square$

<a name="ex18.3"></a>
## Exercise 18.3.
<i>Solution.</i> We expand on the hint. Since every element of $L$ is definable from $I$, let $t_\alpha$ be the Skolem term such that $A \cap \alpha = t_\alpha(\gamma_1^\alpha,\dots,\gamma_{n(\alpha)}^\alpha,\alpha,\delta_1^\alpha,\dots,\delta_{k(\alpha)}^\alpha)$, with the parameters increasing. By indiscernibility, we have:

$$
\begin{align*}
A \cap \alpha = t_\alpha(\gamma_1^\alpha,\dots,\gamma_{n(\alpha)}^\alpha,\alpha,\aleph_2,\dots,\aleph_{k(\alpha)+1})
\end{align*}
$$

Not consider the map $\alpha \mapsto (t_\alpha,\gamma_1^\alpha,\dots,\gamma_{n(\alpha)}^\alpha,k(\alpha))$ on $\omega_1$. Since there are only countably many Skolem terms and the tuple of $\gamma_i^\alpha$'s are countable, the set of all such tuples is also countable, the pre-image of at least one $(t_\alpha,\gamma_1^\alpha,\dots,\gamma_{n(\alpha)}^\alpha,k(\alpha))$ must be uncountable (and hence $f_{-1}(t_\alpha,\gamma_1^\alpha,\dots,\gamma_{n(\alpha)}^\alpha,k(\alpha)) \subseteq \omega_1$ is unbounded). Call this tuple $(t,\gamma_1,\dots,\gamma_n,k)$, and we have that by Fodor's Theorem, there are stationary many $\alpha$'s such that:

$$
\begin{align}
\label{eq18.3.1}
A \cap \alpha = t(\gamma_1,\dots,\gamma_n,\alpha,\aleph_2,\dots,\aleph_{k+1}) \tag{18.3.1}
\end{align}
$$

Let $\varphi(\gamma_1,\dots,\gamma_n,\alpha,\aleph_2,\dots,\aleph_{k+1})$ be the formula denoting the equality (\ref{eq18.3.1}). Since $I \cap \omega_1$ is closed unbounded in $\omega_1$, there exists an $\alpha \in I \cap \omega_1$ such that $\varphi(\gamma_1,\dots,\gamma_n,\alpha,\aleph_2,\dots,\aleph_{k+1})$ holds. By indiscernibility:

$$
\begin{align*}
\varphi(\gamma_1,\dots,\gamma_n,\aleph_1,\aleph_2,\dots,\aleph_{k+1})
\end{align*}
$$

also holds, that is:

$$
\begin{align*}
A = t(\gamma_1,\dots,\gamma_n,\aleph_1,\aleph_2,\dots,\aleph_{k+1})
\end{align*}
$$

as we wanted. 
$\square$

<a name="ex18.4"></a>
## Exercise 18.4.
<i>Solution.</i> The hint solves the problem - we may let $\phi$ be a formula such that for $\gamma \in I \cap \kappa$ and $\gamma > \alpha_n$:

$$
\begin{align*}
\phi(\alpha_1,\dots,\alpha_n,\gamma,\beta_1,\dots,\beta_m) \iff \gamma \in X
\end{align*}
$$

By indiscernibility, we have that $\lbrace \gamma \in I : \alpha_n < \gamma < \kappa\rbrace$ is a subset of either $X$ or $\kappa - X$. The fact that this set is closed unbounded follows from closed and unbounded properties of $I$. 
$\square$

<a name="ex18.5"></a>
## Exercise 18.5.
<a name="lem18.5.A"></a>
<b>Lemma 18.5.A.</b> Let $M$ be a transitive model of $\ZFC$. Let $D$ be an $M$-ultrafilter such that $D \subseteq F$ for some $\sigma$-complete filter $F$. Then the model $\Ult_D(M)$ is well-founded.

<i>Proof.</i> Suppose $\Ult_D(M)$ is not well-founded, so there exists a descending sequence $[f_0] \ni^\ast  [f_1] \ni^\ast  \ldots$ of elements in $\Ult_D(M)$. In other words the sets $X_n := \lbrace \alpha \in \kappa : f_n(\alpha) \in f_{n+1}(\alpha)\rbrace$ lie in $D$ for all $n$. Since $D \subseteq F$ and $F$ is $\sigma$-complete, $X := \bigcap_{n<\omega} X_n \in F$. In particular, $X$ is non-empty, so for any $\alpha \in X$ we have that $f_0(\alpha) \ni f_1(\alpha) \ni \ldots$, a contradiction. 
$\blacksquare$

<i>Solution.</i> The hint solves the problem, with the only non-trivial assertion being that $\Ult_D(L)$ being well-founded (note that in general, $D$ being a $\sigma$-complete $M$-ultrafilter is not sufficient to ensure that $\Ult_D(M)$ is well-founded). This follows from applying <a href="#lem18.5.A">Lemma 18.5.A</a> to the fact that $D$ lies in the closed unbounded filter of $\kappa$, which is $\kappa$-complete. 
$\square$

<a name="ex18.6"></a>
## Exercise 18.6.
<a name="lem18.6.A"></a>
<b>Lemma 18.6.A.</b> Let $B$ be an algebra of subsets of $\kappa$ such that $\vert B\vert  = \kappa$. Then there exists a $\kappa$-complete algebra $B'$ of subsets of $\kappa$ such that $\vert B'\vert  = \kappa$ and $B \subseteq B'$.

<i>Proof.</i> For $\alpha < \kappa$, we shall define algebras $B_\alpha$ of subsets of $\kappa$ such that:
<ol>
<li> $\vert B_\alpha\vert  = \kappa$ for all $\alpha < \kappa$..</li>
<li> If $\beta < \alpha$, then $B_\beta \subseteq B_\alpha$.</li>

<li> If $\mathcal{X} \subseteq B_\alpha$ and $\vert \mathcal{X}\vert  < \kappa$, then $\bigcap \mathcal{X} \in B_{\alpha+1}$ and $\bigcup \mathcal{X} \in B_{\alpha+1}$..</li></ol>
Let $B_0 := B$. If $\alpha$ is a limit ordinal, let $B_\alpha := \bigcup_{\beta<\alpha} B_\beta$, which is still an algebra of sets as it is an increasing union of algebras of sets by induction hypothesis. Also, since $\vert B_\beta\vert  = \kappa$ for all $\beta < \alpha$ and $\alpha < \kappa$, the regularity of $\kappa$ implies that $\vert B_\alpha\vert  = \kappa$. If $B_\alpha$ is defined, we let:

$$
\begin{gather*}
S := \ss{\bigcup \mathcal{X} : \mathcal{X} \subseteq B_\alpha \wedge \vert \mathcal{X}\vert  < \kappa} \\
T := \ss{\bigcap \mathcal{X} : \mathcal{X} \subseteq B_\alpha \wedge \vert \mathcal{X}\vert  < \kappa} \\
B_{\alpha+1} := \func{cl}(S \cup T)
\end{gather*}
$$

where $\func{cl}$ here means take the closure of the set under finite union and intersection. Clearly $B_\alpha \subseteq B_{\alpha+1}$ (for $b \in B_\alpha$, $\vert \lbrace b\rbrace\vert  < \kappa$) and (iii) is satisfied. To show that $B_{\alpha+1}$ is indeed a Boolean algebra, it remains to show that $B_{\alpha+1}$ is closed under taking complement.

<b>Claim.</b>. \hfill
<ol>
<li> If $X \in S$ and $Y \in S$, then $X \cup Y \in S$ and $X \cap Y \in S$.</li>

<li> If $X \in T$ and $Y \in T$, then $X \cup Y \in T$ and $X \cap Y \in T$..</li></ol>

<i>Proof.</i> We only show for the case of $X \cup Y$ - the case for $X \cap Y$ is symmetric.
<ol>
<li> We have $X = \bigcup \mathcal{X}$ and $Y = \bigcup \mathcal{Y}$ where $\vert \mathcal{X}\vert ,\vert \mathcal{Y}\vert  < \kappa$. Then $\vert \mathcal{X} \cup \mathcal{Y}\vert  < \kappa$, and $X \cup Y = \bigcup (\mathcal{X} \cup \mathcal{Y}) \in S$.</li>

<li> We have $X = \bigcap \mathcal{X}$ and $Y = \bigcap \mathcal{Y}$ where $\vert \mathcal{X}\vert ,\vert \mathcal{Y}\vert  < \kappa$. WLOG assume that $\vert \mathcal{X}\vert  \leq \vert \mathcal{Y}\vert  = \lambda$. Write $\mathcal{X} = \lbrace X_\gamma : \gamma < \lambda\rbrace$ and $\mathcal{Y} := \lbrace Y_\gamma : \gamma < \lambda\rbrace$, where $X_\gamma = X_0$ for $\vert X\vert  \leq \gamma < \lambda$. Let $Z_\gamma := X_\gamma \cap Y_\gamma$, and let $\mathcal{Z} := \lbrace Z_\gamma : \gamma < \lambda\rbrace$. Then $\mathcal{Z} \subseteq B_\alpha$ (as $B_\alpha$ is an algebra of sets), and $\vert \mathcal{Z}\vert  < \kappa$ so $Z := \bigcap \mathcal{Z} \in T$. It's easy to check that $Z = X \cap Y$.</li>
</ol> 
$\blacksquare$

Thus by the claim, we have that every element in $B_{\alpha+1}$ is of the form $X \cup Y$ or $X \cap Y$, where $X \in S$ and $Y \in T$. Write $X = \bigcup \mathcal{X}$ and $Y = \bigcap \mathcal{Y}$. for elements of the form $X \cup Y$, we have:

$$
\begin{align*}
\kappa - (X \cup Y) = (\kappa - X) \cap (\kappa - Y) = \bigcap \bar{\mathcal{X}} \cup \bigcup \bar{\mathcal{Y}}
\end{align*}
$$

where $\bar{\mathcal{X}} := \lbrace \kappa - A : A \in \mathcal{X}\rbrace$ and $\bar{\mathcal{Y}} := \lbrace \kappa - A : A \in \mathcal{Y}\rbrace$. Since $B_{\alpha+1}$ is closed under finite intersection, we clearly have $\kappa - (X \cup Y) \in B_{\alpha+1}$. The case for elements of the form $X \cap Y$ is similar. From this we also see that:

$$
\begin{align*}
B_{\alpha+1} = \lbrace X \cup Y : X \in S \wedge Y \in T\rbrace \cup \lbrace X \cap Y : X \in S \wedge Y \in T\rbrace \tag{$*$}
\end{align*}
$$

We now show that $\vert B_{\alpha+1}\vert  = \kappa$. From ($*$), it suffices to show that $\vert S \cup T\vert  = \kappa$. As mentioned, we have $B_\alpha \subseteq S$ and $B_\alpha \subseteq T$, so $\vert S\vert ,\vert T\vert  \geq \kappa$. On the other hand, consider the map $F : [B_\alpha]^{<\kappa} \to S$ defined by $F(\mathcal{X}) := \bigcup \mathcal{X}$. By definition of $S$, $F$ is onto, so $\vert S\vert  \leq \vert [B_\alpha]^{<\kappa}\vert  = \kappa^{<\kappa} = \kappa$ as $\kappa$ is inaccessible. The case is similar for $T$.

We now finish the proof of the lemma. Let $B' := \bigcup_{\alpha<\kappa} B_\alpha$. $B'$ is the union of an increasing sequence of algebra of sets, hence is itself an algebra of sets. Let $\mathcal{X} \subseteq B'$ such that $\vert \mathcal{X}\vert  < \kappa$. Since $\kappa$ is regular, there exists some $\alpha < \kappa$ such that $\mathcal{X} \subseteq B_\alpha$. Then $\bigcup \mathcal{X} \in B_{\alpha+1}$ and $\bigcap \mathcal{X} \in B_{\alpha+1}$, so $\mathcal{B}$ is $\kappa$-complete. Finally, since $\vert B_\alpha\vert  = \kappa$ for all $\alpha < \kappa$, $\vert B'\vert  = \kappa$. 
$\blacksquare$

<i>Solution.</i> Let $B := P^L(\kappa)$. Since $\vert (2^\kappa)^L\vert  = \vert (\kappa^+)^L\vert  = \kappa$, $\vert B\vert  = \kappa$. By <a href="#lem18.6.A">Lemma 18.6.A</a>, there exists a (non-trivial) $\kappa$-complete algebra of subsets of $\kappa$, $B'$, extending $B$. Since $\kappa$ is weakly compact, by <a href="https://clementyung.github.io/jech-solutions/chapter-17#ex17.19">Exercise 17.19</a> there exists a non-principal $\kappa$-complete ultrafilter $U$ of $B'$. Since $P^L(\kappa) \subseteq B'$, $U \cap L$ forms a $\kappa$-complete $L$-ultrafilter. By <a href="#lem18.5.A">Lemma 18.5.A</a>, $\Ult_{U \cap L}(L)$ is well-founded, so there exists a non-trivial elementary embedding $j : L \to L$. 
$\square$

<a name="ex18.7"></a>
## Exercise 18.7.
<i>Solution.</i> As in the remark preceding Kunen's Theorem 18.20, we may extend $j$ to an elementary embedding by stipulating that:

$$
\begin{align*}
j(t^L[\gamma_1,\dots,\gamma_n]) := t^L[j(\gamma_1),\dots,j(\gamma_n)]
\end{align*}
$$

Clearly $\crit(j) \leq i_\omega$. Now let $\alpha < i_\omega$. Then $\alpha < i_n$ for some $n < \omega$, so $\alpha \in L_{i_n}$. Thus $\alpha$ is definable in $(L_{i_n},\in)$ from $I \cap i_n = \lbrace i_0,\dots,i_{n-1}\rbrace$, so for some formula $\varphi$, $\alpha$ is the unique $a$ such that $\varphi[a,\gamma_1,\dots,\gamma_k]$, where $\gamma_1,\dots,\gamma_k \in I \cap i_n$. Since $j(i_m) = i_m$ for all $m < \omega$, we have that $j(\varphi[a,\gamma_1,\dots,\gamma_k]) = \varphi[j(a),\gamma_1,\dots,\gamma_k]$. By uniqueness of $a$, $j(a) = a$, i.e. $j(\alpha) = \alpha$. Hence $\crit(j) = i_\omega$. 
$\square$

<a name="ex18.8"></a>
## Exercise 18.8.
<i>Solution.</i> Define $j : I \to I$ by stipulating that:

$$
\begin{align*}
j(i_\alpha) :=
\begin{cases}
i_\alpha, &\text{if $\alpha < \omega$} \\
i_{\alpha+1}, &\text{if $\alpha \geq \omega$}
\end{cases}
\end{align*}
$$

Then $j$ is order-preserving, so by <a href="#ex18.7">Exercise 18.7</a> we may extend $j$ to an elementary embedding $j : L \to L$ with critical point $i_\omega$. By Lemma 17.32 (as $M = N = L$), $\kappa$ is ineffable in $L$. Indiscernibility then implies that $i_\alpha$ is ineffable in $L$ for all ordinals $\alpha$ (let $\varphi(x)$ be a formula with one free variable asserting that $x$ is an ineffable cardinal. Then $L \models \varphi[i_\omega]$, so $L \models \varphi[i_\alpha]$ for all $\alpha$. 
$\square$

<a name="ex18.9"></a>
## Exercise 18.9.
<i>Solution.</i> Let $H := \lbrace i_n : n < \omega\rbrace$. We shall show that $H$ is homogeneous for $f$. For each $n$, since $f$ is definable let $\varphi$ be the formula stipulating that:

$$
\begin{align*}
\varphi(x_1,\dots,x_n) \iff f(\lbrace x_1,\dots,x_n\rbrace) = 0
\end{align*}
$$

But indiscernibility, for $k_1 < \ldots < k_n$ we have that $\varphi[i_{k_1},\dots,i_{k_n}]$ holds the same truth value, i.e. $f(\lbrace i_{k_1},\dots,i_{k_n}\rbrace)$ takes the same value. This precisely means that $f$ is homogeneous on $[H]^{<\omega}$. 
$\square$

<a name="ex18.10"></a>
## Exercise 18.10.
<i>Solution.</i> Note that the sentence "$x$ is a cardinal and $x \to (\omega)^{<\omega}$" is definable, so call this sentence $\varphi(x)$. Let $\psi(y)$ be the sentence $\exists x < y \, \varphi(x)$. By <a href="#ex18.9">Exercise 18.9</a>, $L \models \psi[i_{\omega+1}]$, and so by indiscernibility we have that $L \models \psi[i_1]$. Hence there exists a cardinal $\kappa < i_1$ such that $\kappa \to (\omega)^{<\omega}$, so $(\eta_\omega)^L < i_1$. 
$\square$

<a name="ex18.11"></a>
## Exercise 18.11.
<i>Solution.</i> By Lemma 17.9(v), since the set of cardinals $\lbrace \lambda : \cf(\lambda) \neq \kappa\rbrace$ is a proper class, the elementary embedding $j_D$ fixes a proper class of cardinals. Now if $\kappa \notin I$, then $\kappa = t(\alpha_1,\dots,\alpha_k,\lambda_1,\dots,\lambda_n)$ with indiscernibles $\alpha_i < \kappa < \lambda_j$ for all $i,j$ (if $\kappa \in I$ then it may be that $\alpha_i = \kappa$ for some $i$ or $\lambda_j = \kappa$ for some $j$). Recall that $0^\sharp$ is the unique well-founded remarkable E.M. set, which is also the set of all true formulas in $L$. Thus formulas of the form (18.13) are true in $L$, so we may choose all the $\lambda_j$'s to be in the class $\lbrace \lambda : \cf(\lambda) \neq \kappa\rbrace$. Then $j_D(\lambda_j) = \lambda_j$ for all $j$. Since $\alpha_i < \kappa$, $j(\alpha_i) = \alpha_i$ for all $i$, so:

$$
\begin{align*}
j_D(\kappa) = t(j_D(\alpha_1),\dots,j_D(\alpha_k),j_D(\lambda_1),\dots,j_D(\lambda_n)) = t(\alpha_1,\dots,\alpha_k,\lambda_1,\dots,\lambda_n) = \kappa
\end{align*}
$$

a contradiction. 
$\square$

<a name="ex18.12"></a>
## Exercise 18.12.
<i>Solution.</i> Note that the constructible universe of a model of $\ZF$ (not necessarily satisfying $\AC$) is a model of $\ZFC$. Following the hint, let $\kappa := \omega_1$ and $\lambda := (\kappa^+)^L$, the successor cardinal of $\kappa$ in $L$, and let $X,Y$ be defined as such. Then $M := L[X,Y]$ is a model of $\ZFC$. If we proved the claim that $\kappa$ is a singular cardinal in $M$ and $\lambda$ is not a cardinal in $M$, then the consequence of Corollary 18.32 does not hold (since $L$ is absolute), so $(0^\sharp)^M$ exists. Thus $0^\sharp = (0^\sharp)^M$ exists (by Lemma 18.19).

It remains to prove that $\kappa$ is a singular cardinal in $M$ and $\lambda$ is not a cardinal in $L[X,Y]$. The first claim is clear - the statement "$\kappa$ is a cardinal" is downward absolute, and the set $X$ witnesses that $\kappa$ is singular. Since $\lambda = (\kappa^+)^L$, $\lambda \leq (\kappa^+)^{L[X,Y]}$ as $L \subseteq L[X,Y]$. But since $L[X,Y]$ is a model of $\ZFC$, we have that $(\kappa^+)^{L[X,Y]}$ is a regular cardinal in $L[X,Y]$, but $Y$ witnesses that $\lambda$ is singular. Thus $\lambda$ is not a cardinal in $L[X,Y]$, as desired. 
$\square$

<a name="ex18.13"></a>
## Exercise 18.13.
<i>Solution.</i> Following the hint, the only thing to prove is the following:

<b>Claim.</b>. Suppose the Covering Theorem for $L$ holds in $L[x]$ but fails in $L[0^\sharp,x]$. Then the Covering Theorem for $L[x]$ fails in $L[0^\sharp,x]$.

<i>Proof.</i> Suppose instead that the Covering Theorem for $L[x]$ holds in $L[0^\sharp,x]$. Let $X \in L[0^\sharp,x]$ be uncountable. By the Covering Theorem for $L[x]$, there exists a set $Y \subseteq X$ in $L[x]$ with $\vert Y\vert  = \vert X\vert $. Since the Covering Theorem for $L$ holds in $L[x]$, there exists a $Z \subseteq Y$ in $L$ with $\vert Z\vert  = \vert Y\vert  = \vert X\vert $. Thus the Covering Theorem for $L$ holds in $L[0^\sharp,x]$, a contradiction. 
$\blacksquare$ 
$\square$