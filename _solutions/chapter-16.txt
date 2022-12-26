---
title: "16)Iterated Forcing and Martin's Axiom
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-16
excerpt: ""
---

{ % include commands.html % }

    <a name="ex16.1"></a>
## Exercise 16.1.
<i>Solution.</i> By Lemma 16.3 we know that $B(P) * B(\dot{Q})$ is a complete Boolean algebra. Thus, it suffices to show that $P * \dot{Q}$ embeds densely in $B(P) * B(\dot{Q})$, by the uniqueness of Boolean completion.

For simplicity we assume $P$ is separative and $\forces_P \dot{Q}$ is separative. For each $(p,\dot{q}) \in P * \dot{Q}$, we define $e : P * \dot{Q} \to B(P) * B(\dot{Q})$ such that $e(p,\dot{q}) = [\dot{c}]$, where it is the unique $\dot{c} \in D$ such that:

$$
\begin{align*}
\Vert \dot{c} = \dot{q}\Vert  = p, \;\; \Vert \dot{c} = \dot{0}\Vert  = -p
\end{align*}
$$

This $e$ is well-defined by the completeness of $B(P)$ and fullness of $V^B$, and clearly $e$ is injective.

We shall show that $e$ is a dense embedding (i.e. it satisfies the conditions in Lemma 14.11).
<ol>[label=(\Alph*)]
<li> Since $1_{P * \dot{Q}} = (1_{P},\dot{1}_{Q})$, clearly $[e(1_{P * \dot{Q}})] = [\check{1}_{Q}]$..</li>
<li> Suppose $(p_1,\dot{q}_1) \leq (p_2,\dot{q}_2)$, so $p_1 \leq p_2$ and $p_1 \forces \dot{q}_1 \leq \dot{q}_2$, i.e. $p_1 \leq \Vert \dot{q}_1 \leq \dot{q}_2\Vert $. If $e(p_1,\dot{q}_1) = [\dot{c}_1]$ and $e(p_2,\dot{q}_2) = [\dot{c}_2]$, then:

$$
\begin{align*}
\Vert \dot{c}_1 \leq \dot{c}_2\Vert  &= \Vert \dot{c}_1 = \dot{q}_1 \wedge \dot{c}_2 = \dot{q}_2 \wedge \dot{q}_1 \leq \dot{q}_2\Vert  \\
&\eqbreak + \Vert \dot{c}_1 = \dot{0} \wedge \dot{c}_2 = \dot{q}_2 \wedge \dot{0} \leq \dot{q}_2\Vert  \\
&\eqbreak + \Vert \dot{c}_1 = \dot{q}_1 \wedge \dot{c}_2 = \dot{0} \wedge \dot{q}_1 \leq \dot{0}\Vert  \\
&\eqbreak + \Vert \dot{c}_1 = \dot{0} \wedge \dot{c}_2 = \dot{0} \wedge \dot{0} \leq \dot{0}\Vert  \\
&= p_1 \cdot p_2 \cdot \Vert \dot{q}_1 \leq \dot{q}_2\Vert  + (-p_1) \cdot p_2 \cdot \Vert \dot{0} \leq \dot{q}_2\Vert  \\
&\eqbreak + \underbrace{p_1 \cdot (-p_2)}_{=0} \cdot \Vert \dot{q}_1 \leq \dot{0}\Vert  + (-p_1) \cdot (-p_2) \cdot \Vert \dot{0} \leq \dot{0}\Vert  \\
&\geq p_1 \cdot p_2 \cdot p_1 + (-p_1) \cdot p_2 \cdot 1 + (-p_1) \cdot (-p_2) \cdot 1 \\
&= p_1 \cdot p_2 + (-p_1) \cdot p_2 + (-p_2) \\
&= 1
\end{align*}
$$

On the other hand, suppose $e(p_1,\dot{q}_1) \leq e(p_2,\dot{q}_2)$. Suppose $e(p_1,\dot{q}_1) = [\dot{c}_1]$ and $e(p_2,\dot{q}_2) = [\dot{c}_2]$, so $\Vert \dot{c}_1 \leq \dot{c}_2\Vert  = 1$. Similar to the workings above, expanding it gives:

$$
\begin{align*}
p_1 \cdot p_2 \cdot \Vert \dot{q}_1 \leq \dot{q}_2\Vert  + (-p_1) \cdot p_2 \cdot 1 + (-p_1) \cdot p_2 \cdot \Vert \dot{q_1} \leq \dot{0}\Vert  + (-p_1) \cdot (p_2) \cdot 1 = 1
\end{align*}
$$

Note that $\Vert \dot{q}_1 \leq 0\Vert  = \Vert \dot{q}_1 = 0\Vert  \geq (-p_1)$, so $(-p_1) \cdot p_2 \cdot \Vert \dot{q_1} \leq \dot{0}\Vert  = (-p_1) \cdot p_2$. Hence:

$$
\begin{align*}
p_1 \cdot p_2 \cdot \Vert \dot{q}_1 \leq \dot{q}_2\Vert  + (-p_1) = 1
\end{align*}
$$

This implies that:

$$
\begin{align*}
p_1 \cdot p_2 \cdot \Vert \dot{q}_1 \leq \dot{q}_2\Vert  \geq p_1
\end{align*}
$$

and so $\Vert \dot{q}_1 \leq \dot{q}_2\Vert  \geq p_1$ and $p_2 \geq p_1$.</li>

<li> Let $[\dot{c}] \in B(P) * B(\dot{Q})$. Now we have:<br/>
$$
\begin{align*}
\Vert \dot{c} \in B(\dot{Q})\Vert  = 1 \iff \Vert (\exists \dot{d} \in B(\dot{Q})) \, \dot{c} = \dot{d}\Vert  = 1
\end{align*}
$$

Since $V^B$ is full, there exists a $\dot{d} \in B(\dot{Q})$ such that:

$$
\begin{align*}
\Vert \dot{c} = \dot{d}\Vert  = 1
\end{align*}
$$

Since $\Vert \dot{Q} \text{ is dense in } B(\dot{Q})\Vert  = 1$, there exists a $\dot{q} \in \dot{Q}$ such that $\Vert \dot{q} \leq \dot{d}\Vert  = 1$. Then clearly we have that $e(1_P,\dot{q}) \leq [\dot{c}]$.</li>
</ol> 
$\square$

<a name="ex16.2"></a>
## Exercise 16.2.
<i>Solution.</i> Consider the map $\pi : P \times Q \to P * \check{Q}$ by:

$$
\begin{align*}
\pi(p,q) = (p,\check{q})
\end{align*}
$$

Clearly $\pi$ is injective. To see that $\pi$ is dense, let $(p,\dot{q}) \in P * \check{Q}$ be such that $\forces_P \dot{q} \in \check{Q}$. In other words, $\Vert \dot{q} \in \check{Q}\Vert  = 1$. Now since $Q \in V$, we have that:

$$
\begin{align*}
1 = \Vert \dot{q} \in \check{Q}\Vert  = \sum_{q \in Q} \Vert \dot{q} = \check{q}\Vert 
\end{align*}
$$

Thus, we have that $\Vert \dot{q} = \hat{q}\Vert  = p'$ for some $p' > 0$ and $q \in Q$. Furthermore, there must be at least one such $p'$ such that $p" := p \cdot p' \neq 0$, for otherwise we have $\Vert \dot{q} \in \check{Q}\Vert  \leq 1 - p$. Thus, we have that $p" \forces_P \Vert \dot{q} = \hat{q}\Vert $, and hence $(p",\hat{q}) \leq (p,\dot{q})$. 
$\square$

<a name="ex16.3"></a>
## Exercise 16.3.
<i>Solution.</i> <u>$\Vert D : B \text{ is a complete Boolean algebra}\Vert  = 1$:</u> Let $A$ be a name such that $\Vert A \subseteq D : B\Vert  = 1$. Let $e := \sum \lbrace d : \Vert d/I \in A\Vert  = 1\rbrace$. Since $D$ is complete, $e$ is well-defined. Following the hint, we shall show that $\Vert e/I = \sum A\Vert  = 1$. To do this, we need to show that (i) for all $d$ such that $\Vert d/I \in A\Vert  = 1$, we have that $\Vert e/I \geq d/I\Vert  = 1$, and (ii) for all $f$, if $\Vert (\forall a \in A) \, f/I \geq a\Vert  = 1$ then $\Vert f/I \geq e/I\Vert  = 1$.
<ol>
<li> Let $d \in D$ such that $\Vert d/I \in A\Vert  = 1$. By definition of $e$, we have that $e \geq d$. Thus:<br/>
$$
\begin{align*}
\Vert d \cdot (-e) \in I\Vert  &= \sum\lbrace b \in B : b \cdot d \cdot (-e) = 0\rbrace \\
&= \sum\lbrace b \in B : b \cdot 0 = 0\rbrace \\
&= 1
\end{align*}
$$

so $\Vert e/I \geq d/I\Vert  = 1$.</li>

<li> Suppose for all $a \in A$, we have that $\Vert f/I \geq a\Vert $. Then for all $d \in D$ such that $\Vert d/I \in A\Vert  = 1$, we have that $\Vert f/I \geq d/I\Vert  = 1$. In other words:<br/>
$$
\begin{align*}
\Vert f/I \geq d/I\Vert  = 1 &\iff \Vert d \cdot (-f) \in I\Vert  = 1 \\
&\iff \sum\lbrace b \in B : b \cdot d \cdot (-f) = 0\rbrace = 1
\end{align*}
$$

Since $B$ is complete, this is equivalent to $d \cdot (-f) = 0$, i.e. $f \geq d$. Therefore $f \geq e$, as desired.</li>
</ol>
Since $A$ is arbitrary, we have that $\Vert D : B \text{ is a complete Boolean algebra}\Vert  = 1$.

<u>$D$ is isomorphic to $B * (D : B)$:</u> Define $\pi : D \to B * (D : B)$ by:

$$
\begin{align*}
\pi(d) := (-b,d/I), \; \text{where } b := \sum\lbrace b' \in B : b' \leq d\rbrace
\end{align*}
$$

This map is well-defined, as such a $b$ exists as $B$ is complete, and by <a href="#ex16.3">Exercise 16.3</a> we have that $\forces_B d/I \in D : B$.

We first show that $\pi$ is one-one. Suppose $\pi(d) = \pi(e)$, so $(-b,d/I) = (-c,e/I)$, where $c := \sum\lbrace b' \in B : b' \leq e\rbrace$. In other words, we have that $b = c$ and $\Vert d/I = e/I\Vert  \geq -b$. On the other hand, we note that:

$$
\begin{align*}
\Vert d/I = e/I\Vert  = \sum\lbrace b' \in B : b' \cdot (d \symdiff e) = 0\rbrace
\end{align*}
$$

Since $b \leq d$ and $b \leq e$, $b \leq d \cdot e$ so $b \cdot (d \symdiff e) = 0$. Therefore $\Vert d/I = e/I\Vert  \geq b$, so $\Vert d/I = e/I\Vert  = 1$. Hence $1 \cdot (d \symdiff e) = 0$, i.e. $d \symdiff e = 0$. Therefore $d = e$.

We now show that $\pi$ is onto. Let $(-b,d/I) \in B * (D : B)$. Let:

$$
\begin{align*}
e := (b + d) - \sum\lbrace b' : b' \leq d - b\rbrace
\end{align*}
$$

We note that:

$$
\begin{align*}
(-b) \cdot (d - e) &= (-b) \cdot \bb{d - \bb{b + d - \sum\lbrace b' : b' \leq d - b\rbrace}} \\
&= (-b) \cdot \bb{d \cdot \bb{(-b) \cdot (-d) + \sum\lbrace b' : b' \leq d - b\rbrace}} \\
&= (-b) \cdot d \cdot \sum\lbrace b' : b' \leq d - b\rbrace
\end{align*}
$$
 
$\square$

<a name="ex16.5"></a>
## Exercise 16.5.
<i>Solution.</i>
<ol>
<li> Suppose $(p_1,\dot{q_1}) \leq (p_2,\dot{q_2})$, so $p_1 \leq p_2$ and $p_1 \forces \dot{q}_1 \leq \dot{q}_2$. The in particular $p_1 \leq p_2$, so $h(p_1,\dot{q}_1) = h(p_2,\dot{q}_2)$..</li>
<li> Let $(p,\dot{q}) \in P * Q$, and let $p' \leq h(p,\dot{q}) = p$. Then of course $p' \forces \dot{q} \leq \dot{q}$, so $(p',\dot{q}) \leq (p,\dot{q})$, and $h(p'\dot{q})$.</li>
</ol> 
$\square$

<a name="ex16.6"></a>
## Exercise 16.6.
<i>Solution.</i> We first note that by Theorem 16.4, $P * \dot{Q}$ satisfies the c.c.c., so all cardinals are preserved in any generic extension. Thus, when mentioning a cardinal $\kappa$ we need not distinguish between $\kappa^V$ and $\kappa^{V[G]}$.

Let $\lbrace (p_\alpha,\dot{q}_\alpha) : \alpha < \omega_1\rbrace$ be an uncountable set of conditions of $P * \dot{Q}$. Let $\dot{Z} \in V^P$ be the canonical name for the set $\lbrace \alpha : p_\alpha \in G\rbrace$, where $G$ is a generic filter on $P$ (i.e. $\Vert \alpha \in \dot{Z}\Vert  = p_\alpha$ for all $\alpha < \omega_1$). We also let $\dot{F} \in V^P$ be the name of a function such that $\Vert (\check{\alpha},\dot{q}_\alpha) \in \dot{F}\Vert  = p_\alpha$ for all $\alpha < \omega_1$.

Since $\Vert \check{\alpha} \in \dot{Z}\Vert  = p_\alpha > 0$ for all $\alpha$, we do have that $\Vert \dot{Z} \subseteq \check{\beta}\Vert  \neq 1$ for all $\beta < \omega_1$. Thus, there exists a generic filter $G$ such that $V[G] \models
\vert Z_G\vert  = \aleph_1$. We fix this generic filter $G$. Now $V[G] \models \dot{Q}$ has property (K), so there exists some $W \subseteq Z$ such that in $V[G]$, $W$ is uncountable and all elements in $\lbrace F_G(\alpha) : \alpha \in W\rbrace$ are pairwise compatible. We fix some $p \in G$ such that $p \forces$ $\dot{W} \subseteq \dot{Z}$ and all elements in $\lbrace \dot{F}(\alpha) : \alpha \in \dot{W}\rbrace$ are pairwise compatible.

From here onwards we work in the ground $V$. Let:

$$
\begin{align*}
W' := \lbrace \alpha < \omega_1 : (\exists p' \in P)(p ' \leq p \wedge p' \leq p_\alpha \wedge p' \forces \alpha \in \dot{W})\rbrace
\end{align*}
$$

Note that indeed $W' \in V$. We see that $W'$ is uncountable - indeed, in $V[G]$ if $\alpha \in W_G$, we have that $p' \forces \check{\alpha} \in \dot{W}$ for some $p' \in G$, and since $G$ is a filter and $p,p_\alpha \in G$, we may choose $p'$ such that $p' \leq p$, $p' \leq p_\alpha$. Thus $V[G] \models W'$ is uncountable, and since all cardinalities are preserved, $W'$ is uncountable in $V$. Thus, for each $\alpha \in W'$ we fix $p_\alpha'$ such that $p_\alpha' \leq p$, $p_\alpha' \leq p_\alpha$ and $p_\alpha' \forces \alpha \in \dot{W}$. Since $P$ has property (K), we let $W" \subseteq W'$ be uncountable such that all elements in $W"$ are pairwise compatible.

We shall show that $\lbrace (p_\alpha,\dot{q}_\alpha) : \alpha \in W"\rbrace$ have elements which are pairwise compatible. Fix $\alpha,\beta \in W"$. Since $p_\alpha'$ and $p_\beta'$ are compatible, we let $p' \leq p_\alpha'$ and $p' \leq p_\beta'$. Then $p' \forces (\check{\alpha} \in \dot{W} \wedge \check{\beta} \in \dot{W})$, and since $p' \leq p$ we have that $p' \forces$ all elements in $\lbrace \dot{F}(\alpha) : \alpha \in \dot{W}\rbrace$ are pairwise compatible. Since $V^P$ is full, there exists some $\dot{q} \in \dot{Q}$ such that $p' \forces (\dot{q} \leq \dot{q}_\alpha \wedge \dot{q} \leq \dot{q}_\beta)$. Then $(p',\dot{q}) \leq (p_\alpha,q_\alpha)$ and $(p',\dot{q}) \leq (p_\beta,q_\beta)$, as desired. 
$\square$

<a name="ex16.7"></a>
## Exercise 16.7.
<i>Solution.</i> We use <a href="https://clementyung.github.io/jech-solutions/chapter-15#ex15.5">Exercise 15.5</a>. By Theorem 16.2, every $(P * \dot{Q})$-generic extension is of the form $V[G][H]$, where $G$ is $V$-generic on $P$ and $H$ is a $V[G]$-generic filter on $\dot{Q}_G$. Let $f : \kappa \to V$ be a function in $V[G][H]$. Working in $V[G]$, since $\dot{Q}_G$ is $\kappa$-distributive we have that $f \in V[G]$. But working in $V$, since $P$ is $\kappa$-distributive we also have $f \in V$. Thus $P * \dot{Q}$ is $\kappa$-distributive. 
$\square$

<a name="ex16.8"></a>
## Exercise 16.8.
<i>Solution.</i> Let $P_\alpha$ be the finite support iteration uniquely determined by a sequence of forcing notions $\c{\dot{Q}_\beta : \beta < \alpha}$.

Let $C$ be the direct limit of the algebras $B_\beta$, $\beta < \alpha$. Similar to the proof of <a name="#15#lem15.9.A">Lemma 15.9.A</a>, it suffices to show that $C$ embeds into $B_\alpha$. Let $U \in C$, so we have that $\forces_\beta U(\beta)$ is a regular cut of $\dot{Q}_\beta$. Let $p \notin U$, so we have that $\forces_\beta p(\beta) \notin U(\beta)$ for some $\beta < \alpha$. Since $\forces_\beta U(\beta)$ is regular, we have that:

$$
\begin{align*}
\forces_\beta (\exists q \leq p(\beta)) \, U_q \cap U(\beta) = \emptyset
\end{align*}
$$

Since $V^{B_\beta}$ is full, there exists some $\dot{q} \in \dot{Q}_\beta$ such that:

$$
\begin{align*}
\forces_\beta U_{\dot{q}} \cap U(\beta) = \emptyset
\end{align*}
$$

Let $q' \in P_\alpha$ be such that $\forces_\beta q'(\beta) = \dot{q}$, and $\forces_\gamma q'(\gamma) = 1$ for all $\gamma \neq \beta$. Let $U_{q'} \in B$ be the regular cut of $P_\alpha$ generated by the element $q'$. It's easy to see that $\forces_\beta U_{q'}(\beta) = U_{\dot{q}}$, and $\forces_\gamma U_{q'}(\gamma) = \dot{Q}_\gamma$ for all $\gamma \neq \beta$. Therefore, $U_{q'} \cap U = \emptyset$, so $U$ is regular, as desired. 
$\square$

<a name="ex16.9"></a>
## Exercise 16.9.
<i>Solution.</i> Since a finite support iteration is in particular an iteration (Definition 16.29), this is a special case of <a href="#ex16.17">Exercise 16.17</a>. 
$\square$

<a name="ex16.10"></a>
## Exercise 16.10.
<i>Solution.</i> Obviously there are $2^{\aleph_0}$ many such $g$'s. It's also easy to see that $D_g$ is dense for all $g$. If $G$ is a $\D$-generic filter, then $g := \bigcup G$ is a function $g : \omega \to \lbrace 0,1\rbrace$ (as $G$ is a filter). Since $G$ is $\D$-generic, we have that $p \in G \cap D_g$ for some $p$. Then $p \subseteq g$ (as $p \in G$ and $g = \bigcup G$) and $p \not\subseteq g$ (as $p \in D_g$), a contradiction. 
$\square$

<a name="ex16.11"></a>
## Exercise 16.11.
<i>Solution.</i> Let $D_n' := \lbrace p \in P : n \in \dom(p)\rbrace$, and clearly $D_n'$ is dense for all $n$. $D_\alpha$ is also clearly dense for all $\alpha \in \ran(p)$. Let $\D := \lbrace D_\alpha : \alpha < \omega_1\rbrace \cup \lbrace D_n' : n < \omega\rbrace$. Of course $\D$ has size $\aleph_1$. If $G$ is a $\D$-generic filter, then $g := \bigcup G$ is a function $g : \omega \to \omega_1$ (as $G \cap D_n' \neq \emptyset$ so $n \in \dom(g)$ for all $n < \omega$). Furthermore, since $G \cap D_\alpha \neq \emptyset$ for all $\alpha < \omega_1$, $\alpha \in \ran(g)$ for all $\alpha < \omega_1$, i.e. $g$ is onto. This implies that $\aleph_1 \leq \aleph_0$, a contradiction. 
$\square$

<a name="ex16.12"></a>
## Exercise 16.12.
<i>Solution.</i> Since complete Boolean algebras are partial orders, $\implies$ is immediate. Conversely, suppose $\MA_\kappa$ holds for complete Boolean algebras. Let $(P,<)$ be a partially ordered set satisfying the c.c.c. We note that this implies that $B(P)$ also satisfies the c.c.c. - if $A \subseteq B(P)$ is an antichain, then for each $a \in A$, let $p_a \in P$ be such that $p_a \leq a$ in $B(P)$ (possible as $P$ is dense in $B(P)$). Then $\lbrace p_a : a \in A\rbrace$ is an antichain in $P$ (and $a \neq a' \implies p_a \neq p_{a'}$), so it must be countable. Therefore $A$ is countable.

Let $\D$ be a collection of at most $\kappa$ dense subsets of $P$. Note that for each $D \in \D$, $D$ remains dense in $B(P)$ as $P$ is dense in $B(P)$. By $\MA_\kappa$, there exists a $\D$-generic filter $G$ on $B(P)$ (by treating $B(P)$ as a partially ordered set) $G$. Then $G \cap P$ is a $\D$-generic filter on $P$. 
$\square$

<a name="ex16.13"></a>
## Exercise 16.13.
<i>Solution.</i> $\implies$ is of course immediate. The proof of the converse follows very closely to that of Lemma 16.12. Suppose $\MA_\kappa$ holds for partial orders of cardinality $\leq\kappa$. Let $P$ be a c.c.c. partially ordered set, and let $\D$ be a family of at most $\kappa$ dense subsets of $P$. Let $W_D$ be the maximal incompatible subset of $D$, which is countable as $P$ satisfies the c.c.c.

<b>Claim.</b>. There exists some $Q \subseteq P$ such that:
<ol>
<li> $\vert Q\vert  \leq \kappa$..</li>
<li> For all $D \in \D$, $W_D \subseteq Q$ and is a in fact a maximal antichain in $Q$.</li>

<li> For all $p,q \in Q$ compatible, there exists an $r \in Q$ such that $r \leq p$ and $r \leq q$..</li></ol>

<i>Proof.</i> Let $W := \bigcup_{D \in \D} W_D$. Since $\vert \D\vert  \leq \kappa$ and $\vert D\vert  \leq \aleph_0$ for all $D \in \D$, we have that $\vert W\vert  \leq \kappa$. For $n < \omega$, we define $Q_n$ inductively as follows: Let $Q_0 := W \cup \lbrace 1\rbrace$. Assume $Q_n$ is constructed and $\vert Q_n\vert   \leq \kappa$. Let $f_n$ be a choice function on $Q_n \times Q_n$ such that for all $p,q$, if $p$ and $q$ are compatible then $f_n(p,q) \leq p$ and $f_n(p,q) \leq q$ (otherwise, $f_n(p,q) = 1$). Let $Q_{n+1} := Q_n \cup \ran(f_n)$. Since $\vert Q_n\vert  \leq \kappa$, $\vert Q_{n+1}\vert  \leq \kappa$.

Now let $Q := \bigcup_{n\in\omega} Q_n$. Clearly $\kappa$ is regular, $\vert Q\vert  \leq \kappa$. Clearly $Q$ satisfies (ii). Finally, for (iii), if $p,q \in Q$ are compatible, then $p,q \in Q_n$ for some $n$, and so $r := f_n(p,q) \in Q_{n+1}$. 
$\blacksquare$

Since $E_D := \lbrace q \in Q : q \leq w \text{ for some }w \in W_D\rbrace$ is dense for all $D \in \D$, each $W_D$ is a maximal antichain in $Q$. Then $\vert Q\vert  \leq \kappa$ and $Q$ satisfies c.c.c., so by $\MA_\kappa$ there exists a filter $G$ intersecting all of the $E_D$'s. Then $w \in G$ for some $w \in W_D \subseteq D$ by upward-closure, so the filter in $P$ generated by $G$ is $\D$-generic. Hence $\MA$ holds. 
$\square$

<a name="ex16.14"></a>
## Exercise 16.14.
<i>Solution.</i> We note that $P^V = P^{V[G]}$ (i.e. the Cohen forcing notion in $V$ and in $V[G]$ are the same), as all conditions in $P$ are finite, which are absolute. Thus, $P$ remains c.c.c. in $V[H]$. $P_T \times P$ is therefore c.c.c. by Corollary 16.6 ($P_T$ is c.c.c. by Corollary 15.29). Since $P_T \times P$ is clearly isomorphic to $P \times P_T$, $P \times P_T$ is also c.c.c., so by Lemma 16.5 $P_T$ is c.c.c. in $V[G]$.

By the absoluteness in the definition of a normal $\omega_1$-tree (and the fact that $\omega_1$ is preserved due to c.c.c.), we have that $T$ remains a normal $\omega_1$-tree in $V[G]$. By definition of $P_T$, we have that antichains in $T$ are at most countable iff $P_T$ satisfies the c.c.c., which holds by the first paragraph. Therefore $T$ is a normal Suslin tree in $V[G]$. Note that this also implies that no uncountable chains are added, as otherwise by <a href="https://clementyung.github.io/jech-solutions/chapter-9#ex9.7">Exercise 9.7</a> it produces an uncountable antichain in $T$. 
$\square$

<b>Remark.</b>. It follows that the existence of a Suslin tree is consistent with $2^{\aleph_0} > \aleph_1$.

<a name="ex16.15"></a>
## Exercise 16.15.
<i>Solution.</i> Let $P$ be the L\'{e}vy Collapse of $\omega_2$ onto $\omega_1$, as in (15.18). Let $G$ be $P$-generic, and let $f := \bigcup G$ be the generic mapping of $\omega_1$ onto $\omega_2$. Note that $\omega_1^{V[f]} = \omega_1$, and $\omega_2$ is collapsed. Now $\vert f\vert  = \aleph_1$, so by considering its transitive closure and the canonical ordering $\Gamma$, there exists some $X \subseteq \omega_1$ such that $V[f] = V[X]$ (see <a href="https://clementyung.github.io/jech-solutions/chapter-13#ex13.27">Exercise 13.27</a>). Using almost disjoint forcing, we may obtain $A \subseteq \omega$ such that $V[A] = V[X][A]$ (see Theorem 16.20, its proof and the remark afterwards). Since the almost disjoint forcing notion is c.c.c., all cardinals and cofinalities are preserved, so $\omega_1^{V[A]} = \omega_1$ and $\omega_2^{V[A]} = \omega_2^{V[X][A]} = \omega_2^{V[X]}$ is collapsed, as desired. 
$\square$

<a name="ex16.16"></a>
## Exercise 16.16.
<i>Solution.</i> Let $P$ be the forcing notion consisting of conditions in the hint. Let $\D = \lbrace D_n : n < \omega\rbrace \cup \lbrace E_\alpha : \alpha < \kappa\rbrace$. By $\MA_\kappa$, let $G$ be $\D$-generic, and let:

$$
\begin{align*}
X := \bigcup_{(s,F) \in G} s
\end{align*}
$$

We shall show that $X \subseteq \omega$ is the set we want. Since $G$ intersects all of $D_n$, $\lbrace \vert s\vert  : (s,F) \in G\rbrace$ is an unbounded subset of $\omega$ and therefore $X$ is infinite. Now fix $\alpha < \kappa$. Since $G$ intersects $E_\alpha$, there exists some $(s,F) \in G$ such that $\alpha \in F$. Then for all $(s',F') \in G$ such that $(s',F') \leq (s,F)$, $s' - s \in X_\alpha$ so we have that $X - X_\alpha \subseteq s$, which is finite. 
$\square$

<a name="ex16.17"></a>
## Exercise 16.17.
<i>Solution.</i> We may assume WLOG that  Let $\gamma < \kappa$ and let $\c{p_\alpha : \alpha < \gamma}$ be a decreasing sequence of conditions in $P_\alpha$. 
$\square$

<a name="ex16.19"></a>
## Exercise 16.19.
<i>Solution.</i> We first note that we may assume WLOG that $\kappa$ is regular - this follows from the observation that (i) if $I$ is $\kappa$-complete and $\kappa$ is singular, then $I$ is $\kappa^+$-complete and (ii) if $P$ is $<\!\kappa$-closed and $\kappa$ is singular, then $P$ is $\kappa$-closed, i.e. $<\!\kappa^+$-closed. This assumption implies that $\kappa < \vert \alpha\vert $, and if $\alpha$ is limit then $\cf(\alpha) > \kappa$. Thus, for all $p \in P_\alpha$ we have that $s(p)$ is a bounded subset of $\alpha$.

Now let $\gamma < \kappa$, and let $\c{p_\xi : \xi < \gamma}$ be a decreasing sequence of conditions in $P$. Let $S := \bigcup_{\xi < \gamma} s(p_\xi)$. Since $I$ is $\kappa$-complete and $\gamma < \kappa$, we have that $S \in I$. Now define inductively conditions $q_\beta := q\restrictedto\beta$, for $\beta \leq \alpha$, as follows:
<ol>
<li> If $\beta = \delta + 1$, then let $q_\beta$ be such that $q_\beta\restrictedto\delta = \delta$, and in addition the following: Since $\forces_\delta \c{p_\alpha(\delta) : \alpha < \gamma}$ is a decreasing sequence in $\dot{Q}_\delta$ (note that if $\delta \notin S$, then $\forces_\delta p_\alpha(\delta) = 1$ for all $\alpha < \gamma$), and $\forces_\delta \dot{Q}_\delta$ is $<\!\kappa$-closed, we have that $\forces_\delta (\forall \alpha < \gamma) , \dot{r}_\delta \leq p_\alpha(\delta)$  for some $\dot{r}_\delta \in \dot{Q}_\delta$. Then let $q_\beta$ such that $\forces_\delta q_\beta(\delta) = \dot{r}_\delta$.</li>

<li> If $\beta$ is a limit ordinal, then we simply let $q_\beta := \bigcup_{\delta<\beta} q_\delta$. To see that this is well-defined (i.e. $s(q_\beta) \in I$), we consider two cases. If $S \cap \beta$ is bounded in $\beta$, then $s(q_\beta) = s(q_\delta) \in I$ for some $\delta < \beta$. Otherwise, we must have $\cf(\beta) < \kappa$, so let $\c{\delta_\xi : \xi < \cf(\beta)}$ be a sequence in $S$ cofinal in $\beta$. Then $s(q_\beta) = \bigcup_{\xi<\cf(\beta)} s(q_{\delta_\xi})$, and by $\kappa$-completeness of $I$ we have that $s(q_\beta) \in I$..</li></ol> 
$\square$

<a name="ex16.20"></a>
## Exercise 16.20.
<i>Solution.</i> Following the hint, it suffices to show that:
<ol>
<li> For $\beta < \kappa$, $P_\beta$ satisfies the $\kappa$-chain condition for all $\beta < \kappa$.</li>

<li> $P_\kappa$ is a direct limit..</li>
<li> For a stationary set of $\beta < \kappa$, $P_\beta$ is a direct limit.</li>
</ol>
For (i), let $A \subseteq P_\beta$ be an antichain. Let $D \subseteq P_\beta$ be a dense subset of size $<\kappa$. Then for each $p \in A$, there exists a $p' \in D$ such that $p' \leq p$. Furthermore, if $p \neq q$ in $A$ then $p' \neq q'$, for otherwise $p$ and $q$ are comparable, contradicting that $A$ is an antichain. Therefore, the map $p \mapsto p'$ is a one-to-one map on the set $A$ into $D$, which is of size $<\kappa$. Hence $A$ is of size $<\kappa$.

For (ii), this follows from that $\kappa \geq \aleph_2$ is a regular cardinal, and $P$ is a countable support iteration.

For (iii), we first note that under the countable support iteration, if $\cf(\beta) > \omega$ then $P_\beta$ is a direct limit. Since $E_{\aleph_1}^\kappa$ is a stationary subset of $\kappa$, the result follows. 
$\square$