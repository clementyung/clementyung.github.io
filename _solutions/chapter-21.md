---
title: "21) Large Cardinals and Forcing"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-21
excerpt: ""
---

{% include commands.html %}

<a name="ex21.1"></a>
## Exercise 21.1.
<i>Solution.</i> Clearly $\kappa \in W$ and $W$ is upward-closed. To see that, $W$ is $\kappa$-complete, fix $\gamma < \kappa$ and let $\lbrace X_\alpha : \alpha < \gamma\rbrace \subseteq W$. Let $p_0 \in G$ be such that $G \forces (\forall \alpha < \gamma) \, \dot{X}_\alpha \in \dot{J}$, where $\dot{X}_\alpha$ and $\dot{J}$ are names for $X_\alpha$ and $J$ respectively.

For each $\alpha < \gamma$, let $A_\alpha$ be the maximal antichain of $q \leq p_0$ such that there exists $Y_{\alpha,q} \in U$ which $q \forces \check{Y}_{\alpha,q} \subseteq \dot{X}_\alpha$. Then $\vert A_\alpha\vert  \leq \vert P\vert  < \kappa$, so by $\kappa$-completeness we have that:

$$
\begin{align*}
\bigcap_{\substack{\alpha<\gamma \\ q \in A_\alpha}} Y_{\alpha,q} \in U
\end{align*}
$$

Note that this sequence of $Y_{\alpha,q}$ can be defined inside $V$. It's then easy to see that $p_0 \forces \bigcap_{\alpha<\gamma} X_\alpha \supseteq Y$, so $\bigcap_{\alpha<\gamma} X_\alpha \in W$.

We now show that $W$ is an ultrafilter. The hint basically solves the problem, so we expand it a little. We first note that since $\kappa$ is inaccessible, we have $\lambda^{<\kappa} < \kappa$ for all $\lambda < \kappa$, so by <a href="https://clementyung.github.io/jech-solutions/chapter-15#ex15.1">Exercise 15.1</a> we have $\vert B\vert  \leq \vert P\vert ^{<\kappa} < \kappa$. Let $Y \in U$ such that $\Vert \alpha \in \dot{X}\Vert  = b$ is the same for all $\alpha \in Y$. Then:

$$
\begin{gather*}
\Vert Y \subseteq \dot{X}\Vert  = \Vert \forall \alpha \in Y \, (\alpha \in \dot{X})\Vert  = \prod_{\alpha \in Y} \Vert \alpha \in \dot{X}\Vert  = \prod_{\alpha \in Y} b = b \\
\Vert Y \subseteq \kappa - \dot{X}\Vert  = \Vert \forall \alpha \in Y \, (\alpha \notin \dot{X})\Vert  = \prod_{\alpha \in Y} -\Vert \alpha \in \dot{X}\Vert  = \prod_{\alpha \in Y} -b = -b
\end{gather*}
$$

Thus if $b \in G$ then $Y \subseteq X$, and $Y \subseteq \kappa - X$ otherwise. 
$\square$

<a name="ex21.2"></a>
## Exercise 21.2.
<i>Solution.</i> By <a href="https://clementyung.github.io/jech-solutions/chapter-15#ex15.1">Exercise 15.1</a> again, since $\kappa$ is inaccessible and $\vert P\vert  < \kappa$, we have $\vert B\vert  < \kappa$. Note that $C_b \in V$ for all $b \in B$. Now we have:

$$
\begin{align*}
C = \bigcup_{b \in G} C_b
\end{align*}
$$

Since $\vert G\vert  \leq \vert B\vert  < \kappa$ and $\kappa$ is regular, we have that $C_b$ is unbounded for some $b \in G$. Let $D$ be the closure of $C_b$. Then $D$ is definable from $C_b$ and $\kappa$, so $D \in V$. Since $C$ is closed, $D \subseteq C$. Thus, $D$ is a closed unbounded subset of $C$ in $V$. 
$\square$

<a name="ex21.3"></a>
## Exercise 21.3.
<i>Solution.</i> We consider two cases. If $I\restrictedto Z$ is a prime ideal for some $Z \subseteq \kappa$ with $\vert Z\vert  = \kappa$, then $F := \lbrace Z - X : X \in I\rbrace$ is a $\kappa$-complete nonprincipal ultrafilter over $Z$. Thus, $\vert Z\vert  = \kappa$ is a measurable cardinal.

Otherwise, let $F := \lbrace \kappa - X : X \in I\rbrace$, which is a $\kappa$-complete filter (so, in particular, $X \notin F$ for all $\vert X\vert  < \kappa$). We may construct a tree $T$ of sets in $F$ in a way similar to the proof of Lemma 10.9 as follows: Start with the zeroth level containing only $\emptyset$. If $T(n)$ (the $n^\text{th}$ level of the tree $T$) has been defined, then for

Given a tree $T$ we denote the $\alpha^\text{th}$ level of $T$ as $T(\alpha)$.  Define a tree $T$ of sets in $F$ as follows: $T(0) = \lbrace \kappa\rbrace$. If $X \in T(n)$, since $I\restrictedto X$ is not a prime ideal (as $\vert X\vert  = \kappa$), there exists some non-empty $Y,Z$, with $\vert Y\vert  = \vert Z\vert  = \kappa$, such that $Y \sqcup Z = X$. Then both $Y$ and $Z$ are in $T(n+1)$, and all sets in $T(n+1)$ are formed like this. The limit case is similar to that in the proof of Lemma 10.9. We may continue the argument as in that proof and conclude that $\kappa \leq 2^\nu$. 
$\square$

<a name="ex21.4"></a>
## Exercise 21.4.
<i>Solution.</i> Fix $\alpha < \kappa$. We first prove the statement in the hint that for all $p \in P$ there exists a $p' \leq p$ such that $P_{p'}$ is $\alpha$-closed. We let:

$$
\begin{align*}
p' :=
\begin{cases}
p \cup \lbrace \alpha\rbrace, &\text{if $p \subseteq \alpha$} \\
p, &\text{otherwise}
\end{cases}
\end{align*}
$$

Clearly $p' \in P$. To see that $P_{p'}$ is $\alpha$-closed, let $p' \geq p_0 > p_1 > \cdots > p_\beta > \cdots$, where $\beta < \alpha'$ and $\alpha' \leq \alpha$. Take $p_{\alpha'} := \bigcup_{\beta<\alpha'} p_\beta$. Then we see that $p_{\alpha'} \in P_{p'}$ - let $\gamma \leq \kappa$ be regular. If $\gamma > \alpha'$, then $\vert p_{\alpha'} \cap \gamma\vert  = \sup_{\beta<\alpha'} \vert p_\beta \cap \gamma\vert  < \gamma$ as $\vert p_\beta \cap \gamma\vert  < \gamma$ for all $\beta$, $\alpha' < \gamma$ and $\gamma$ is regular. If $\gamma \leq \alpha$, then $p' \cap \gamma = p \cap \gamma$, so $\vert p' \cap \gamma\vert  < \gamma$.

Now suppose for each $p$ and each $\alpha < \kappa$, we have $p_\alpha' \leq p$ such that $P_{p_\alpha'}$ is $\alpha$-closed. Let $Q := \bigcup_{p \in P} P_{p_\alpha'}$. Then $Q$ is $\alpha$-closed and dense inside $P$, so $P$ is $\alpha$-closed (and hence $\alpha$-distributive). Since $P$ and $Q$ are then forcing equivalent and forcing with $Q$ does not add any subsets of size $<\kappa$, so does $P$, so $P$ is $\alpha$-distributive. Then the proof finishes as usual: We have:

$$
\begin{align*}
f(\alpha) := \text{the unique $x$ such that $p_\gamma \forces \dot{f}(\alpha) = x$}
\end{align*}
$$

Since $p_\gamma \in V$, so does $f$.

We now show that $\kappa$ is not Mahlo in $V[G]$, where $G$ is a generic filter of $P$. Clearly $\bigcup G$ is unbounded, so by <a href="https://clementyung.github.io/jech-solutions/chapter-8#lem8.11(iii).A">Lemma 8.11(iii).A</a> $\Lim\bb{\bigcup G}$ is closed unbounded. Yet, we observe that all cardinals in $\Lim\bb{\bigcup G}$ are singular - indeed, if $\lambda$ is regular, then $\vert p \cap \lambda\vert  < \lambda$ for all $p \in G$. Thus, $\sup \bigcup\lbrace p \cap \lambda : p \in G\rbrace < \lambda$, i.e. $\lambda \notin \Lim\bb{\bigcup G}$. This implies that the set of regular cardinals below $\kappa$ avoids a closed unbounded set, so it is not stationary. 
$\square$

<a name="ex21.5"></a>
## Exercise 21.5.
<i>Solution.</i> If $U$ is a $\kappa$-complete non-principal ultrafilter of $\kappa$ in the ground model $V$, then $U$ remains a $\kappa$-complete non-principal ultrafilter in $V[G]$ as $P$ does not add new subsets of $\kappa$. 
$\square$

<a name="ex21.6"></a>
## Exercise 21.6.
<i>Solution.</i> To be precise, we wish to show that it is consistent <i>with the existence of a supercompact cardinal</i> that $2^{\cf(\kappa)} < \kappa$ and $\kappa^+ < \kappa^{\cf(\kappa)} < 2^\kappa$.

Start with the universe $V$. Following the hint, we obtain the Prikry model $V[G]$ in Corollary 21.13, in which there exists a strong limit cardinal $\kappa$ such that $2^\kappa > \kappa^+$ and $\cf(\kappa) = \omega$. This gives $2^{\cf(\kappa)} = 2^{\aleph_0} < \kappa$ (as $\kappa$ is uncountable and a strong limit cardinal in $V[G]$), and $\kappa^+ < 2^\kappa = \kappa^{\cf(\kappa)}$ (by (5.23)). Let $\lambda := (2^{2^{\kappa}})^{V[G]}$ (so in $V[G]$, $\lambda > 2^\kappa > \kappa$ and $\lambda^\kappa = \kappa$). Let $P$ be the partial order in (15.3), with $\kappa$ and $\lambda$ above. By <a href="https://clementyung.github.io/jech-solutions/chapter-5#ex5.23">Exercise 5.23</a>, we have that $2^{<\kappa} = \kappa$ in $V[G]$, so by an argument similar to that of Lemma 15.4 we have that and $P$ satisfies the $\kappa^+$-chain condition. Let $H$ be $V[G]$-generic on $P$. Then in $V[G][H]$, $\kappa^+$ remains regular and all cardinals $\leq\kappa$ are preserved. Since $P$ is $<\!\kappa$-closed, no new countable subsets are added so $2^{\aleph_0}$ and $\kappa^{\aleph_0}$ are preserved. All cardinals below $\kappa$ are also preserved. On the other hand, we have:

$$
\begin{align*}
(2^{\kappa})^{V[G][H]} = (2^{2^{\kappa}})^{V[G]} > (2^{\kappa})^{V[G]} = (\kappa^{\aleph_0})^{V[G]} = (\kappa^{\aleph_0})^{V[G][H]}
\end{align*}
$$

which gives the desired model. 
$\square$

<a name="ex21.7"></a>
## Exercise 21.7.
\begin{setup}[<a href="#ex21.7">Exercise 21.7</a>]
The Prikry model $V[G]$ of Theorem 21.10 provides an example of a singular Rowbottom cardinal. The exercise below shows that $\kappa$ has in $V[G]$ the combinatorial property equivalent to being a Rowbottom cardinal.
\end{setup}

<i>Proof.</i> We prove the equivalence. The proof is similar to that of <a href="https://clementyung.github.io/jech-solutions/chapter-17#ex17.31">Exercise 17.31</a>.

Suppose $\kappa$ is Rowbottom. We note that $(\kappa,\lambda,<,F\restrictedto[\kappa]^n)_{n \in \omega}$ is a model of type $(\kappa,\lambda)$. Since $\kappa$ is Rowbottom, there exists an elementary submodel $(H,H \cap \lambda,<,F\restrictedto[H]^n)_{n \in \omega}$ which is of type $(\kappa,\aleph_0)$. In other words, $\vert H \cap \lambda\vert  = \aleph_0$, so $F\restrictedto[H]^n$ takes on at most countably many values for all $n$, so $F$ takes on at most countably many values on $[H]^{<\omega}$, as desired.

Now suppose the combinatorial property below holds for a cardinal $\kappa$. Let $\A = (\kappa,\lambda,\dots)$ be a model of type $(\kappa,\lambda)$. Let $\lbrace h_n : n < \omega\rbrace$ be a set of Skolem functions for $\A$, arranged such that $h_n$ is $k(n)$-ary, where $k(n) \leq n$ for all $n$. Define $F : [\kappa]^{<\omega} \to \lambda$ by stipulating that:

$$
\begin{align*}
F(x_1,\dots,x_n) =
\begin{cases}
h_n(x_1,\dots,x_{k(n)}), &\text{if $h_n(x_1,\dots,x_{k(n)}) < \lambda$} \\
0, &\text{otherwise}
\end{cases}
\end{align*}
$$

By the combinatorial property, there exists a $H \subseteq \kappa$ of size $\kappa$ such that $F"([H]^{<\omega}) = \aleph_0$. Let $B := \bigcup_{n=0}^\infty h_n"([H]^{k(n)})$. By considering the formula $x = y$, we note that $H \subseteq B$ so $\vert B\vert  = \kappa$. Meanwhile, by definition of $H$ we also have $\vert B \cap \lambda\vert  = \aleph_0$. Thus, $\B := (B,\lambda \cap B,\dots)$ is a model of type $(\kappa,\aleph_0)$. We shall show that $\B \prec \A$, which completes the proof.

By <a name="#12#lem12.12.B">Lemma 12.12.B</a> it suffices to show that for all existential formulas $\exists y \, \varphi(x,y)$, if $\A \models \exists y \, \varphi(x,y)$ and $x \in B$. then $\B \models \exists y \, \varphi(x,y)$. But this follows from that if $h_n = h_\varphi$, then $h_n(x) \in B$, so indeed $\B \models \exists y \, \varphi(x,y)$. 
$\blacksquare$

In the Prikry model, for every partition $F : [\kappa]^{<\omega} \to \lambda$ into $\lambda < \kappa$ pieces there exists a set $H \subseteq \kappa$ of size $\kappa$ such that $F$ takes at most $\aleph_0$ values on $[H]^{<\omega}$.

\begin{hint}
Let $\dot{F}$ be a name for $F$ and let $(s_0,A_0)$ be a condition (such that $\max(s_0) < \min(A_0)$). Let $g$ be a partition of $[\kappa]^{<\omega} \times [\kappa]^{<\omega}$ into $\lambda$ pieces, defined as follows: If $s \in [A_0]^{<\omega}$ and for some $X \subseteq A_0$, $(s_0 \cup s, X) \forces \dot{F}(t) = \alpha$, then let $g(s,t) = \alpha$; otherwise, let $g(s,t) = 0$. Show that there is $A \subseteq A_0$ in $D$ and a countable $S \subseteq \lambda$ such that $g([A]^{<\omega} \times [A^{<\omega}]) \subseteq S$ [sic]\footnote{Replace "$g([A]^{<\omega} \times [A^{<\omega}]) \subseteq S$" with $g([A]^{<\omega} \times [A]^{<\omega}) \subseteq S$}. Then $(s_0,A) \forces \dot{F}([A]^{<\omega}) \subseteq S$.
\end{hint}

<a name="lem21.7.A"></a>
<b>Lemma 21.7.A.</b> Let $\kappa$ be a measurable cardinal, and let $D$ be a normal measure on $\kappa$. For every partition $g : [\kappa]^{<\omega} \times [\kappa]^{<\omega} \to \lambda$ with $\lambda < \kappa$, there exists a set $H \in D$ such that $F\restrictedto([H]^{<\omega} \times [H]^{<\omega})$ takes on at most countably many values.

<i>Proof.</i> We note that the proof of Theorem 10.22 showed that for all $n$ and all partitions $g : [\kappa]^n \to \lambda$ with $\lambda < \kappa$, there exists a homogeneous $H \in D$ such that $g\restrictedto [H]^n$ is constant.

Fix $m,n \in \omega$ and let $\max\lbrace m,n\rbrace \leq k \leq m + n$. Let $N(m,n,k)$ denote the number of functions $f : k \to 3$ such that $\vert f_{-1}(\lbrace 0,1\rbrace)\vert  = m$ and $ \vert f_{-1}(\lbrace 1,2\rbrace)\vert  = n$. Let $\lbrace f_{n,m,k,i} : i < N(n,m,k)\rbrace$ be an enumeration of all such functions. Now define $G_{n,m,k,i} : [\kappa]^k \to [\kappa]^m \times [\kappa]^n$ as follows: For each $x \in [\kappa]^k$ and $j < k$, let $x(j)$ denote the $j^\text{th}$ smallest element of $x$. Then $G_{n,m,k,i}(x) := (y,z)$, where $x(j) \in y \iff f_{n,m,k,i}(j) \leq 1$ and $x(j) \in z \iff f_{n,m,k,i}(k) \geq 1$.

We now observe that for all $(y,z) \in [\kappa]^m \times [\kappa]^n$, there exists some $k,i$ such that $(y,z) \in \ran(G_{m,n,k,i})$ - indeed, let $x := y \cup z$ (so $\max\lbrace m,n\rbrace \leq \vert x\vert  \leq m + n$), and define $f : \vert x\vert  \to 3$ such that:

$$
\begin{align*}
f(j) :=
\begin{cases}
0, &\text{if $x(j) \in y$ and $x(j) \notin z$} \\
1, &\text{if $x(j) \in y$ and $x(j) \in z$} \\
2, &\text{if $x(j) \notin y$ and $x(j) \in z$}
\end{cases}
\end{align*}
$$

Then $f = f_{m,n,\vert x\vert ,i}$ for some $i < N(m,n,\vert x\vert )$, so $(y,z) \in \ran(G_{m,n,\vert x\vert ,i})$.

For each $(m,n,k,i)$ consider the function $g \circ G_{m,n,k,i} : [\kappa]^k \to \lambda$. By the first paragraph, there exists a set $H_{m,n,k,i} \in D$ such that $(g \circ G_{m,n,k,i})\restrictedto H_{m,n,k,i}$ takes constant value $\gamma_{m,n,k,i}$. Now let $H := \bigcap H_{m,n,k,i}$, and $S$ be the set of all $\gamma_{m,n,k,i}$'s. Clearly $S$ is countable and $H \in D$. We shall show that $g([H]^{<\omega} \times [H]^{<\omega}) \subseteq S$.

Let $(y,z) \in [H]^{<\omega} \times [H]^{<\omega}$, so $(y,z) \in [H]^m \times [H]^n$ for some $m,n$. Let $x := y \cup z$, and we have that $x \in [H]^k$ for some $\max\lbrace m,n\rbrace \leq k \leq m + n$. As stated above we have that $(y,z) = G_{m,n,\vert x\vert ,i}(x)$ for some $i < N(m,n,\vert x\vert )$, so $g(y,z) = g(G_{m,n,\vert x\vert ,i}(x)) = \gamma_{m,n,\vert x\vert ,i} \in S$, as desired. 
$\blacksquare$

<i>Solution.</i> Let $g$ be as defined in the hint with a condition $(s_0,A_0)$. By <a href="#lem21.7.A">Lemma 21.7.A</a>, there exists an $A \subseteq A_0$ in $D$, and a countable $S \subseteq \lambda$ such that $g([A]^{<\omega} \times [A]^{<\omega}) \subseteq S$. Note that $A \in V[G]$ and $\vert A\vert ^{V[G]} = \kappa$ as all cardinalities are preserved under the Prikry forcing. We fix $t \in [A]^{<\omega}$, and suppose for a contradiction that $(s_0,A)$ does not force $\dot{F}([A]^{<\omega}) \subseteq S$. Then for some $(s_0 \cup s,B) \leq (s_0,A)$ and $t \in [A]^{<\omega}$, we have that $(t_0,B) \forces \dot{F}(t) \notin S$. In other words, $g(s,t) \notin S$, a contradiction. 
$\square$