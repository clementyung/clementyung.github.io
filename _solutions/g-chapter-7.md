---
title: "7) Filters, Ultrafilters and Boolean Algebras"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-7
excerpt: ""
---

{% include commands.html %}

<body>
<a name="ex7.1"></a><br/>
<h2>Exercise 7.1.</h2>
<i>Solution.</i> We check the axioms.
<ol>
<li> Clearly $X \in P(X) \cap F$ and $\emptyset \notin P(X) \cap F$.</li>
<li> Let $Y,Z \in P(X) \cap F$. Then $Y,Z \subseteq P(X)$ i.e. $Y,Z \subseteq X$. Then $Y \cap Z \subseteq X$. Since $F$ is a filter, $Y \cap Z \in F$. Thus, $Y \cap Z \in P(X) \cap F$.</li>
<li> Let $Y \in P(X) \cap F$ and let $Z \subseteq X$ such that $Y \subseteq Z$. Then immediately $Z \in P(X)$. On the other hand, since $F$ is a filter, $Z \in F$. Thus, $Z \in P(X) \cap F$.</li></ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.2"></a><br/>
<h2>Exercise 7.2.</h2>
<i>Solution.</i> We first check that $F$ is a filter.
<ol>
<li> $S \in F$, as $S = \hat{\emptyset}$. To see that $\emptyset \notin F$, if otherwise we have that $\emptyset \supseteq \hat{P}$ for some $P \in S$. This implies that $\hat{P} = \emptyset$. But this is clearly impossible, as $P \in \hat{P}$.</li>
<li> Suppose $X,Y \in F$. Then $X \supseteq \hat{P}$ and $Y \supseteq \hat{Q}$ for some $X,Y \in S$. Since $S$ is a filter, we have $R := P \cup Q \in S$. Then $X \supseteq \hat{R}$ and $Y \supseteq \hat{R}$, as if $T \in \hat{R} \implies R \subseteq T$, then $P \subseteq R \subseteq T$, so $T \in \hat{P} \subseteq X$ (and similarly for $Y$). Thus, we have $\hat{R} \subseteq X \cap Y$, hence $X \cap Y \in F$.</li>
<li> If $X \in F$ and $X \subseteq Y \in S$, then we have $Y \supseteq X \supseteq \hat{P}$ for some $P \in S$, so $Y \in F$.</li>
</ol>
Let $B := \lbrace \lbrace a\rbrace^\wedge : a \in A\rbrace$. Clearly $B \subseteq F$. It remains to show that for every filter $G$ such that $B \subseteq G$, $F \subseteq G$. Let $X \in F$, so $X \supseteq \hat{P}$ for some $P \in S$. Suppose $P = \lbrace a_1,\dots,a_n\rbrace$. We observe that $\hat{P} = \lbrace a_1\rbrace^\wedge \cap \cdots \cap \lbrace a_n\rbrace^\wedge$, and since $B \subseteq G$ and $G$ is closed under finite intersections, $\hat{P} \in G$. Then $X \in G$, as desired.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.3"></a><br/>
<h2>Exercise 7.3.</h2>
<i>Solution.</i> Say $U$ is an ultrafilter on the set $S$. Suppose $X \notin U$ and $Y \notin U$. Then $S - X \in U$ and $S - Y \in U$, so $(S - X) \cap (S - Y) = S - (X \cup Y) \in U$. But this implies that $(X \cup Y) \cap (S - (X \cup Y)) = \emptyset \in U$, a contradiction.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.4"></a><br/>
<h2>Exercise 7.4.</h2>
<i>Solution.</i> Let:<br/>
$$
\begin{align*}<br/>
U' := \lbrace X \subseteq S \times S : \lbrace a \in S : \lbrace b \in S : (a,b) \in X\rbrace \in U\rbrace \in U\rbrace<br/>
\end{align*}$$
We verify the axioms.
<ol>[label=(\roman*)]<br/>
<li> Let $Y,Z \subseteq S$. Then for all $a \in Y$, we have $\lbrace b \in S : (a,b) \in Y \times Z\rbrace = Z \in U$, so $\lbrace a \in S : \lbrace b \in S : (a,b) \in Y \times Z\rbrace \in U\rbrace \in U$. Thus, $Y \times Z \in U'$, and in particular $S \times S \in U'$.</li>
<li> Suppose $X \in U'$, and let $X \subseteq X' \subseteq S \times S$. Then for all $a \in S$, we have $\lbrace b \in S : (a,b) \in X'\rbrace \supseteq \lbrace b \in S : (a,b) \in X'\rbrace$, so $\lbrace b \in S : (a,b) \in X'\rbrace \in U$ by upward closure of $U$. In other words, we have:<br/>
$$
\begin{align*}<br/>
\lbrace a \in S : \lbrace b \in S : (a,b) \in X\rbrace \in U\rbrace \subseteq \lbrace a \in S : \lbrace b \in S : (a,b) \in X'\rbrace \in U\rbrace<br/>
\end{align*}$$
By upward closure of $U$ again, we have $\lbrace a \in S : \lbrace b \in S : (a,b) \in X'\rbrace \in U\rbrace \in U$. Therefore, $X' \in U'$.</li>
<li> Let $X,X' \in U'$. It's easy to see that for all $a \in S$:<br/>$$
\begin{align*}<br/>
\lbrace b \in S : (a,b) \in X \cap X'\rbrace = \lbrace b \in S : (a,b) \in X\rbrace \cap \lbrace b \in S : (a,b) \in X'\rbrace<br/>
\end{align*}$$
Since $U$ is closed under finite intersection, $\lbrace b \in S : (a,b) \in X \cap X'\rbrace \in U$. In other words:<br/>
$$
\begin{gather*}<br/>
\lbrace a \in S : \lbrace b \in S : (a,b) \in X \cap X'\rbrace \in U\rbrace \\<br/>
= \\<br/>
\lbrace a \in S : \lbrace b \in S : (a,b) \in X\rbrace \in U\rbrace \cap \lbrace a \in S : \lbrace b \in S : (a,b) \in X'\rbrace \in U\rbrace<br/>
\end{gather*}$$
Again, since $U$ is closed under finite intersection, we have that $X \cap X' \in U'$.</li>
</ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.5"></a><br/>
<h2>Exercise 7.5.</h2>
<a name="lem7.5.A"></a><br/>
<b>Lemma 7.5.A.</b> Let $U$ be a filter on a set $S$. Then $U$ is an ultrafilter iff for all $X,Y \subseteq S$, if $X \cup Y \in U$ then $X \in U$ or $Y \in U$.<br/>
<br/>
<i>Proof.</i> <u>$\implies:$</u> Let $X,Y \subseteq S$ such that $X \cup Y \in U$. Suppose $X \notin U$ and $Y \notin U$. Since $U$ is an ultrafilter, $S - X,S - Y \in U$. Thus $(S - X) \cap (S - Y) = S - (X \cup Y) \in U$. This contradicts that $X \cup Y \in U$.<br/>
<br/>
<u>$\impliedby$:</u> Let $X \subseteq S$. Then $X \cup (S - X) = S \in U$, so $X \in U$ or $S - X \in U$. Thus $U$ is an ultrafilter.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> We verify the axioms.
<ol>
<li> We have $f_{-1}(T) = S \in U$, so $T \in f_*(U)$.</li>
<li> Let $X,Y \in f_*(U)$, so $f_{-1}(X),f_{-1}(Y) \in U$. Then $f_{-1}(X) \cap f_{-1}(Y) = f_{-1}(X \cap Y) \in U$, so $X \cap Y \in U$.</li>
<li> Let $X \in f_*(U)$ and suppose $X \subseteq Y$. Then $f_{-1}(X) \subseteq f_{-1}(Y)$, and since $f_{-1}(X) \in U$ we have that $f_{-1}(Y) \in U$. Thus $Y \in f_*(U)$.</li>
<li> Let $X \subseteq T$. Observe that $f_{-1}(X) \cup f_{-1}(T - X) = f_{-1}(T) = S \in U$. By <a href="#lem7.5.A">Lemma 7.5.A</a>, we have $f_{-1}(X) \in U$ or $f_{-1}(T - X) \in U$. Thus $X \in f_*(U)$ or $T - X \in f_*(U)$.</li>
</ol>
Thus $f_*(U)$ is an ultrafilter.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.6"></a><br/>
<h2>Exercise 7.6.</h2>
<i>Solution.</i> For each $X \subseteq \boldsymbol{N}$, let $S_X := \lbrace a_n : n \in X\rbrace$. Let:<br/>
$$
\begin{align*}<br/>
Y := \bigcap_{X \in U} \bar{S_X}<br/>
\end{align*}$$
Note that $\ss{\bar{S_X} : X \in U}$ is a family of compact sets (as the sequence is bounded) satisfying the finite intersection property, so $Y$ is non-empty. Let $a \in Y$. We shall show that $a$ is a $U$-limit.<br/>
<br/>
Let $\varepsilon > 0$, and suppose $A := \lbrace n : \vert a_n - a\vert  < \varepsilon\rbrace \notin U$. Then $B := \boldsymbol{N} - A \in U$. Since $a \in Y$, we have that $a \in \bar{S_B}$, so there exists $a_n \in S_B$ such that $\vert a_n - a\vert  < \varepsilon$, a contradiction. Thus $A$ is a $U$-limit.<br/>
<br/>
To see that the $U$-limit $a$ is unique, suppose $a'$ is another $U$-limit. Fix $\varepsilon > 0$, and let $A := \lbrace n : \vert a_n - a\vert  < \varepsilon\rbrace$, $A' := \lbrace n : \vert a_n - a'\vert  < \varepsilon\rbrace$. Then $A \cap A'$ is non-empty, so take $a_n \in A \cap A'$. Then $\vert a - a'\vert  \leq \vert a - a_n\vert  + \vert a_n - a'\vert  < 2\varepsilon$, so we see that $a = a'$ by letting $\varepsilon \to 0$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.7"></a><br/>
<h2>Exercise 7.7.</h2>
<i>Solution.</i> <u>$\implies$:</u> Let $A_0 \supseteq A_1 \supseteq \dots \supseteq A_n \subseteq \dots$ be a decreasing sequence of elements of $D$. We may assume WLOG that it is strictly decreasing,  For each $n \in \omega$ we define $B_n$ by $B_0 := \boldsymbol{N} - A_0$, and $B_{n+1} := A_n - A_{n+1}$. Now consider:<br/>
$$
\begin{align*}<br/>
\lbrace B_n : n \in \omega\rbrace \cup \ss{\lbrace k\rbrace : k \in \bigcap_{n=0}^\infty A_n}<br/>
\end{align*}$$
Clearly this is a partition of $\boldsymbol{N}$ into $\aleph_0$ pieces, each which is not in $D$. Since $D$ is a $p$-point, there exists an $X \in D$ such that $X$ has finite intersection with all sets in this partition. Then for each $n$, we have:<br/>
$$
\begin{align*}<br/>
X - A_n = X \cap \bb{\bigcup_{k<n} B_k} = \bigcup_{k<n} X \cap B_k<br/>
\end{align*}$$
which is finite.<br/>
<br/>
<u>$\impliedby$:</u> Let $\lbrace A_n : n \in \omega\rbrace$ be a a partition of $\omega$ into $\aleph_0$ pieces, with $A_n \notin D$ for all $n$. Let $B_n := \bigcup_{m \geq n} A_m = \boldsymbol{N} - \bigcup_{m<n} A_m$. Note that since $A_m \notin D$ for all $m < n$, $\bigcup_{m<n} A_m \notin D$, so $B_n \in D$ for all $n$. Clearly $B_0 \supseteq B_1 \supseteq \dots$, so by hypothesis we obtain an $X \in D$ such that $X - B_n$ is finite for each $n$. Then:<br/>
$$
\begin{align*}<br/>
X \cap A_n \subseteq X \cap \bigcup_{m<n+1} A_n = X - B_{n+1}<br/>
\end{align*}$$
which is finite.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.8"></a><br/>
<h2>Exercise 7.8.</h2>
<a name="lem7.8.A"></a><br/>
<b>Lemma 7.8.A.</b> For any countable linearly ordered set $(P,<)$, there exists a subset $X \subseteq \Q$ such that $(P,<) \cong (X,<)$, where $<$ in $(X,<)$ is the usual order of rationals.<br/>
<br/>
<i>Proof.</i> Write $P = \lbrace p_n : n < \omega\rbrace$. Define $q_n \in \Q$ as follows: Let $q_0$ be any rational number. If $q_0,\dots,q_{n-1}$ are defined, we may choose $q_n$ such that for $i < n$, $q_i < q_n$ iff $p_i < p_n$ (this is possible as $\Q$ is dense, and $\lbrace q_0,\dots,q_{n-1}\rbrace$ is discrete. Then clearly $(P,<) \cong (\lbrace q_n : n < \omega\rbrace,<)$.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> By <a href="#lem7.8.A">Lemma 7.8.A</a> we may assume WLOG that $P \subseteq \Q$, and $<$ is the usual ordering of rationals. If $P$ is unbounded in $\Q$, we may find an unbounded sequence in $P$, which will be order-type $\omega$ (if it tends to $+\infty$) or $\omega^\ast $ (if it tends to $-\infty$). Thus we assume $P$ is bounded, say $P \subseteq [a_0,b_0]$.<br/>
<br/>
Now suppose $a_n,b_n$ are defined such that $P \cap [a_n,b_n] \in D$. By <a href="#lem7.5.A">Lemma 7.5.A</a>, we have that $P \cap \sb{a_n,\frac{a_n + b_n}{2}} \in D$ or $P \cap \sb{\frac{a_n + b_n}{2},b_n} \in D$. Let $[a_{n+1},b_{n+1}]$ be one of these two intervals such that $P \cap [a_{n+1},b_{n+1}] \in D$.<br/>
<br/>
Let $r$ be the unique real number in the set $\bigcap_{n=0}^\infty [a_n,b_n]$. Then $P \cap [a,r] \in D$ or $P \cap [r,b] \in D$. Suppose it's the first case. Then since $[a,r] \cap [a_n,b_n] = [a_n,r]$ for all $n$, we have that $P \cap [a_n,r] \in D$ for all $n$. Then $P \cap [a_0,r] \supseteq P \cap [a_1,r] \supseteq \dots$, and since $D$ is a $p$-point, by <a href="#ex7.7">Exercise 7.7</a> there exists an $X \in D$ such that $X - (P \cap [a_n,r])$ is finite for all $n$. Note that $X$ is infinite as $D$ is non-principal. We define $x_n \in X$ inductively as follows: Let $x_0 \in [a_n,r) \cap P$ be any point. Given $x_n$, let $N$ be the smallest integer such that $x_n < a_N$ (this is well-defined as $a_n \nearrow r$). Since $X - (P \cap [a_n,r))$ is finite, there exists an $x_{n+1} \in X \cap P \cap [a_N,r)$ . Then $x_0 > x_1 > \dots$, so $P$ has a subset or order-type $\omega$.<br/>
<br/>
If instead $P \cap [r,b] \in D$, then we may repeat the previous paragraph but with $<$ reversed, yielding a subset of order-type $\omega^\ast $.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.9"></a><br/>
<h2>Exercise 7.9.</h2>
<i>Solution.</i> <u>$\implies$:</u> Let $f : \omega \to \omega$. Consider the partition $\lbrace f_{-1}(\lbrace n\rbrace) : n \in \omega\rbrace$. If $f_{-1}(\lbrace n\rbrace) \in D$ for some $n$, then $f$ takes the constant value $n$ on the set $f_{-1}(\lbrace n\rbrace)$. Otherwise, since $D$ is Ramsey there exists some $X \in D$ such that $X \cap f_{-1}(\lbrace n\rbrace)$ has at most one element for all $n \in \omega$ ($X \cap f_{-1}(\lbrace n\rbrace) = \emptyset$ if $f_{-1}(\lbrace n\rbrace) = \emptyset$). Then $f$ is one-to-one on $X$.<br/>
<br/>
<u>$\implies$:</u> Let $\lbrace A_n : n \in \omega\rbrace$ be a partition of $\omega$ into $\aleph_0$ pieces such that $A_n \notin D$ for all $n$. Let $f : \omega \to \omega$ be defined by:<br/>
$$
\begin{align*}<br/>
f(n) = \text{the unique $m$ such that $n \in A_m$}<br/>
\end{align*}$$
By assumption, there exists $X \in D$ such that $f$ is either constant or one-to-one on a set in $D$. If $f$ takes the constant value $m$ on $X$, then $X \subseteq A_m$ so $A_m \in D$, a contradiction. Thus $f$ is one-to-one on $X$, hence $X \cap A_m$ has at most one element for all $m$. Thus there exists $X' \supseteq X$ such that $X' \cap A_m$ has one element for all $m$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.10"></a><br/>
<h2>Exercise 7.10.</h2>
<i>Solution.</i> The hint basically solves the problem. We clarify some details:
<ol>
<li> In $X$, obviously all decreasing must be of finite length since $\boldsymbol{N}$ is well-ordered. By "The set $Y$ is handled similarly" they mean repeating the proof on the set $Y - Z$, the set of all $n$ such that $f(n) > n$ and the longest chain $n < f(n) < f^2(n) < \dots$ is finite.</li>
<li> If $Z_0 \in D$, then since $f_{-1}(Z_1) \cap Z = Z_0$ we have that $f_{-1}(Z_1) \in D$ by upward closure. Thus $Z_1 \in D$ as $D = f_*(D)$. But $Z_0 \cap Z_1 = \emptyset$, a contradiction. If $Z_1 \in D$, a similar contradiction can be derived.</li>
</ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.11"></a><br/>
<h2>Exercise 7.11.</h2>
<i>Solution.</i> Let $f,g : \omega \to \omega$ such that $D = f_*(E)$ and $E = g_*(D)$. Then $D = f_*(g_*(D)) = (f \circ g)_*(D)$. By <a href="#ex7.10">Exercise 7.10</a>, we have $X := \lbrace n : f(g(n)) = n\rbrace \in D$. Let $Y := \ran(g\restrictedto X)$. Then $g\restrictedto X$ is one-to-one and maps onto $Y$, and that for $Z \subseteq Y$ we have:<br/>
$$
\begin{align*}<br/>
Z \in E \iff f_{-1}(Z) \in D \iff (g\restrictedto X)_{-1}(Z) \in D<br/>
\end{align*}$$
By <a href="#lem7.5.A">Lemma 7.5.A</a>, we may fix a $X' \subseteq X$, with $X' \in D$, such that $X - X'$ is infinite. Let $Y' := g"(X')$ (so $Y' \in E$). Let $g' : \omega - X' \to \omega - Y'$ be any bijection, and let $h := g\restrictedto X' \cup g'$. clearly $h$ is one-to-one and onto. We shall show that $E = h_*(D)$, so $E \equiv D$. Indeed, let $Z \subseteq \omega$. Since $Y' \in E$ we have that $Z \in E$ iff $Z \cap Y' \in E$. Thus:<br/>
$$
\begin{align*}<br/>
Z \in E &\iff Z \cap Y' \in E \\<br/>
&\iff (g\restrictedto X')_{-1}(Z \cap Y') \in D \\<br/>
&\iff h_{-1}(Z \cap Y') \in D \\<br/>
&\iff h_{-1}(Z) \in D<br/>
\end{align*}$$
as desired. Note that this proof shows the following: If $E = g_*(D)$ and $g$ is one-to-one on a set in $D$, then $D \leq E$ (and hence $D \equiv E$).<p align="right">$\square$</p><br/>
<br/>
<b>Remark.</b>. Thus $\leq$ is a partial ordering of ultrafilters on $\omega$.<br/>
<br/>
<a name="ex7.12"></a><br/>
<h2>Exercise 7.12.</h2>
<i>Solution.</i> <u>$\impliedby$:</u> Suppose $D$ is Ramsey, and $E = f_*(D)$ is non-principal. By <a href="#ex7.9">Exercise 7.9</a>, $f$ is either one-to-one on a set in $D$, or constant on a set in $D$. Observe that if it is the latter case, say $f$ takes constant value $a$ on $X \in D$, then $\lbrace a\rbrace \in E$, so $E$ is principal, a contradiction. Thus, $f$ is one-to-one on a set in $D$. By the proof of <a href="#ex7.11">Exercise 7.11</a>, we see that this implies that $D \leq E$, so $D \equiv E$ necessarily (hence $D$ is minimal).<br/>
<br/>
<u>$\implies$:</u> Suppose $D$ is minimal. Fix any $f : \omega \to \omega$, and consider the ultrafilter $f_*(D)$. If $f_*(D)$ is principal and is generated by $\lbrace a\rbrace$, then $f_{-1}(\lbrace a\rbrace) \in D$, i.e. $f$ is constant on a set in $D$. Otherwise, since $D$ is minimal, $D \leq f_*(D)$. By <a href="#ex7.10">Exercise 7.10</a> and <a href="#ex7.11">Exercise 7.11</a> this implies that $f$ is one-to-one on some set in $D$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.13"></a><br/>
<h2>Exercise 7.13.</h2>
<i>Solution.</i> Suppose $I$ is a non-principal $\omega_\alpha$-complete ideal on $\omega\alpha$. Let $\lbrace \beta_\gamma : \gamma < \cf(\alpha)\rbrace$ be a sequence cofinal in $\omega_\alpha$. Since $I$ is non-principal and $\omega_\alpha$-complete, it contains all bounded subset of $\omega_\alpha$, so $\beta_\gamma \in I$ for all $\gamma < \cf(\alpha)$. Since $\cf(\alpha) < \omega_\alpha$, we have that $\omega_\alpha = \bigcup_{\gamma<\cf(\alpha)} \beta_\gamma \in I$, a contradiction.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.14"></a><br/>
<h2>Exercise 7.14.</h2>
<i>Solution.</i> We verify the axioms. Let $\mu$ denote the Lebesgue measure, and let $I$ denote the set of all sets of reals of Lebesgue measure $0$.
<ol>
<li> Clearly $\mu(\emptyset) = 0$ and $\mu(\R) = \infty$, so $\emptyset \in I$ and $\R \notin I$.</li>
<li> Let $\lbrace X_n : n < \omega\rbrace$ be a set of $\aleph_0$ many Lebesgue measure $0$ sets. Since $\mu$ is $\sigma$-additive, we have:<br/>
$$
\begin{align*}<br/>
\mu\bb{\bigcup_{n=0}^\infty X_n} \leq \sum_{n=0}^\infty \mu(X_n) = \sum_{n=0}^\infty 0 = 0<br/>
\end{align*}$$
</li>
<li> It is a well-known theorem that the Lebesgue measure is a <b>complete measure</b>, i.e. every subset of measure $0$ set is measurable (and of course of measure $0$ as well). Thus $I$ is downward closed.</li></ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.15"></a><br/>
<h2>Exercise 7.15.</h2>
<i>Solution.</i> We verify the axioms. Let $I$ denote the set of all meager sets.
<ol>
<li> Clearly $\emptyset$ is nowhere dense hence meager, so $\emptyset \in I$. Baire Category Theorem 4.8. tells us that $\R$ is not meager, so $\R \notin I$.</li>
<li> Let $\lbrace X_n : n < \omega\rbrace$ be a set of $\aleph_0$ many Lebesgue measure $0$ sets. For each $X_n$, suppose $X_n = \bigcup_{i=0}^\infty Y_{i,n}$, where each $Y_{i,n}$ is nowhere dense. Let $X := \bigcup_{n=0}^\infty X_n$. Then $X = \bigcup_{(i,j) \in \omega \times\omega} Y_{i,j}$, and since $\omega \times \omega$ is countable, $X$ is meager. Thus $X \in I$.</li>
<li> Observe that every subset of a nowhere dense set is nowhere dense. Thus, if $X = \bigcup_{n=0}^\infty X_n$, where each $X_n$ is nowhere dense, and $Y \subseteq X$, then $Y = \bigcup_{n=0}^\infty X_n \cap Y$. Each $X_n \cap Y \subseteq X_n$ is nowhere dense, so $Y$ is meager and $Y \in I$.</li>
</ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.16"></a><br/>
<h2>Exercise 7.16.</h2>
<i>Solution.</i> We verify the axioms.
<ol>
<li> Clearly $S \supseteq \hat{P}$ for any $P \in S$, so $S \in F$. Since $\hat{P}$ are non-empty for all $P \in S$, $\emptyset \notin F$.</li>
<li> Let $\lbrace X_\alpha : \alpha < \lambda\rbrace$ be a set of sets in $F$, where $\lambda < \kappa$. Suppose $X_\alpha \supseteq \hat{P}_\alpha$. Observe that:<br/>
$$
\begin{align*}<br/>
Q \in \bigcap_{\alpha < \lambda} \hat{P}_\alpha &\iff (\forall \alpha < \lambda) \, P_\alpha \subseteq Q \\<br/>
&\iff \bigcup_{\alpha < \lambda} P_\alpha \subseteq Q \\<br/>
&\iff Q \in \bb{\bigcup_{\alpha < \lambda} P_\alpha}^\wedge<br/>
\end{align*}$$
Note that since $\vert P_\alpha\vert  < \kappa$ for all $\alpha < \lambda$, $\lambda < \kappa$ and $\kappa$ is regular, $\mod{\bigcup_{\alpha < \lambda} P_\alpha} < \kappa$. Thus $\bigcap_{\alpha < \lambda} \hat{P}_\alpha \in F$, so $\bigcap_{\alpha < \lambda} X_\alpha \in F$.</li>
<li> Clearly $F$ is upward closed.</li></ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.17"></a><br/>
<h2>Exercise 7.17.</h2>
<a name="lem7.17.A"></a><br/>
<b>Lemma 7.17.A.</b> Let $B$ be a Boolean algebra and let $u,v,w \in B$. Then $u \cdot v - w = u \cdot v - u \cdot w$.<br/>
<br/>
<i>Proof.</i> $$
\begin{align*}<br/>
u \cdot v - u \cdot w &= u \cdot v \cdot (-(u \cdot w)) \\<br/>
&= u \cdot v \cdot ((-u) + (-w)) \\<br/>
&= u \cdot v \cdot (-u) + u \cdot v \cdot (-w) \\<br/>
&= 0 + u \cdot v \cdot (-w) \\<br/>
&= u \cdot v - w<br/>
\end{align*}$$
<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> We first show that $(B,\oplus)$ forms an abelian group.
<ol>
<li> (Commutativity) This follows immediately from definition and that $+$ is commutative.</li>
<li> (Associativity) Let $u,v,w \in B$. Then:<br/>$$
\begin{align*}<br/>
&\eqbreak (u \oplus v) \oplus w \\<br/>
&= ((u - v) + (v - u)) \oplus w \\<br/>
&= (((u - v) + (v - u)) - w) + (w - ((u - v) + (v - u))) \\<br/>
&= (u \cdot (-v) + v \cdot (-u)) \cdot (-w) + w \cdot (-(u \cdot (-v) + v \cdot (-u))) \\<br/>
&= u \cdot (-v) \cdot (-w) + v \cdot (-u) \cdot (-w) + w \cdot (-(u \cdot (-v))) \cdot (-(v \cdot (-u))) \\<br/>
&= u \cdot (-v) \cdot (-w) + v \cdot (-u) \cdot (-w) + w \cdot ((-u) + v) \cdot ((-v) + u)) \\<br/>
&= u \cdot (-v) \cdot (-w) + v \cdot (-u) \cdot (-w) + w \cdot ((-u) \cdot (-v) + u \cdot v) \\<br/>
&= u \cdot (-v) \cdot (-w) + v \cdot (-u) \cdot (-w) + w \cdot (-u) \cdot (-v) + w \cdot u \cdot v<br/>
\end{align*}$$
Observe that the final expression is invariant under any permutation of $u,v,w$. Since $\oplus$ is commutative, it follows that it is associative.</li>
<li> (Identity) We have $u \oplus 0 = (u - 0) + (0 - u) = u + 0 = u$, so $0$ is the additive identity.</li>
<li> (Inverse) We have $u \oplus u = (u - u) + (u - u) = 0 + 0 = 0$, so every element is its own inverse.</li>
</ol>
We already know that $\cdot$ is associative and $1$ serves as the multiplicative identity. It remains to check that $\cdot$ is distributive with respect to $\oplus$. Indeed:<br/>
$$
\begin{align*}<br/>
u \cdot (v \oplus w) &= u \cdot ((v - w) + (w - v)) \\<br/>
&= u \cdot (v \cdot (-w) + w \cdot (-v)) \\<br/>
&= (u \cdot v) \cdot (-w) + (u \cdot w) \cdot (-v) \\<br/>
&= (u \cdot v - w) + (u \cdot w - v) \\<br/>
&=^\ast  (u \cdot v - u \cdot w) + (u \cdot w - u \cdot v) \\<br/>
&= (u \cdot v) \oplus (u \cdot w)<br/>
\end{align*}$$
where the starred equality follows from <a href="#lem7.17.A">Lemma 7.17.A</a>.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.18"></a><br/>
<h2>Exercise 7.18.</h2>
<i>Solution.</i> Let $B$ be a Boolean algebra with $X \subseteq B$. Let $B_X$ be the subalgebra generated by $X$ (the smallest subalgebra of $B$ containing $X$), and let $B_X' \subseteq B$ be the set of all $u \in B$ of the form stated in the question. We shall show that $B_X = B_X'$.<br/>
<br/>
Clearly $B_X' \subseteq B_X$ as $B_X$ is closed under $+$, $-$ and $\cdot$. Conversely, it's easy to see that $B_X'$ is itself a Boolean algebra (i.e. closed under $+$, $-$ and $\cdot$) containing $X$, and therefore $B_X \subseteq B_X'$ as $B_X$ is the <i>smallest</i> Boolean algebra containing $X$. Thus $B_X = B_X'$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.19"></a><br/>
<h2>Exercise 7.19.</h2>
<i>Solution.</i> Let $C := \lbrace a \cdot u + (b - u) : a,b \in A\rbrace$. We first see that $A \cup \lbrace u\rbrace \subseteq C$ - for each $a \in A$, we have $a = a \cdot u + a \cdot (-u) = a \cdot u + (a - u) \in C$, and $u = 1 \cdot u + (0 - u) \in C$. By closure under $+$, $-$ and $\cdot$, one may also see that if $D$ is a subalgebra containing $A \cup \lbrace u\rbrace$, then $D$ must contain $C$. It remains to show that $C$ is itself a subalgebra.<br/>
<br/>
Let $v,w \in C$. Write $v = a \cdot u + (b - u)$ and $w = c \cdot u + (d - u)$.<br/>
<br/>
Addition:<br/>
$$
\begin{align*}<br/>
v + w &= (a \cdot u + (b - u)) + (c \cdot u + (d - u)) \\<br/>
&= (a + c) \cdot u + ((b + d) - u) \in C<br/>
\end{align*}$$
Complement:<br/>
$$
\begin{align*}<br/>
-v &= -(a \cdot u + (b - u)) \\<br/>
&= -(a \cdot u) + (-(b \cdot (-u))) \\<br/>
&= (-a) \cdot (-u) + (-b) \cdot u \\<br/>
&= (-b) \cdot u + ((-a) - u) \in C<br/>
\end{align*}$$
Multiplication:<br/>
$$
\begin{align*}<br/>
v \cdot w &= (a \cdot u + (b - u)) \cdot (c \cdot u + (d - u)) \\<br/>
&= a \cdot u \cdot c \cdot u + b \cdot (-u) \cdot c \cdot u + a \cdot u \cdot d \cdot  (-u) + b \cdot (-u) \cdot d \cdot (-u) \\<br/>
&= (a \cdot c) \cdot u + (b \cdot d) \cdot (-u) \\<br/>
&= (a \cdot c) \cdot u + ((b \cdot d) - u) \in C<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.20"></a><br/>
<h2>Exercise 7.20.</h2>
<i>Solution.</i> Suppose $A$ is generated by $X = \lbrace x_1,\dots,x_k\rbrace$. We induct on the size of $k$. For $k = 1$, we of course must have $A = \lbrace 0,x_1,-x_1,1\rbrace$, so $\vert A\vert  = 4 = 2^{2^1}$. Now suppose $A$ is a Boolean algebra generated by $\lbrace x_1,\dots,x_{k+1}\rbrace$. Let $A'$ be the subalgebra generated by $\lbrace x_1,\dots,x_k\rbrace$. By induction hypothesis, $\vert A'\vert  \leq 2^{2^k}$. By <a href="#ex7.19">Exercise 7.19</a>, the map $\pi : A' \times A' \to A$ defined by $(a,b) \mapsto a \cdot x_{k+1} + (b - x_{k+1})$ is onto. Thus:<br/>
$$
\begin{align*}<br/>
\vert A\vert  \leq \vert A'\vert ^2 = (2^{2^k})^2 = 2^{2^k \cdot 2} = 2^{2^{k+1}}<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.21"></a><br/>
<h2>Exercise 7.21.</h2>
<i>Solution.</i> Let $B$ be a finite Boolean algebra. We shall prove this exercise in a series of claims.<br/>
<br/>
<b>Claim.</b>. For any non-zero $u \in B$, there exists an atom $a \leq u$. In particular, $B$ is atomic.<br/>
<br/>
<i>Proof.</i> Let $u \in B$ and suppose there is no atom $a \leq u$. Then in particular $u$ is not an atom, so we may obtain $a_0 < u$. $a_0$ is again not an atom, so we obtain another element $a_1 < a_0$. By repeating this, we obtain an infinite descending chain of non-zero elements $u > a_0 > a_1 > \dots$, contradicting that $B$ is infinite.<p align="right">$\blacksquare$</p><br/>
<br/>
Let $A = \lbrace a_1,\dots,a_n\rbrace$ be the set of all distinct atoms of $B$.<br/>
<br/>
<b>Claim.</b>. $\sum A = 1$, and for $i \neq j$ we have $a_i \cdot a_j = 0$. Thus $A$ is a partition of $B$.<br/>
<br/>
<i>Proof.</i> If $\sum A \neq 1$, then consider the element $1 - \sum A$. By the first claim, $1 - \sum A$ contains an atom $a$ below it. But clearly $a_i \not\leq 1 - \sum A$ for all $i$, a contradiction.<br/>
<br/>
Let $1 \leq i,j \leq k$, and suppose $a_i \cdot a_j \neq 0$. Since $a_i \cdot a_j \leq a_i$ and $a_i \cdot a_j \leq a_j$, and $a_i$ and $a_j$ are atoms, we have that $a_i = a_i \cdot a_j = a_j$, so $i = j$.<p align="right">$\blacksquare$</p><br/>
<br/>
<b>Claim.</b>. Every element $u \in B$ is of the form $u = a_{i_1} + \dots + a_{i_k}$ for some $1 \leq i_1 < \dots < i_k \leq n$<br/>
<br/>
<i>Proof.</i> Fix $u \in B$. Since $A$ is a partition of $B$, we have that $u = \sum_{i=1}^n u \cdot a_i$. But $u \cdot a_i \leq a_i$ and $a_i$ is an atom, so $u \cdot a_i = 0$ or $a_i$.<p align="right">$\blacksquare$</p><br/>
<br/>
Therefore, if we consider the map $\pi : P(A) \to B$ by $\pi(A) := \sum A$, we see that $\pi$ is one-to-one and onto. It's straightforward (albeit a little tedious) to check that $\pi$ is in fact an isomorphism of Boolean algebras. Thus, $\vert B\vert  = \vert P(A)\vert  = 2^n$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.22"></a><br/>
<h2>Exercise 7.22.</h2>
<i>Solution.</i> The approach we provide here is widely known as the "back-and-forth argument".<br/>
<br/>
Let $A,B$ be two countable atomless Boolean algebras. Write $A = \lbrace a_n : n < \omega\rbrace$ and $B = \lbrace b_n : n < \omega\rbrace$ such that $a_0 = b_0 = 0$ and $a_1 = b_1 = 1$. We shall construct a map $\pi : A \to B$ recursively: First let $\pi(a_0) = b_0$ and $\pi(a_1) = b_1$.<br/>
<br/>
Suppose we have defined $\pi$ on the subalgebra generated by $\lbrace a_0,\dots,a_{n-1}\rbrace$, denoted by $\c{a_0,\dots,a_{n-1}}$, such that $\pi\restrictedto \c{a_0,\dots,a_{n-1}}$ is a one-to-one Boolean algebra homomorphism. We wish to extend the definition of $\pi$ to $\c{a_0,\dots,a_n}$. If $a_n \in \c{a_0,\dots,a_{n-1}}$, then we're done. Otherwise, by <a href="#ex7.21">Exercise 7.21</a> $\c{a_0,\dots,a_n}$ is atomic, so we let $X := \lbrace x_0,\dots,x_m\rbrace$ be the set of all atoms of $\c{a_0,\dots,a_{n-1}}$, and $Y := \lbrace y_0,\dots,y_k\rbrace$ be the set of all atoms of $\c{a_0,\dots,a_n}$. Now for each each $0 \leq i \leq m$, there exists $y_{i,0},\dots,y_{i,k_i} \in Y$ such that $x_i = y_{i,0} + \dots + y_{i,k_i}$. Observe that since $\lbrace a_0,\dots,a_n\rbrace$ forms a partition of $\c{a_0,\dots,a_n}$ (as proven in the proof of <a href="#ex7.21">Exercise 7.21</a>), we have that the elements $y_{i,k_i}$'s are pairwise distinct, and:<br/>
$$
\begin{align*}<br/>
\lbrace y_{i,j} : 0 \leq i \leq m, j \leq k_i\rbrace = Y<br/>
\end{align*}$$
Since $B$ is atomless, for each $i$ we may write $\pi(x_i) = w_{i,0} + \dots + w_{i,k_i}$ for some $w_{i,0},\dots,w_{i,k_i}$ pairwise disjoint. We note that since $x_i \cdot x_j = 0$, $w_{i,i'} \cdot w_{j,j'} = 0$, so the elements in $\lbrace w_{i,j} : 0 \leq i \leq m, j \leq k_i\rbrace$ are pairwise disjoint. Now define $\pi$ on $\c{a_0,\dots,a_n}$ by stipulating that:<br/>
$$
\begin{align*}<br/>
\pi(y_{i,j}) := w_{i,j}<br/>
\end{align*}$$
and extend to the rest of the elements in the algebra by addition (see the last claim of the proof of <a href="#ex7.21">Exercise 7.21</a>). Then $\pi$ is extends the original $\pi\restrictedto \c{a_0,\dots,a_{n-1}}$ and is a one-to-one Boolean algebra homomorphism (any map defined on atoms then extended to the algebra by addition is a homomorphism).<br/>
<br/>
This completes the "forth" step. The "back" step is similar, except we suppose $\pi^{-1}$ has been defined on $\c{b_0,\dots,b_{n-1}}$, and extend the definition to $\c{b_0,\dots,b_n}$ in the same way. Let $\pi := \bigcup_n \pi\restrictedto \c{a_0,\dots,a_n}$. Then $\pi$ is a Boolean algebra isomorphism from $A$ to $B$ ($\pi$ is one-to-one as each $\pi\restrictedto \c{a_0,\dots,a_n}$ is one-to-one, and it is onto as the "back" step ensures that all elements in $B$ are mapped onto).<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.23"></a><br/>
<h2>Exercise 7.23.</h2>
<i>Solution.</i> We define $\pi : B\restrictedto a \to B/I$ by:<br/>
$$
\begin{align*}<br/>
\pi(u) := [u]<br/>
\end{align*}$$
We shall show that $\pi$ is a Boolean algebra isomorphism. As seen in (7.17) of the book it is seen that $\pi$ is a Boolean algebra homomorphism. Thus, it remains to show that it is one-to-one and onto.<br/>
<br/>
<u>$\pi$ is one-to-one:</u> Suppose $\pi(u) = \pi(v)$, so $[u] = [v]$. Then $(u - v) + (v - u) \in I$, i.e. $(u - v) + (v - u) \leq -a$. But since $u \leq a$, $u - v \leq a$. Thus $u - v \leq a$ and $u - v \leq -a$ implies that $u - v = 0$. Similarly for $v$, we have that $v - u = 0$. Thus $v = u$.<br/>
<br/>
<u>$\pi$ is onto:</u> Fix $[u] \in B/I$. Then $u \cdot a \in B\restrictedto a$. We shall show that $\pi(u \cdot a) = [u]$, i.e. $[u \cdot a] = [u]$. Indeed, we have $u \cdot a - u = 0$ as $u \cdot a \leq u$, and:<br/>
$$
\begin{align*}<br/>
u - u \cdot a &= u \cdot (-(u \cdot a)) \\<br/>
&= u \cdot ((-u) + (-a)) \\<br/>
&= u \cdot (-u) + u \cdot (-a) \\<br/>
&= u \cdot (-a)<br/>
\end{align*}$$
Thus $u \symdiff u \cdot a = u \cdot (-a) \in I$, so $[u \cdot a] = [u]$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.24"></a><br/>
<h2>Exercise 7.24.</h2>
<a name="lem7.24.A"></a><br/>
<b>Lemma 7.24.A.</b> Let $B$ be a Boolean algebra and let $F \subseteq B$ be a filter. Suppose $u \notin F$ and $-u \in F$. Then there exists a filter $G \supseteq F$ such that $u \in G$.<br/>
<br/>
<i>Proof.</i> We first note that for all $w \in F$, $u \cdot w \neq 0$. This is because otherwise, we have that $w \leq -u$ for some $w \in F$, so $-u \in F$ by upward closure, a contradiction. We may thus define:<br/>
$$
\begin{align*}<br/>
G := \lbrace v \in B : (\exists w \in F) \, w \cdot u \leq v\rbrace<br/>
\end{align*}$$
Clearly $G \supseteq F$ as $w \cdot u \leq w$ for all $w \in F$. We shall show that $G$ is a filter.
<ol>
<li> Clearly $1 \in G$. $0 \notin G$ as, as mentioned in the first paragraph above, $w \cdot u \neq 0$ for all $w \in F$.</li>
<li> Let $v_1,v_2 \in G$. Let $w_1,w_2 \in F$ such that $w_1 \cdot u \leq v_1$ and $w_2 \cdot u \leq v_2$. Then $w_1 \cdot w_2 \in F$, and $(w_1 \cdot w_2) \cdot u \leq v_1 \cdot v_2$, so $v_1 \cdot v_2 \in G$.</li>
<li> Clearly $G$ is upward closed.</li></ol>
Finally, since $w \cdot u \leq u$ we have that $u \in G$.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Fix $u \in B - A$. Let $X := \lbrace x \in A : x \geq u\rbrace$ and $Y := \lbrace x \in A : x \geq -u\rbrace$. Observe that if $x \in X$ and $y \in Y$, then $x \cdot y \neq 0$ - otherwise, we have $x \cdot y = 0 \implies x \leq -y \leq u$, so $x = u$, contradicting that $u \notin A$. Thus, $X \cup Y$ satisfies the finite intersection property (FIP), i.e. $\prod W \neq 0$ for all finite $W \subseteq X \cup Y$. By Zorn's Lemma we obtain an ultrafilter $U \supseteq X \cup Y$.<br/>
<br/>
We make an important observation here: For all $x \in U$, if $x \cdot u = 0$ then $x \leq -u$. But this implies that $u \leq -x$, so $-x \in U$ as well, a contradiction. A similar contradiction may be derived if we assume $x \cdot (-u) = 0$. Thus, $x \cdot u \neq 0$ and $x \cdot (-u) \neq 0$ for all $x \in U$.<br/>
<br/>
Now $U$ is a subset of $B$ that satisfies the FIP, so let $U'$ be the filter in $B$ generated by $U$. By the observation in the previous paragraph, we have that $u \notin U'$ and $-u \notin U'$. By \ref{lem7.24.A}, there exists ultrafilters $F,G \supseteq U'$ such that $u \in F$ and $u \notin G$. Futrthermore, $U \subseteq F \cap A$ and $U \subseteq G \cap A$, but both $F \cap A$ and $G \cap A$ are ultrafilters of $A$, so we have $F \cap A = U = G \cap A$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.25"></a><br/>
<h2>Exercise 7.25.</h2>
Let $B$ be an infinite Boolean algebra, $\vert B\vert  = \kappa$. There are at least $\kappa$ ultrafilters on $B$.<br/>
<br/>
\begin{hint}<br/>
Assume otherwise. For each pair $(F,G) \in S \times S$ pick $u \in F - G$, and let these $u$'s generate a subalgebra $A$. Since $\vert A\vert  \leq \vert S\vert  < \kappa$, let $u \in B - A$. Use <a href="#ex7.24">Exercise 7.24</a> to get a contradiction.<br/>
\end{hint}<br/>
<br/>
<a name="lem7.25.A"></a><br/>
<b>Lemma 7.25.A.</b> Let $B$ be a Boolean algebra. Let $X \subseteq B$ be an infinite set, and let $A$ be the subalgebra generated by $X$. Then $\vert X\vert  = \vert A\vert $.<br/>
<br/>
<i>Proof.</i> Clearly $\vert A\vert  \geq \vert X\vert $. Conversely, by repeating the proof of <a href="#ex7.18">Exercise 7.18</a>, we see that there are $\lambda$ many finite partial maps $\pi : Y \to \lbrace -1,0,1\rbrace$, where $\vert X\vert  = \lambda$ and $Y \subseteq X$ is finite. This yields a map of the set of finite sets of such partial maps $\pi$ onto $A$, which is of course of size $\lambda$ as well. Thus $\vert A\vert  \leq \vert X\vert $.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> Let $S$ denote the set of all ultrafilters on $B$. As in the hint, let $A$ denote the subalgebra generated by the an element picked in $F - G$ for each $(F,G) \in S \times S$, $F \neq G$. The subalgebra $A$ is generated by a set $X$ of cardinality $\lambda < \kappa$, so by \ref{lem7.25.A} we have that $\vert A\vert  \leq \vert S \times S\vert  = \vert S\vert $.<br/>
<br/>
Let $u \in B - A$. By <a href="#ex7.24">Exercise 7.24</a>, there exists ultrafilters $F,G$ on $B$ such that $u \in F$, $u \notin G$ and $F \cap A = G \cap A$. Then $F,G \in S$, so there exists some $v \in F - G$ such that $v \in A$ (which is the element picked when generating the subalgebra $A$). This is a contradiction, as $(F - G) \cap A = \emptyset$.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.26"></a><br/>
<h2>Exercise 7.26.</h2>
<i>Solution.</i> It suffices to show that the identity in the hint holds. Assume that all sums in $B$ exist. For $X \subseteq B$, let $v := \sum\lbrace u : u \leq x \text{ for all } x \in X\rbrace$. We observe that if $u \leq x$ for all $x \in X$, then $u \leq v$ by definition. Thus, it remains to show that $v$ is indeed a lower bound.<br/>
<br/>
Suppose not, so there exists some $x \in X$ such that $v - x \neq \emptyset$. Let $w := v \cdot x$. Then we observe that for each $u$ such that $u \leq x$ for all $x \in X$:<br/>
$$
\begin{align*}<br/>
u - w = u - v \cdot x = u \cdot (-(v \cdot x)) = u \cdot (-v) + u \cdot (-x) = 0<br/>
\end{align*}$$
where the last equality holds because $u \leq v$ and $u \leq x$. Then $w < v$ but $w$ is an upper bound of the set $\lbrace u : u \leq x \text{ for all } x \in X\rbrace$, contradicting that $v$ is the least upper bound.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.27"></a><br/>
<h2>Exercise 7.27.</h2>
<a name="ex7.27(i)"></a><br/>
<h3>Exercise 7.27(i).</h3>
<i>Solution.</i>
<ol>
<li> Let $Y := \lbrace a \cdot u : u \in X\rbrace$. Let $v := \sum\lbrace u : u \in X\rbrace$. Then for all $u \in X$, $a \cdot v \geq a \cdot u$, so $a \cdot v$ is an upper bound of $Y$. To see that it is the least upper bound, let $w \in B$ be such that $a \cdot u \leq w$ for all $u \in X$. Then $u = (-a) \cdot u + a \cdot u \leq (-a) \cdot v + w$ for all $u \in X$, and since $v$ is the least upper bound of $X$, we have that $v \leq (-a) \cdot v + w$. Then $a \cdot v \leq a \cdot (-a) \cdot v + a \cdot w = a \cdot w \leq w$, so $a \cdot v$ is the least upper bound.</li>
<li> Let $Y := \lbrace a + u : u \in X\rbrace$. Let $v := \prod\lbrace u : u \in X\rbrace$. Then for all $u \in X$, $a + v \leq a + u$, so $a + v$ is a lower bound of $Y$. To see that it is the greatest lower bound, let $w \in B$ be such that $w \leq a + u$ for all $u \in X$. Then $(-a) \cdot w \leq (-a) \cdot a + (-a) \cdot u = (-a) \cdot u$ for all $u \in X$, so by (1) above we have that $(-a) \cdot w \leq (-a) \cdot v$. Then $w \leq a + w = a + (-a) \cdot w \leq a + (-a) \cdot v = a + v$, so $a + v$ is the greatest lower bound.</li></ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.27(ii)"></a><br/>
<h3>Exercise 7.27(ii).</h3>
<i>Solution.</i> Let $Y := \lbrace -u : u \in X\rbrace$.
<ol>
<li> Let $v := \sum\lbrace u : u \in X\rbrace$. Then since $u \leq v$ for all $u \in X$, $-v \leq -u$ for all $u \in X$ so $v$ is a lower bound. If $w \leq -u$ for all $u \in X$, then $u \leq -w$ for all $u \in X$, so $v \leq -w$ as $v$ is the least upper bound of $X$. Thus $w \leq -v$, so $-v$ is the greatest lower bound of $Y$.</li>
<li> This follows from (1), by replacing $X$ with $Y$.</li></ol><p align="right">$\square$</p><br/>
<br/>
<a name="ex7.28"></a><br/>
<h2>Exercise 7.28.</h2>
<i>Solution.</i> We first note that it suffices to show that if $A \cong A\restrictedto a$ and $a \leq b$, then $A \cong A\restrictedto b$. This is because if $f_1 : A \to B\restrictedto b$ and $f_2 : B \to A\restrictedto a$ are isomorphisms, then $f_2 \circ f_1 : A \to A\restrictedto f_2(b)$ is an isomorphism. Clearly $f_2(b) \leq a$, so assuming the claim above has been proven, there exists an isomorphism $g : A\restrictedto f_2(b) \to A\restrictedto a$. Then $f_2^{-1} \circ g \circ f_2 \circ f_1 : A \to B$ is an isomorphism, as desired.<br/>
<br/>
Let $f : A \to A\restrictedto a$ be an isomorphism, and let $b \geq a$. We define $a_n,b_n \in A$, $b_n \in B$ inductively as follows: $a_0 := 1$, $b_0 := b$, $a_{n+1} := f(a_n)$ and $b_{n+1} := f(b_n)$. Let:<br/>
$$
\begin{align*}<br/>
c := \sum\lbrace a_n - b_n : n < \omega\rbrace, \; c_1 := \sum\lbrace a_n - b_n : 0 < n < \omega\rbrace<br/>
\end{align*}$$
Note that since $a_n \leq a$ for all $n$, we have that $c_1 \leq c \leq a$, and:<br/>
$$
\begin{align*}<br/>
f(c) = \sum_{n < \omega} f(a_n - b_n) = \sum_{n < \omega} a_{n+1} - b_{n+1} = c_1<br/>
\end{align*}$$
We now define $g : A \to A\restrictedto b$ by stipulating that for all $u \in A$:<br/>
$$
\begin{align*}<br/>
g(u) := f(u) \cdot c + u \cdot (-c)<br/>
\end{align*}$$
We shall show that $g : A \to A\restrictedto b$ is an isomorphism. The fact that $g$ respects $+$, $\cdot$ and $-$ follows from simple computation.<br/>
<br/>
<u>$g$ is one-to-one:</u> Let $u,v \in A$ and suppose $g(u) = g(v)$, so $f(u) \cdot c + u \cdot (-c) = f(v) \cdot c + v \cdot (-c)$. Then $g(u) \cdot (-c) = g(v) \cdot (-c) \implies u \cdot (-c) = v \cdot (-c)$. On the other hand, we have $g(u) \cdot c = g(v) \cdot c \implies f(u) \cdot c = g(u) \cdot c$. Since $c_1 \leq c$, this implies that $f(u) \cdot c_1 = f(v) \cdot c_1$. But $c_1 = f(c)$, so we have $f(u \cdot c) = f(v \cdot c)$. Since $f$ is one-to-one we have that $u \cdot c = v \cdot c$. Thus $u = u \cdot c + u \cdot (-c) = v \cdot c + v \cdot (-c) = v$.<br/>
<br/>
<u>$g$ is onto:</u> Let $v \in A$ such that $v \leq b$. We note that since $a_0 - b_0 = 1 - b = -b$, we have that $(a_0 - b_0) \cdot v = 0$, and therefore $v \cdot c = v \cdot c_1$ for all $v \leq b$. Now $v \cdot c_1 \leq c_1 \leq a$, and since $f$ is onto there exists $u \in A$ such that $f(u) = v \cdot c_1$. Then:<br/>
$$
\begin{align*}<br/>
g(u + v \cdot (-c)) &= f(u + v \cdot (-c)) \cdot c + (u + v \cdot (-c)) \cdot (-c) \\<br/>
&= v \cdot c_1 \cdot c + f(v \cdot (-c)) \cdot c_1 + u \cdot (-c) + v \cdot (-c) \\<br/>
&= v \cdot c_1 + f(v \cdot (-c)) \cdot f(c) + u \cdot (-c) + v \cdot (-c) \\<br/>
&= v \cdot c + f(v \cdot (-c) \cdot c) + u \cdot (-c) + v \cdot (-c) \\<br/>
&= v \cdot c + 0 + u \cdot (-c) + v \cdot (-c) \\<br/>
&= v + u \cdot (-c)<br/>
\end{align*}$$
Observe that $f(u) = v \cdot f(c) \leq f(c)$, so $u \leq c$. Thus $u \cdot (-c)$, and therefore:<br/>
$$
\begin{align*}<br/>
g(u + v \cdot (-c)) = v<br/>
\end{align*}$$
as desired.<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.29"></a><br/>
<h2>Exercise 7.29.</h2>
<i>Solution.</i> The hint basically solves the problem. Note that:
<ol>
<li> $v$ is well-defined as if $a \leq u \leq b$, then in particular $a \leq b \implies h(a) \leq h(b)$. Thus $h(a)$ is a lower bound of $\lbrace h(b) : b \in A, u \leq b\rbrace$, vice versa. Of course the sums</li>
<li> By <a href="#ex7.19">Exercise 7.19</a>, to extend $h$ to $A(u)$ it suffices to define $h(a \cdot u + b \cdot (-u)) = h(a) \cdot v + h(b) \cdot (-v)$. The proof that $h$ respects $+$, $\cdot$ and $-$ is similar to the computation in <a href="#ex7.19">Exercise 7.19</a>.</li></ol>
We notice further that if $h$ is a complete homomorphism, then the extension of $h$ is also a complete homomorphism. Indeed, let $X \subseteq A(u)$. For each $x \in X$, suppose $x = a_x \cdot u + b_x \cdot (-u)$. Suppose $w := \sum X$ exists. We observe that $w \cdot u = \sum\lbrace a_x : x \in X\rbrace$. If $w = a \cdot u + b \cdot (-u)$, then $w \cdot u = a \cdot u$.<br/>
$$
\begin{align*}<br/>
h\bb{\sum X} &= h(w) \\<br/>
&= h(a \cdot u + b \cdot (-u)) \\<br/>
&= h(a) \cdot v + h(b) \cdot (-v)<br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.30"></a><br/>
<h2>Exercise 7.30.</h2>
<i>Solution.</i> Let:<br/>
$$
\begin{align*}<br/>
\F := \lbrace f : f \text{ is a homomorphism on some subalgebra $A \subseteq B$ into $C$ extending $h$}\rbrace<br/>
\end{align*}$$
We endow $\F$ with the inclusion partial order. $\F$ is non-empty, as the "identity" map from $\lbrace 0,1\rbrace \subseteq B$ to $\lbrace 0,1\rbrace \subseteq C$ is certainly a Boolean algebra homomorphism. Furthermore, if $C \subseteq \F$ is a chain, then clearly $\bigcup C$ is an upper bound of this chain. To see this, suppose $\lbrace h_\gamma : \gamma < \alpha\rbrace$ is a chain and let $h' := \bigcup_{\gamma<\alpha} h_\gamma$. Let $u,v \in \dom(h)$. Then $u,v \in \dom(h_\gamma)$ for some $\gamma < \alpha$, and $h'\restrictedto\dom(h_\gamma) = h_\gamma$. Since $h_\gamma$ respects $+$, $\cdot$ and $-$ of $u$ and $v$, so does $h$.<br/>
<br/>
By Zorn's Lemma we obtain a maximal element $f \in \F$. Then $\dom(f) = B$ - otherwise, let $u \in B - \dom(f)$. By <a href="#ex7.29">Exercise 7.29</a> it is possible to extend $f$ to a larger homomorphism $f'$ on the subalgebra generated by $\dom(f) \cup \lbrace u\rbrace$, so $f \subsetneq f'$. This contradicts the maximality of $h$.<p align="right">$\square$</p><br/>
<br/>
<br/>
<a name="ex7.32"></a><br/>
<h2>Exercise 7.32.</h2>
<i>Solution.</i> We expand on the hint. In the first case where $\vert B\restrictedto a\vert  = \vert B\vert $, since $B$ is an infinite complete Boolean algebra, by Theorem 7.15 we have $\sat(B)$ is regular uncountable. In particular, there exists a countable partition of $B$, call it $W = \lbrace a_n : n < \omega\rbrace$.<br/>
<br/>
Consider the map $\pi : \prod B\restrictedto a \to B$ defined by:<br/>
$$
\begin{align*}<br/>
\pi(x_0,x_1,\dots) := \sum_{n < \omega} x_n<br/>
\end{align*}$$
Of course this is well-defined as $B$ is complete. Furthermore, this is in fact one-to-one and onto, as if $\pi(x_0,x_1,\dots) = x$ then we have $x_n = a_n \cdot x$ for all $n$. Therefore:<br/>
$$
\begin{align*}<br/>
\vert B\vert  = \prod\lbrace \vert B\restrictedto a\vert  : a \in W\rbrace = \vert B\vert ^{\aleph_0}<br/>
\end{align*}$$
We now address the general case. We first show that the set of all stable $a \in B$ is dense. Let $a \in B$. We consider two cases.
<ol>
<li> Suppose there exists a $b \leq a$ that is atomic. Then the only elements below $b$ are $0$ and $b$ itself, thus $b$ is stable.</li>
<li> Suppose every element below $a$ is not atomic. If no elements below $a$ are stable, then for all $b \leq a$ there exists $c < b$ such that $\vert B\restrictedto c\vert  < \vert B\restrictedto b\vert $. Then there exists a decreasing sequence $a > a_1 > a_2 > \dots$ such that $\vert B\restrictedto a_{n+1}\vert  < \vert B\restrictedto a_n\vert $ for all $n$, which is not possible.</li>
</ol>
Recall that if $D$ is any dense subset of $B$, then a countable partition in $D$ can be constructed as follows: First fix countable partition $W' = \lbrace a_n : n < \omega\rbrace \subseteq B$. For each $n$, let $a_{n,0} \in D$ such that $a_{n,0} \leq a_n$, and let $a_{n,m+1} \in D$ such that $a_{n,m+1} \leq a_n - a_{n,m}$. We have $\lbrace a_{n,m} : n,m < \omega\rbrace \subseteq D$ is a countable partition. Let $W$ be one such partition.<br/>
<br/>
Let $\kappa := \sup\lbrace \vert B\restrictedto a\vert  : a \in W\rbrace$. We see that $\vert B\vert  = \prod\lbrace \vert B\restrictedto a\vert  : a \in W\rbrace = \kappa^{\aleph_0}$, so:<br/>
$$
\begin{align*}<br/>
\vert B\vert ^{\aleph_0} = (\kappa^{\aleph_0})^{\aleph_0} = \kappa^{\aleph_0} = \vert B\vert <br/>
\end{align*}$$
<p align="right">$\square$</p><br/>
<br/>
<a name="ex7.33"></a><br/>
<h2>Exercise 7.33.</h2>
<a name="lem7.33.A"></a><br/>
<b>Lemma 7.33.A.</b> Let $X \subseteq B$. Let $U := \lbrace u \in B : (\exists v \in X) \, v \leq x\rbrace$. Then $U$ is open. Furthermore, if $\sum U$ exists, then so does $\sum X$, and $\sum X = \sum U$.<br/>
<br/>
<i>Proof.</i> $U$ is open as if $v \in U$ and $w \leq v$, then $w \leq v \leq x$ for some $x \in X$ so $w \in U$. To see that $\sum X = \sum U$, we first note that $\sum U$ is indeed an upper bound of $X$ as $X \subseteq U$. Now suppose $v$ is an upper bound of $X$. Then for any $u \in U$, we have $u \leq x \leq v$ for some $x \in X$. Thus, $v$ is an upper bound of $U$. Since $\sum U$ is the least upper bound, $\sum U \leq v$, so $\sum U = \sum X$.<p align="right">$\blacksquare$</p><br/>
<br/>
<i>Solution.</i> By <a href="#lem7.33.A">Lemma 7.33.A</a> and <a href="#ex7.26">Exercise 7.26</a> it suffices to show that supremum exists for all open subsets of $B$. Let $X \subseteq B$ be open, and let $W \subseteq X$ be a maximal subset of $X$ that is an antichain. Since $B$ is $\kappa$-saturated, $\vert W\vert  < \kappa$, and since $B$ is $\kappa$-complete, $\sum W$ exists. Thus, it remains to show that $\sum X = \sum W$.<br/>
<br/>
Write $W := \lbrace w_\alpha : \alpha < \lambda\rbrace$, where $\lambda < \kappa$. Let $x \in X$. Observe that $x = \sum_{\alpha < \lambda} x \cdot w_\alpha$, as if $x > \sum_{\alpha < \lambda} x \cdot w_\alpha$ then $x - \sum_{\alpha < \lambda} w_\alpha \in X$ (as $X$ is open) is non-zero and so $W \cup \ss{x - \sum_{\alpha < \lambda} w_\alpha}$ is a strictly larger antichain, contradicting maximality. Thus:<br/>
$$
\begin{align*}<br/>
x = \sum_{\alpha < \lambda} x \cdot w_\alpha \leq \sum_{\alpha < \lambda} w_\alpha = \sum W<br/>
\end{align*}$$
Thus $\sum W$ is an upper bound of $X$. Let $v$ be an upper bound of $X$. Then since $W \subseteq X$ in particular $v$ is an upper bound of $W$. Thus $\sum W \leq v$ as $\sum W$ is the least upper bound of $W$. Therefore $\sum W = \sum X$.<p align="right">$\square$</p>
</body>