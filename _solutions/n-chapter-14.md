---
title: "14) Forcing"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-14
excerpt: ""
---

{% include commands.html %}

<a name="ex14.1"></a>
## Exercise 14.1.
<i>Solution.</i> We shall show that the $D$ in the hint is dense (for fixed $p,q \in P$). This gives the conclusion, as if $G$ is generic then $G \cap D \neq \emptyset$, so we have $r \in G \cap D$. Since all elements in $G$ are compatible, neither $r$ is incompatible with $p$ now $r$ is incompatible with $q$ is possible. It follows that $r \leq p$ and $r \leq q$, as desired.

Let $s \in P$, and we consider two cases. If $s$ is incompatible with $p$ or $q$, then by definition of $D$, $s \in D$. Otherwise, $s$ is compatible with both $p$ and $q$, so there exists $t \in P$ such that $t \leq s,p,q$. Then, in particular, $t \leq p,q$ so $t \in D$, and $t \leq s$. 
$\square$

<a name="ex14.2"></a>
## Exercise 14.2.
<i>Solution.</i> <u>$\implies$:</u> Fix $p \in G$. Let $D \in M$ be dense below $p$. Define:

$$
\begin{align*}
D' := \lbrace q \in P : q \perp p \vee q \in D\rbrace
\end{align*}
$$

We see that $D'$ is dense in $P$. Indeed, for any $r \in P$, if $r \perp p$ then $r \in D'$. Otherwise, there exists $s \in P$ such that $s \leq p,r$. Since $D$ is dense below $p$, there exists $t \in D'$ such that $t \leq s \leq r$, as desired.

Thus, we have that $G \cap D' \neq \emptyset$. Let $q \in G \cap D'$. But since $p \in G$, we must have $q \not\perp p$, so $q \in D$. Hence $q \in G \cap D$.

<u>$\impliedby$:</u> Fix $D \in M$ dense in $P$, and let $p \in G$ be arbitrary. Consider:

$$
\begin{align*}
D' := \lbrace q \in D : q \leq p\rbrace
\end{align*}
$$

Clearly $D'$ is dense below $p$, so by hypothesis $\emptyset \neq G \cap D' \subseteq G \cap D$. 
$\square$

<a name="ex14.3"></a>
## Exercise 14.3.
<i>Solution.</i> $\implies$ is immediate. For $\impliedby$, let $D$ be a (not necessarily open) dense set in $P$. Define:

$$
\begin{align*}
D' := \lbrace q \in P : (\exists p \in D) \, q \leq p\rbrace = \bigcup_{p \in D} O(p)
\end{align*}
$$

where $O(p) := \lbrace q \in P : q \leq p\rbrace$ is the basic open set corresponding to $p$. Then clearly $D'$ is dense open, so by hypothesis $G \cap D \neq \emptyset$, and say it contains the condition $r$. By definition of $D'$, there exists an $s \in D$ such that $r \leq s$. Then $s \in G$ as $G$ is upward closed, so $G \cap D \neq \emptyset$. 
$\square$

<a name="ex14.4"></a>
## Exercise 14.4.
<i>Solution.</i> $\impliedby$ is immediate. For $\implies$, let:

$$
\begin{align*}
D' := \lbrace q \in P :  (\exists p \in D) \, q \leq p\rbrace
\end{align*}
$$

Then $D'$ is dense - indeed, let $r \in P$, and since $P$ is predense, $r$ is compatible with some $p \in P$, i.e. there exists $q \in P$ such that $q \leq r$ and $q \leq p$. Then $q \in D'$, so $D'$ is dense. By genericity of $G$, $G \cap D' \neq \emptyset$. Let $q \in G \cap D'$, so $q \leq p$ for some $p \in D$. Then $p \in G$ by upward closure, so $G \cap D \neq \emptyset$. 
$\square$

<a name="ex14.5"></a>
## Exercise 14.5.
<i>Solution.</i> Since every maximal antichain in $P$ is predense in $P$, this follows from <a href="#ex14.4">Exercise 14.4</a>. 
$\square$

<a name="ex14.6"></a>
## Exercise 14.6.
<i>Solution.</i> As in the hint, let $D := \lbrace p \in P : p \notin F\rbrace$. Then for every $p \in P$, consider two cases: If $p \notin F$, then $p \in D$ and we're done. Otherwise, let $q,r \leq p$ be incompatible. Since all elements in $F$ are comparable, we have $q \notin F$ or $r \notin F$. then $q \in D$ or $r \in D$, so $D$ is indeed dense.

If $G$ is a filter and $G \in M$, then $D \in M$ and $G \cap D = \emptyset$. Thus $G$ can't be generic. 
$\square$

<a name="ex14.7"></a>
## Exercise 14.7.
<i>Solution.</i> By Theorem 14.7(i)(c), it suffices to show that no $q \leq p$ forces $\neg\varphi$. Suppose such a $q$ exists. By denseness we let $r \leq q$ such that $r \forces \varphi$. By Theorem 14.7(i)(a), $r \forces \neg\varphi$ as $r \leq q$, contradicting Theorem 14.7(i)(b). 
$\square$

<a name="ex14.8"></a>
## Exercise 14.8.
<i>Solution.</i> $\implies$ follows immediately from the Forcing Theorem 14.6. Conversely, suppose $p \not\forces \sigma$. Then there exists $q \leq p$ such that $q \forces \neg\sigma$ (otherwise by <a href="#ex14.7">Exercise 14.7</a> we have $p \forces \sigma$). Let $G \subseteq P$ be generic such that $q \in G$. Then $p \in G$ by upward closure, and since $q \forces \neg\sigma$ by the Forcing Theorem we have $M[G] \models \neg\sigma$ (so $M[G] \not\models \sigma$). 
$\square$

<a name="ex14.9"></a>
## Exercise 14.9.
<i>Solution.</i> We use the notations/definitions in the proof of Lemma 14.11. Fix a poset $(P,<)$ and let $(Q,<')$ be a separative quotient of $(P,<)$, along with an onto embedding $h : P \to Q$. It suffices to show that $(Q,<')$ is isomorphic to $({P/\!\sim},\prec)$, where $\sim$ is defined as in Lemma 14.11.

For $x \in P$, define $g : {P/\!\sim} \to Q$ by:

$$
\begin{align*}
g([x]) = h(x)
\end{align*}
$$

We show that this is well-defined. Suppose $x \sim y$ for some $x,y \in P$. Then for all $z \in P$, we have $z$ is compatible with $x$ iff $z$ is compatible with $y$. Thus $h(z)$ is compatible with $h(x)$ iff $h(z)$ is compatible with $h(y)$. Since $(Q,<')$ is separative and $h$ is into, we have that $h(x) = h(y)$. By a reversed reasoning, we may also conclude that $g$ is one-to-one.

We now show that $g$ is order-preserving. Suppose $[x] \preceq [y]$, so $(\forall z \leq x)$[$z$ and $y$ are compatible]. This implies that, in $(Q,<')$, for all $z \leq h(x)$ we have that $z$ and $h(y)$ are compatible. By the hint again, this implies that $h(x) \leq h(y)$, as desired. 
$\square$

<a name="ex14.10"></a>
## Exercise 14.10.
<a name="lem14.10.A"></a>
<b>Lemma 14.10.A.</b> Let $X \subseteq B^+$ and define:

$$
\begin{align*}
D := \lbrace u \in B^+ : (\forall x \in X) \, u \leq x\rbrace \cup \lbrace u \in B^+ : (\exists x \in X) \, u \leq -x\rbrace
\end{align*}
$$

Then $D$ is an open dense subset of $B^+$.

<i>Proof.</i> Openness of $D$ is clear. Let $u \in B^+$, and we consider two cases. If $u \leq x$ for all $x \in X$, then immediately we have $u \in D$. Otherwise, $u \not\leq x$ implies that $u \cdot (-x) \neq 0$ for some $x \in X$. Then $u \cdot (-x) \leq -x \in D$. 
$\blacksquare$

<i>Solution.</i> Note that $0 \notin G$ so $G \subseteq B^+$. It's easy to see that $G$ is a filter on $B$ iff $G$ is a filter on $B^+$.

<u>$\implies:$</u> Note that $G \subseteq B^+$ remains an ultrafilter. Let $D \subseteq B^+$ be open dense. Suppose $G \cap D = \emptyset$. Then $X := \lbrace -u : u \in D\rbrace \subseteq G$, and since $G$ is generic in $B$, $\prod X \in G$. If $\prod X = 0$, then we have a contradiction immediately. Otherwise, $\prod X \in B^+$, so by denseness of $D$ we have that $v \leq \prod X$ for some $v \in D$. Then $v \leq -v$ and $v \neq 0$, a contradiction as well.

<u>$\impliedby:$</u> We first show that $G$ is an ultrafilter. Let $u \in B$ and let:

$$
\begin{align*}
D := \lbrace v \in B^+ : v \leq u \vee v \cdot u = 0\rbrace
\end{align*}
$$

By <a href="#lem14.10.A">Lemma 14.10.A</a>, $D$ is open dense. Since $G$ is generic in $B^+$, we have $v \in G \cap D$ for some $v \in B^+$. If $v \leq u$ then $u \in G$ by upward closure. Otherwise, $v \cdot u = 0$ so $v \leq -u$, hence $-u \in G$.

Now let $X \subseteq G$. Consider:

$$
\begin{align*}
D := \lbrace u \in B^+ : (\forall x \in X) \, u \leq x\rbrace \cup \lbrace u \in B^+ : (\exists x \in X) \, u \leq -x\rbrace
\end{align*}
$$

Again by <a href="#lem14.10.A">Lemma 14.10.A</a>, $D$ is open dense in $B^+$. Since $G$ is generic in $B^+$, we have that $v \in G \cap D$ for some $v \in B^+$. By compatibility of elements in $G$, we can't have $v \leq -x$ for any $x \in X \subseteq$. Thus, we must have $v \leq x$ for all $x \in X$. By upward closure (and completeness of $B$), $\prod X \in G$. 
$\square$

<a name="ex14.11"></a>
## Exercise 14.11.
<i>Solution.</i> It's easy to see that $W$ is a partition of $B$ iff $W$ is a maximal antichain of $B^+$. By <a href="#ex14.10">Exercise 14.10</a>, $G$ is a generic filter of $B^+$ iff $G$ is a generic ultrafilter of $B$. Finally, by <a href="#ex14.5">Exercise 14.5</a> $G$ is a generic filter of $B^+$ iff $G \cap W \neq \emptyset$ for all maximal antichains $W \subseteq B^+$. The uniqueness of $u \in G \cap W$ comes from that $W$ is an antichain and $G$ is a filter. 
$\square$

<a name="ex14.12"></a>
## Exercise 14.12.
<i>Solution.</i> Again we use $\to$ in place of $\Rightarrow$. We use <a href="https://clementyung.github.io/jech-solutions/chapter-7#ex7.27">Exercise 7.27</a> and <a href="#ex14.12(i)">Exercise 14.12(i)</a>.

$$
\begin{align*}
\Vert (\forall y \in x) \, \varphi(y)\Vert  &= -\Vert (\exists y \in x) \, \neg\varphi(y)\Vert  \\
&= -\bb{\sum_{y \in \dom{x}} x(y) \cdot \Vert \neg\varphi(y)\Vert } \\
&= \prod_{y \in \dom(x)} -(x(y) \cdot \Vert \neg\varphi(y)\Vert ) \\
&= \prod_{y \in \dom(x)} (-x(y) + (-\Vert \neg\varphi(y)\Vert )) \\
&= \prod_{y \in \dom(x)} (-x(y) + \Vert \varphi(y)\Vert ) \\
&= \prod_{y \in \dom(x)} (x(y) \to \Vert \varphi(y)\Vert )
\end{align*}
$$
 
$\square$

<a name="ex14.13"></a>
## Exercise 14.13.
<i>Solution.</i> See the solution of <a href="#ex14.13(i)">Exercise 14.13(i)</a>. 
$\square$

<a name="ex14.14"></a>
## Exercise 14.14.
<a name="ex14.14(i)"></a>
### Exercise 14.14(i).
<i>Solution.</i> Recall that the statement "$G$ is an ultrafilter on $B$" is equivalent to the conjunction of the following:
<ol>
<li> $1 \in G$, $0 \notin G$Lib</li>
<li> $(\forall u \in G)(\forall v \in B)(u \leq v \to v \in G)$.</li>

<li> $(\forall u \in G)(\forall v \in G) \, u \cdot v \in G$Lib</li>
<li> $(\forall u \in B)(u \in G \vee -u \in G)$.</li>
</ol>
Thus, it suffices to show that all the statements above have Boolean values $1$. WLOG we may assume that $B$ is a complete Boolean algebra of sets, so by Lemma 14.21 we have that for $u,v \in B$, $u \leq v$ iff $\Vert \check{u} \leq \check{v}\Vert  = 1$. This implies that for any $u \in B$:

$$
\begin{align*}
\Vert \check{u} \in \dot{G}\Vert  = \sum_{v \in B} \Vert \check{u} = \check{v}\Vert  \cdot \dot{G}(\check{v}) = \dot{G}(\check{u}) = u
\end{align*}
$$

<ol>
<li> We have $\Vert \check{1} \in \dot{G}\Vert  = \dot{G}(\check{1}) = 1$ and $\Vert \check{0} \in \dot{G}\Vert  = \dot{G}(\check{0}) = 0$Lib</li>
<li> Using <a href="#ex14.12">Exercise 14.12</a>:

$$
\begin{align*}
&\eqbreak \Vert (\forall u \in \dot{G})(\forall v \in \check{B})(u \leq v \to v \in \dot{G})\Vert  \\
&= \prod_{u \in \dom{\dot{G}}} \bb{\dot{G}(u) \to \Vert (\forall v \in \check{B})(u \leq v \to v \in \dot{G})\Vert } \\
&= \prod_{u \in B} \bb{(-u) + \Vert (\forall v \in \check{B})(\check{u} \leq v \to v \in \dot{G})\Vert }
\end{align*}
$$

Fix a $u \in B$. Then:

$$
\begin{align*}
\Vert (\forall v \in \check{B})(\check{u} \leq v \to v \in \dot{G})\Vert  &= \prod_{v \in \dom{\check{B}}} (\check{B}(v) \to \Vert \check{u} \leq v \to v \in \dot{G}\Vert ) \\
&= \prod_{v \in B} ((-1) + \Vert \check{u} \leq \check{v} \to \check{v} \in \dot{G}\Vert ) \\
&= \prod_{v \in B} \Vert \check{u} \leq \check{v} \to \check{v} \in \dot{G}\Vert  \\
&= \prod_{v \in B} (-\Vert \check{u} \leq \check{v}\Vert ) + \Vert \check{v} \in \dot{G}\Vert )
\end{align*}
$$

Now if $v > u$, then $-\Vert \check{u} \leq \check{v}\Vert  = 1$, so it suffices to consider products of Boolean values $v \geq u$. Thus:

$$
\begin{align*}
\prod_{v \in B} (-\Vert \check{u} \leq \check{v}\Vert ) + \Vert \check{v} \in \dot{G}\Vert ) &= \prod_{\substack{v \in B \\ u \leq v}} \dot{G}(\check{v}) \\
&= \prod_{\substack{v \in B \\ u \leq v}} v \\
&= u
\end{align*}
$$

Therefore:

$$
\begin{align*}
\prod_{u \in B} \bb{(-u) + \Vert (\forall v \in \check{B})(\check{u} \leq v \to v \in \dot{G})\Vert } = \prod_{u \in B} ((-u) + u)) = 1
\end{align*}
$$
</li>

<li> We have:<br/>
$$
\begin{align*}
\Vert (\forall u \in \dot{G})(\forall v \in \dot{G}) \, u \cdot v \in \dot{G}\Vert  = \prod_{u \in B} \bb{(-u) + \Vert (\forall v \in \dot{G}) \, \check{u} \cdot v \in \dot{G}\Vert }
\end{align*}
$$

So we fix $u \in B$. Then:

$$
\begin{align*}
\Vert (\forall v \in \dot{G}) \, \check{u} \cdot v \in \dot{G}\Vert  = \prod_{v \in B} \bb{(-v) + \Vert \check{u} \cdot \check{v} \in \dot{G}\Vert }
\end{align*}
$$

Since $B$ is an algebra of sets, $\check{u} \cdot \check{v} = (u \cdot v)\check{}$. Thus:

$$
\begin{align*}
\prod_{v \in B} \bb{(-v) + \Vert \check{u} \cdot \check{v} \in \dot{G}\Vert } &= \prod_{v \in B} \bb{(-v) + u \cdot v} \\
&\geq \prod_{v \in B} \bb{u \cdot (-v) + u \cdot v} \\
&= \prod_{v \in B} u \\
&= u
\end{align*}
$$

Therefore:

$$
\begin{align*}
\prod_{u \in B} \bb{(-u) + \Vert (\forall v \in \dot{G}) \, \check{u} \cdot v \in \dot{G}\Vert } \geq \prod_{u \in B} ((-u) + u) = 1
\end{align*}
$$
</li>

<li> We have:<br/>
$$
\begin{align*}
\Vert (\forall u \in B)(\check{u} \in G \vee -\check{u} \in G)\Vert  &= \prod_{u \in B} ((-1) + \Vert \check{u} \in G \vee -\check{u} \in G\Vert ) \\
&= \prod_{u \in B} (\Vert \check{u} \in G\Vert  + \Vert \!-\!\check{u} \in G\Vert ) \\
&= \prod_{u \in B} (u + (-u)) \\
&= \prod_{u \in B} 1 \\
&= 1
\end{align*}
$$
</li>
</ol> 
$\square$

<a name="ex14.14(ii)"></a>
### Exercise 14.14(ii).
<i>Solution.</i> We first note that since $B$ is complete, and that $\Vert \dot{G} \text{ is an ultrafilter on } B\Vert  = 1$ by <a href="#ex14.14(i)">Exercise 14.14(i)</a>, we have that:

$$
\begin{align*}
\norm{\prod X \in \dot{G}} &= \Vert (\exists u \in \dot{G})(\forall x \in \check{X}) \, u \leq x\Vert  \\
&= \sum_{u \in B}(\dot{G}(\check{u}) \cdot \Vert (\forall x \in \check{X}) \, \check{u} \leq x\Vert ) \\
&= \sum_{u \in B}(u \cdot \Vert (\forall x \in \check{X}) \, \check{u} \leq x\Vert )
\end{align*}
$$

Now for each $u \in B$, we have $\Vert (\forall x \in \check{X}) \, \check{u} \leq x\Vert  = \prod_{x \in X} \Vert \check{u} \leq \check{x}\Vert $. Observe that RHS is $1$ iff $u \leq \prod X$, and $0$ otherwise. Thus:

$$
\begin{align*}
\sum_{u \in B}(u \cdot \Vert (\forall x \in \check{X}) \, \check{u} \leq x\Vert ) = \sum_{u \leq \prod X} u = \prod X
\end{align*}
$$

On the other hand, we have:

$$
\begin{align*}
\Vert \check{X} \subseteq \dot{G}\Vert  &= \Vert (\forall x \in \check{X}) \, x \in \dot{G} \Vert  \\
&= \prod_{x \in X} \Vert \check{x} \in \dot{G}\Vert  \\
&= \prod_{x \in X} x \\
&= \prod X
\end{align*}
$$

Thus:

$$
\begin{align*}
\Vert \text{if $\check{X} \subseteq \dot{G}$ then $\prod X \in \dot{G}$}\Vert  &= -\Vert \check{X} \subseteq \dot{G}\Vert  + \norm{\prod X \in \dot{G}} \\
&= -\prod X + \prod X \\
&= 1
\end{align*}
$$
 
$\square$

<a name="ex14.15"></a>
## Exercise 14.15.
<i>Solution.</i> Define the map $h : M^B/G \to M[G]$ by stipulating that $h([x]) := x^G$. This is well-defined and one-to-one by Lemma 14.28(ii), preserves the $\in$ predicate by Lemma 14.28(i), and is clearly onto by definition of $h$ and $M[G]$. 
$\square$

<a name="ex14.16"></a>
## Exercise 14.16.
<i>Solution.</i> By <a href="#ex14.14(i)">Exercise 14.14(i)</a> $H$ remains an ultrafilter as $\Vert \dot{G} \text{ is an ultrafilter on } B\Vert  = 1$ implies:

$$
\begin{align*}
\Vert \pi(\dot{G}) \text{ is an ultrafilter on } \pi(B)\Vert  = \Vert \dot{H} \text{ is an ultrafilter on } B\Vert  = 1
\end{align*}
$$

Similarly by <a href="#ex14.14(ii)">Exercise 14.14(ii)</a>, $H$ remains generic. $M[H] \subseteq M[G]$ as $G,\pi \in M[G]$ so $H = \pi(G) \in M[H]$. This argument is symmetric between $G$ and $H$, so $M[H] = M[G]$. 
$\square$