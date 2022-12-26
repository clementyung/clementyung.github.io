---
title: "11) Borel and Analytic Sets
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-11
excerpt: ""
---

{% include commands.html %}

<a name="ex11.1"></a>
## Exercise 11.1.
<i>Solution.</i> Let $\lbrace A_n : n < \omega\rbrace$ be a countable collection of sets.

<b>Countable union:</b> For $s \in \Seq$, let:

$$
\begin{align*}
A_s =
\begin{cases}
A_{s(0)}, &\text{if $\length(s) > 0$} \\
\N, &\text{otherwise} \\
\end{cases}
\end{align*}
$$

Then, we have that:

$$
\begin{align*}
\mathcal{A}\lbrace A_s : s \in \Seq\rbrace = \bigcup_{a \in \omega^\omega} \bigcap_{n=0}^\infty A_{a\restrictedto n} = \bigcup_{a \in \omega^\omega} \bigcap_{n=1}^\infty A_{a(0)} = \bigcup_{a \in \omega^\omega} A_{a(0)} = \bigcup_{n=0}^\infty A_n
\end{align*}
$$

<b>Countable intersection:</b> For $s \in \Seq$, let:

$$
\begin{align*}
A_s := A_{\length(s)}
\end{align*}
$$

Then, we have that:

$$
\begin{align*}
\mathcal{A}\lbrace A_s : s \in \Seq\rbrace = \bigcup_{a \in \omega^\omega} \bigcap_{n=0}^\infty A_{a\restrictedto n} = \bigcup_{a \in \omega^\omega} \bigcap_{n=1}^\infty A_n = \bigcap_{n=1}^\infty A_n
\end{align*}
$$
 
$\square$

<a name="ex11.2"></a>
## Exercise 11.2.
<i>Solution.</i> We prove the identity in the hint. Since $\lbrace A_s : \func{length}(s) = n\rbrace$ is countable, the result follows.

For any $a \in \omega^\omega$, we note that $A_{a\restrictedto n} \in \lbrace A_s : \func{length}(s) = n\rbrace$, therefore $A_{a\restrictedto n} \subseteq \bigcup\lbrace A_s : \func{length}(s) = n\rbrace$. Taking intersections on both sides yields $\bigcap_{n=0}^\infty A_{a\restrictedto n} \subseteq \bigcap_{n=0}^\infty\bigcup\lbrace A_s : \func{length}(s) = n\rbrace$. Since this holds for all $a$, we have $\bigcup_{a \in \omega^\omega} \bigcap_{n=0}^\infty A_{a\restrictedto n} \subseteq \bigcap_{n = 0}^\infty \bigcup\lbrace A_s : \func{length}(s) = n\rbrace$.

On the other hand, let $x \in \bigcap_{n = 0}^\infty \bigcup\lbrace A_s : \func{length}(s) = n\rbrace$. So for each $n$ there exists an $s_n \in \N$ such that $\func{length}(s_n) = n$ and $x \in A_{s_n}$.

<b>Claim.</b>. For each $n$, $s_n$ is an initial segment of $s_{n+1}$.

<i>Proof.</i> Suppose this fails at some $n \geq 1$. Let:

$$
\begin{align*}
m := \min\lbrace k \in \omega : s_n(k) \neq s_{n+1}(k)\rbrace
\end{align*}
$$

Thus, we have $s_n\restrictedto m = t^\frown u$ and $s_{n+1}\restrictedto m = t^\frown v$ for some $t \in \N$ and $u,v \in \omega$.

By the property in (11.10), we have that $x \in A_{s_n\restrictedto m}$ and $x \in A_{s_{n+1}\restrictedto m}$, so $A_{t^\frown v} \cap A_{t^\frown u} \neq \emptyset$. This contradicts the additional condition in the hypothesis. 
$\blacksquare$

Thus, we may let $a := \bigcup_{n < \omega} s_n \in \N$, and we have that $s_n = a\restrictedto n$, so $x \in \bigcap_{n=0}^\infty A_{a\restrictedto n}$ for all $n < \omega$, proving the reverse inclusion. 
$\square$

<a name="ex11.3"></a>
## Exercise 11.3.
<i>Solution.</i> By the first paragraph of the proof of Lemma 11.11, for all $n$ we have that $A_n$ and $\bigcup_{i \neq n} A_i$ are separated (since $A_n$ and $A_i$, $i \neq n$, are separated by Lemma 11.11). Thus, for each $n$ we define $E_n$ to be the Borel set such that $A_n \subseteq E_n \subseteq X - \bigcup_{i \neq n} A_i$. Then define:

$$
\begin{align*}
D_n := E_n - \bigcup_{i \neq n} E_i
\end{align*}
$$

Then clearly $A_n \subseteq D_n$ for all $n$, and $D_i \cap D_j = \emptyset$ for all $i \neq j$. 
$\square$

<a name="ex11.4"></a>
## Exercise 11.4.
<i>Solution.</i> There is probably a typo in the problem, as we can simply let each $G_n$ be an open interval around $a_n$ of small enough size and the assertion follows. Of course $G_n$ can have rational endpoints. Thus, we do the problem with the requirement $A \subseteq \bigcap_{n=0}^\infty G_n$ instead.

We first define $G_0$. Let $J$ be an open interval (with rational endpoints) around $0$ of measure $<\frac{a_0}{2}$. Since $\lim_n a_n = 0$, all but finitely many of the points in the set $\lbrace a_i : i < \omega\rbrace$ lies in $J$. Enumerate the uncovered points $\lbrace a_{i_0},\dots,a_{i_k}\rbrace$. Let $I_i$ be an open interval (with rational endpoints) around $a_i$ of measure $<\frac{a_0}{2(k + 1)}$. Let:

$$
\begin{align*}
G_0 := J \cup \bigcup_{i=0}^k I_i
\end{align*}
$$

Then $G_0$ is a finite union of open intervals such that $A \subseteq G_0$. We may construct the remaining $G_n$ inductively, by ensuring that all open intervals chosen when constructing $G_{n+1}$ lie in $G_n$. Clearly $A \subseteq \bigcap_{n=0}^\infty G_n$. 
$\square$

<a name="ex11.5"></a>
## Exercise 11.5.
<a name="lem11.5.A"></a>
<b>Lemma 11.5.A.</b> Every meager set is included in a meager $F_\sigma$ set.

<i>Proof.</i> Let $M$ be a meager set, so $M = \bigcup_{i=0}^\infty X_i$, where $X_i$ is nowhere dense for all $i$. Let $M' := \bigcup_{i=0}^\infty \cl(X_i)$. Since closure of nowhere dense set is nowhere dense, $M'$ is meager. Clearly $M'$ is $F_\sigma$. 
$\blacksquare$

<a name="lem11.5.B"></a>
<b>Lemma 11.5.B.</b> If $U$ is open, then $\del U := \bar{U} - U$ is nowhere dense.

<i>Proof.</i> Note that $\del U$ is closed. Observe furthermore that $\del U = \bar{U} \cap U^c$. Thus:

$$
\begin{align*}
\int(\del U) = \int(\bar{U}) \cap \int(U^c) = \int(\bar{U}) \cap (\bar{U})^c \subseteq \bar{U} \cap (\bar{U})^c = \emptyset
\end{align*}
$$

so $\del U$ has empty interior. 
$\blacksquare$

<i>Solution.</i> Let $A$ be a set with the Baire property, so $A = U \symdiff M$ for some open $U$ and meager $M$. By <a href="#lem11.5.A">Lemma 11.5.A</a>, we have that $M \subseteq M'$ for some meager $F_\sigma$ set $M'$. Let $F := \bar{U} \cup M'$. Clearly $F$ is $F_\sigma$. We shall show that $F - A$ is meager.

Note that every subset of meager set is meager. Observe that:

$$
\begin{align*}
F - A &= (\bar{U} \cup M') - ((U - M) \cup (M - U)) \\
&\subseteq (\bar{U} \cup M') - (U - M) \\
&= ((\bar{U} \cup M') \cap (U \cap M^c)^c) \\
&= ((\bar{U} \cup M') \cap (U^c \cup M)) \\
&\subseteq (\bar{U} \cup M') \cap (U^c \cup M') \\
&= (\bar{U} - U) \cup M'
\end{align*}
$$

Since $\bar{U} - U$ is meager by <a href="#lem11.5.B">Lemma 11.5.B</a>, and $M'$ is also meager, $F - A$ is meager.

Un the other hand, let $G := U - M' \subseteq U - M \subseteq A$. Since $M'$ is $F_\sigma$, $U - M'$ is $G_\delta$. Then $A - G$ is meager, as:

$$
\begin{align*}
A - G &= ((U - M) \cup (M - U)) - (U - M') \\
&\subseteq ((U - M) - (U - M')) \cup M \\
&\subseteq M' \cup M \\
&= M'
\end{align*}
$$

which is meager. 
$\square$

<a name="ex11.6"></a>
## Exercise 11.6.
<i>Solution.</i> Write $A = U \symdiff M$ where $U$ is open and $M$ is meager. Let $U' := \int(\bar{U})$. Then:

$$
\begin{align*}
A \symdiff U' &= (U \symdiff M) \symdiff U' \\
&= ((U \symdiff M) - U') \cup (U' - (U \symdiff M)) \\
&= (((U - M) \cup (M - U)) - U') \cup (U' - ((U - M) \cup (M - U))) \\
&\subseteq ((U - U') \cup (M - U')) \cup (U' - (U - M)) \\
&\subseteq M \cup (U' - U)
\end{align*}
$$

Since $U' - U \subseteq \bar{U} - U$, by <a href="#lem11.5.B">Lemma 11.5.B</a> $U' - U$ is meager. Thus, $A \symdiff U'$ is meager. It remains to show that $U'$ is regular open.

To do this, it suffices to show that $\bar{\int(\bar{U})} = \bar{U}$. On one hand, since $\int(\bar{U}) \subseteq \bar{U}$ and $\bar{U}$ is closed, we have that $\bar{\int(\bar{U})} \subseteq \bar{U}$ (this holds for all closed sets). Conversely, suppose $x \in \bar{U}$. Then for all open $U_x \ni x$, we have that $U_x \cap U \neq \emptyset$. But $U \subseteq \int(\bar{U})$, so $U_x \cap \int(\bar{U}) \neq \emptyset$ for all open $U_x \ni x$. Hence $x \in \bar{\int(\bar{U})}$.

We now show that such a $U$ is unique. Suppose $U_1$ and $U_2$ are regular open sets such that both $A \symdiff U_1$ and $A \symdiff U_2$ are meager. Note that this is equivalent to saying that $A = U_1 \symdiff M = U_2 \symdiff N$ for meager sets $M$ and $N$, which gives $U_1 \symdiff U_2 = M \symdiff N$. Thus:

$$
\begin{align*}
U_1 - \bar{U_2} \subseteq U_1 - U_2 \subseteq U_1 \symdiff U_2 \subseteq M \symdiff N
\end{align*}
$$

Now $M \symdiff N$ is meager, so $U_1 - \bar{U_2}$ is a meager open set, thus empty (by Baire category theorem). This implies that $U_1 \subseteq \int(\bar{U_2}) = U_2$. This argument is symmetric between $U_1$ and $U_2$, so equality holds. 
$\square$

<a name="ex11.7"></a>
## Exercise 11.7.
<i>Solution.</i> Following the hint, if $M$ has the Baire property, then $M = U \symdiff N$ for some open $U$ and meager $N$. Then $U - M \subseteq N$ is also meager. Take some interval $(a,b) \subseteq U$, and we have that $(a,b) - M$ is meager. Since $\bigcup_{q \in \Q} M_q \cap (a,b) = (a,b)$, and the sets $M_q$'s are pairwise disjoint, we have that $\bigcup_{q \in \Q, q \neq 0} M_q \cap (a,b) = (a,b) - M$. Thus, $(a,b) \cap M_q$ is meager for all rational $q \neq 0$.

Since the meager property is translational invariant, we have that $(a - q, b - q) \cap M$ (which is $(a,b) \cap M_q$ shifted to the left by length $q$) is meager. Thus, $M = \bigcup_{q \in \Q} (a-q,b-q) \cap M$ is meager. By translational invariance again, this implies that $M_q$ is meager for all rational $q$. Thus, $\R = \bigcup_{q \in \Q} M_q$ is meager, a contradiction. 
$\square$

<a name="ex11.8"></a>
## Exercise 11.8.
<i>Solution.</i> The hint solves the problem. 
$\square$