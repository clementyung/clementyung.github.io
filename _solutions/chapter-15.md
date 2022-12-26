---
title: "15) Applications of Forcing
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-15
excerpt: ""
---

{ % include commands.html % }

<a name="ex15.1"></a>
## Exercise 15.1.
<i>Solution.</i> We note that in the proof of Theorem  7.13, the cuts $U$ in $B(P)$ are exactly:

$$
\begin{align*}
U = \sum\lbrace p \in P : p \in U\rbrace
\end{align*}
$$

We may then reduce the summand to an antichain in $P$. Since $P$ is $\kappa$-cc, every antichain is of length $<\kappa$. For each $\lambda < \kappa$, there are at most $\vert P\vert ^\lambda$ many possible antichains of length $\lambda$. Thus:

$$
\begin{align*}
\vert B(P)\vert  &\leq \mod{\ss{\sum W : W \subseteq P \text{ is an antichain}}} \\
&= \bigcup_{\lambda < \kappa} \mod{\ss{\sum W : W \subseteq P \text{ is an antichain of length $\lambda$}}} \\
&\leq \bigcup_{\lambda < \kappa} \vert P\vert ^\lambda \\
&= \vert P\vert ^{<\kappa}
\end{align*}
$$
 
$\square$

<a name="ex15.2"></a>
## Exercise 15.2.
<i>Solution.</i> For any $p \in P$, let $\lambda = \sup\dom(p)$. Since $\kappa$ is regular and $\vert \dom(p)\vert  < \kappa$, $\lambda < \kappa$. Define $q : \lambda \to \lbrace 0,1\rbrace$ by:

$$
\begin{align*}
q(\alpha) =
\begin{cases}
p(\alpha), &\text{if $\alpha \in \dom(p)$} \\
0, &\text{otherwise} \\
\end{cases}
\end{align*}
$$

Clearly $q \leq p$ and $q \in Q$, so $Q$ is dense in $P$. 
$\square$

<a name="ex15.3"></a>
## Exercise 15.3.
<i>Solution.</i> We modify the hint for singular cardinals in general. Fix a singular cardinal $\kappa$, along with the added subset $X \subseteq \kappa$ (so $\bigcup G$ is the characteristic function of $X$). Also, fix a cofinal sequence of cardinals $\c{\lambda_\gamma : \gamma < \cf(\kappa)}$, and we may assume every $\lambda_\gamma$ is regular (otherwise just take the successor cardinal). Define $g : \kappa \to \cf(\kappa)$ (as sets) by:

$$
\begin{align*}
g(\alpha) := \min\lbrace \gamma < \cf(\kappa) : \otp(X \cap (\lambda_{\gamma+1} - \lambda_\gamma)) = \lambda_\gamma + \alpha\rbrace
\end{align*}
$$

<b>Claim.</b>. For all ordinals $\alpha < \kappa$ and $p \in P$, there exists a $q \leq p$ ($q \supseteq p$) such that there is a $\gamma < \cf(\kappa)$ in which $\lambda_{\gamma+1} - \lambda_\gamma \subseteq \dom(q)$, and:

$$
\begin{align*}
\otp(\lbrace \xi \in \lambda_{\gamma+1} - \lambda_\gamma : q(\xi) = 1\rbrace) = \lambda_\gamma + \alpha
\end{align*}
$$

In other words, the set:

$$
\begin{align*}
D_\alpha &:= \lbrace p \in P : \exists \gamma < \cf(\kappa)[\lambda_{\gamma+1} - \lambda_\gamma \subseteq \dom(p) \\
&\eqbreak \wedge \otp(\lbrace \xi \in \lambda_{\gamma+1} - \lambda_\gamma : q(\xi) = 1\rbrace) = \lambda_\gamma + \alpha]\rbrace
\end{align*}
$$

is dense in $P$.

This proves the result, as the genericity of $G$ implies that for all $\alpha$ there is a $q \in D_\alpha$ such that $q \subseteq f = \bigcup G$. Thus, for every $\alpha < \kappa$ there is a $\gamma < \cf(\kappa)$ such that $\otp(\lbrace \xi \in \lambda_{\gamma+1} - \lambda_\gamma : f(\xi) = 1\rbrace) = \lambda_\gamma + \alpha$. Then, in $V[G]$ $g$ is a well-defined injective map from $\kappa$ to $\cf(\kappa)$ (as sets).

<i>Proof.</i> We work in $V$. Fix $p \in P$, and let $p_\gamma := p\restrictedto(\lambda_{\gamma+1} - \lambda_\gamma)$. Then there exists a $\gamma$ such that $\vert \dom(p_\gamma)\vert  < \lambda_\gamma$, for otherwise we have:

$$
\begin{align*}
\vert \dom(p)\vert  = \sum_{\gamma < \cf(\kappa)} \vert \dom(p_\gamma)\vert  = \sum_{\gamma < \cf(\kappa)} \lambda_\gamma = \kappa
\end{align*}
$$

contradicting that $\vert \dom(p)\vert  < \kappa$. With this $\gamma$, we have that $\dom(p_\gamma) \subseteq \lambda_{\gamma+1} - \lambda_\gamma$ is bounded as $\lambda_{\gamma+1}$ is regular. We may then define $q_\gamma$ (on the domain $\lambda_{\gamma+1} - \lambda_\gamma$) by extending $p_\gamma$ such that $q_\gamma(\xi) = 1$ for the enough ordinals above $\sup{\dom(p_\gamma)}$, followed by $q_\gamma(\xi) = 0$ for the remaining ordinals, such that $\otp(\lbrace \xi \in \lambda_{\gamma+1} - \lambda_\gamma : q(\xi) = 1\rbrace) = \lambda_n + \alpha$. Then let $q := \bigsqcup_{\delta \neq \gamma} p_\gamma \sqcup q_\gamma$, and we have that $q \supseteq p$ has the desired property. 
$\blacksquare$ 
$\square$

<a name="ex15.4"></a>
## Exercise 15.4.
<i>Solution.</i> The proof of <a href="#ex15.3">Exercise 15.3</a> may be repeated. Note that for the proof of the claim, we have furthermore that $p_\gamma = \emptyset$ for some $\gamma$ large enough. 
$\square$

<a name="ex15.5"></a>
## Exercise 15.5.
<i>Solution.</i> We will provide a solution that does not use the hint. We shall show that:

$$
\begin{align*}
W := \ss{\prod_{\alpha < \kappa} f(\alpha) : f \in \prod_{\alpha < \kappa} W_\alpha}
\end{align*}
$$

is a partition which is a common refinement of $\c{W_\alpha : \alpha < \kappa}$.

<u>Antichain:</u> Let $f,g \in \prod_{\alpha < \kappa} W_\alpha$ such that $f \neq g$. Then $f(\alpha) \neq g(\alpha)$ for some $\alpha$. Since $f(\alpha),g(\alpha) \in W_\alpha$ and $W_\alpha$ is an antichain, $f(\alpha) \cdot g(\alpha) = 0$. Thus $\bb{\prod_{\alpha < \kappa} f(\alpha)} \cdot \bb{\prod_{\alpha < \kappa} g(\alpha)} = 0$.

<u>$\sum W = 1$:</u> Let $w := \sum W$. It suffices to show that for all $u \neq 0$, $u \cdot w \neq 0$. Indeed, fix $u \in B$ and let $G$ be a generic filter such that $u \in G$. Let $W_\alpha' := \lbrace -u\rbrace \cup (\lbrace u \cdot w_\alpha : w \in W_\alpha\rbrace - \lbrace 0\rbrace)$. Then $W_\alpha'$ is a partition, and since $G$ is generic, $G \cap W' \neq \emptyset$. Of course $-u \notin G$, so we have that $u_\alpha := u \cdot w_\alpha \in G$ for some $w_\alpha \in W_\alpha$. We let $f : \kappa \to V$ be defined by $f(\alpha) := u_\alpha$. By the premise, $f \in V$. Since $G$ is generic, we have that $v := \prod_{\alpha<\kappa} f(\alpha) \in G$. Then $u \cdot v = v \neq 0$, and clearly $v \in W$.

<u>$W \leq W_\alpha$ for all $\alpha$:</u> For all $f \in \prod_{\alpha<\kappa}$, $\prod_{\alpha<\kappa} f(\alpha) \leq f(\alpha) \in W_\alpha$. 
$\square$

<a name="ex15.6"></a>
## Exercise 15.6.
<i>Solution.</i> This is a special case of <a href="#ex15.9">Exercise 15.9</a>. 
$\square$

<a name="ex15.7"></a>
## Exercise 15.7.
<i>Solution.</i> This is a special case of <a href="#lem15.9.A">Lemma 15.9.A</a>. 
$\square$

<a name="ex15.8"></a>
## Exercise 15.8.
<i>Solution.</i> Let $G \subseteq P$ be a filter (generic or not).  Let:

$$
\begin{align*}
D := \lbrace (p_1,p_2) \in P \times P : p_1 \perp p_2\rbrace
\end{align*}
$$

We see that $D$ is dense in $P \times P$ - indeed, let $(p_1,p_2) \in P$. Let $q_i,r_i \leq p_i$ be incompatible. If $q_1 \perp q_2$, then $(q_1,q_2) \leq (p_1,p_2)$ and $(q_1,q_2) \in D$. Otherwise, we must have $r_1 \perp q_2$, so again $(r_1,q_2) \leq (p_1,p_2)$ and $(r_1,q_2) \in D$. But observe that $(G \times G) \cap D = \emptyset$, as if $(p_1,p_2) \in G \times G$ then $p_1$ and $p_2$ must be compatible (by compatibility condition of filters). 
$\square$

<a name="ex15.9"></a>
## Exercise 15.9.
<a name="lem15.9.A"></a>
<b>Lemma 15.9.A.</b> If $P = \prod_i P_i$, then $B(P)$ is the completion of the direct sum of the algebras $B(P_i)$.

<i>Proof.</i> It suffices to show that $\prod_i B(P_i)$ embeds into $B(P)$ - indeed, from that since $B(P)$ is a complete algebra and $\prod_i P_i$ embeds densely into $B(P)$, then so does $\prod_i B(P_i)$. By the uniqueness of completion of Boolean algebras, $B\bb{\prod_i B(P_i)} = B(P)$.

We follow the construction of $B(P)$ in Theorem 7.13. Let $U \in \prod_i B(P_i)$, so $U = \prod_i U_i$, where $U_i$ is a regular cut in $P_i$, and $U_i \neq P_i$ on finitely many $i \in I$. We shall show that $U$ is a regular cut in $P$. Indeed, let $p = (p_i)_{i \in I} \notin U$. Then $p_i \notin U_i$ for some $i \in I$. Since $U_i$ is regular, there exists $p_i' \leq p_i$ such that $U_{p_i'} \cap U_i = \emptyset$. For $j \neq i$, let $p_j' := p_j$. Let $p' := (p_i')_{i \in I}$. Then $U_{p'} = \prod_i U_{p_i'}$ and $U_{p'} \cap U = \emptyset$, so $U$ is regular. 
$\blacksquare$

<i>Solution.</i> By <a href="#lem15.9.A">Lemma 15.9.A</a>, we have:

$$
\begin{align*}
B(P) = B\bb{\prod_i P_i} = B\bb{\prod_i B(P_i)} = B\bb{\prod_i B(Q_i)} = B\bb{\prod_i Q_i} = B(Q)
\end{align*}
$$
 
$\square$

<a name="ex15.10"></a>
## Exercise 15.10.
<i>Solution.</i> For $\alpha < \kappa$ let each $P_\alpha$ be notion of forcing (14.2) adding a single Cohen real (for $\alpha \neq \beta$, $P_\alpha = P_\beta$). Define $F : \prod_\alpha P_\alpha \to P$ such that for $p_\alpha \in P_\alpha$, we have:

$$
\begin{align*}
F\bb{(p_\alpha)_{\alpha < \kappa}}(\beta,n) := p_\beta(n)
\end{align*}
$$

Clearly for all $p \in \prod_\alpha \to P$, $\ran(p) \subseteq \lbrace 0,1\rbrace$. Furthermore, $\dom(p)$ is finite as $\prod_\alpha P_\alpha$ is of finite support, so all but finitely many $\alpha$'s are such that $p_\alpha = \emptyset$.

$F$ is invertible, with the inverse $p \mapsto \prod_\alpha p(\alpha,-)$ (which is well-defined as $\dom(p)$ is finite). Finally, if $p,q \in \prod_\alpha P_\alpha$ and $p \leq q$, then $p_\alpha \supseteq q_\alpha$ for all $\alpha$, so $F(p) \supseteq F(q)$. 
$\square$

<a name="ex15.11"></a>
## Exercise 15.11.
<i>Solution.</i> Let $A \subseteq P \times Q$ be an antichain. Let $B := \lbrace q \in Q : (\exists p \in P) \, (p,q) \in A\rbrace$. We consider two cases.
<ol>
<li> Suppose $B$ is countable. For each $q \in B$, let $A_q := \lbrace p \in P : (p,q) \in A\rbrace$. Since $A$ is an antichain, for two conditions $(p,q)$, $(p',q)$ in $A_q$, $(p,q) \perp (p',q)$ so $p \perp p'$. Thus $A_q \subseteq P$ is an antichain. Since $P$ satisfies c.c.c., $A_q$ must be countable. Thus $A = \bigcup_{q \in B} A_q \times \lbrace q\rbrace$ is countable..</li>
<li> Suppose $B$ is uncountable. Since $Q$ has property (K), there exists an uncountable $B' \subseteq B$ such that elements in $B'$ are pairwise compatible. Now for $q_1,q_2 \in B'$, if $(p_1,q_1) \in A$ and $(p_2,q_2) \in A$ then we must have $p_1 \perp p_2$, for other wise $(p_1,q_1) \not\perp (p_2,q_2)$. This implies that $A' := \lbrace p \in P : (\exists q \in B') \, (p,q) \in A\rbrace$ is an uncountable antichain, contradicting that $P$ satisfies c.c.c.</li>
</ol>
Thus $P \times Q$ satisfies c.c.c. 
$\square$

<a name="ex15.12"></a>
## Exercise 15.12.
<i>Solution.</i> We elaborate on each identity used in the hint. Suppose $V[G] \models 2^{\cf(\kappa)} < \kappa$, i.e. $F(\cf(\kappa)) < \kappa$.
<ol>
<li> $(\kappa^{\cf(\kappa)})^{V[G]} = (\kappa^{\cf(\kappa)})^N$ follows from Lemma 15.19..</li>
<li> $(\kappa^{\cf(\kappa)})^N \leq (2^\kappa)^N$ follows from simple cardinal arithmetic: $\kappa^{\cf(\kappa)} \leq (2^\kappa)^{\cf(\kappa)} = 2^{\kappa \cdot \cf(\kappa)} = 2^\kappa$.</li>

<li> $(2^\kappa)^N \leq \vert B(P^{\leq\cf(\kappa)})\vert ^\kappa$ follows from Lemma 15.1..</li>
<li> To show that $\vert B(P^{\leq\cf(\kappa)})\vert ^\kappa = (F(\cf(\kappa)))^\kappa$, we first show that $\vert P^{\leq\cf(\kappa)}\vert  = F(\cf(\kappa))$. Given $\alpha < \cf(\kappa)$, we have $((\alpha,0,0),0) \in P^{\leq\cf(\kappa)}$, so we have that $\vert P^{\leq\cf(\kappa)}\vert  \geq F(\cf(\kappa))$. On the other hand, we have:

$$
\begin{align*}
\vert P^{\leq\cf(\kappa)}\vert  &\leq \vert \lbrace (\lambda,\alpha,\beta,n) : \lambda \leq \cf(\kappa), \alpha < \lambda, \beta < F(\lambda), n \in \lbrace 0,1\rbrace\vert  \\
&\leq \sup_{\lambda < \cf(\kappa)} \lambda \cdot \lambda \cdot F(\lambda) \cdot 2 \\
&= \sup_{\lambda < \cf(\kappa)} F(\lambda) \\
&\leq F(\cf(\kappa))
\end{align*}
$$

Thus $\vert P^{\leq\cf(\kappa)}\vert  = F(\cf(\kappa))$. By <a href="#ex15.1">Exercise 15.1</a>, since $P^{\leq\cf(\kappa)}$ satisfies the $(\cf(\kappa))^+$-chain condition, we have that:

$$
\begin{align*}
\vert B(P^{\leq\cf{\kappa}})\vert  \leq \vert P^{\leq\cf(\kappa)}\vert ^{<(\cf(\kappa))^+} = \vert P^{\leq\cf(\kappa)}\vert ^{\cf(\kappa)}
\end{align*}
$$

Thus:

$$
\begin{align*}
\vert P^{\leq\cf(\kappa)}\vert ^\kappa \leq \vert B(P^{\leq\cf(\kappa)})\vert ^\kappa \leq (\vert P^{\leq\cf(\kappa)}\vert ^{\cf(\kappa)})^\kappa = \vert P^{\leq\cf(\kappa)}\vert ^\kappa
\end{align*}
$$

so $\vert B(P^{\leq\cf(\kappa)})\vert ^\kappa = (F(\cf(\kappa)))^\kappa$.</li>

<li> Since $F(\cf(\kappa)) < \kappa$, we have that $(F(\cf(\kappa)))^\kappa = 2^\kappa = \kappa^+$, since the ground model satisfies $\GCH$..</li>
<li> Finally, we have that $\kappa^+ = (\kappa^+)^{V[G]}$ as all cardinals and cofinalities are preserved.</li>
</ol> 
$\square$

<a name="ex15.13"></a>
## Exercise 15.13.
<i>Solution.</i> Let $P$ denote the forcing notion (15.18). As explained in the paragraph below (15.18), in $V[G]$ we have that $f$ is a function on $\aleph_1$ onto $\aleph_\omega$. Note that the $-$ here denotes set exclusion, so $\alpha + \omega - \alpha = \lbrace \alpha + n : n \in \omega\rbrace$.

<b>Claim.</b>. There exists an ordinal $\alpha$ such that $f"(\alpha + \omega - \alpha) = X$.

<i>Proof.</i> Let $P$ denote the forcing notion (15.18). Let:

$$
\begin{align*}
D := \lbrace p \in P : (\exists \alpha \in \omega_1)(\alpha + \omega - \alpha \subseteq \dom(p) \wedge p"(\alpha + \omega - \alpha) = X)\rbrace
\end{align*}
$$

We shall show that $D$ is dense in $P$. Indeed, let $p \in P$. Since $\dom(p)$ is countable and $\aleph_1$ is regular, there exists a limit ordinal $\alpha > \sup{\dom(p)}$. Since $P$ is $\aleph_0$-closed, no countable subsets of $\aleph_\omega$ is added. Thus, in $V$ there exists a one-to-one $h$ on $\omega$ onto $X$. Thus, let:

$$
\begin{align*}
q := p \cup \lbrace (\alpha + n,h(n)) : n \in \omega\rbrace
\end{align*}
$$

Then clearly $q \leq p$ and $q \in D$, as desired. Since $G$ is generic, $G \cap D \neq \emptyset$. So $f = \bigcup G$ must have some $\alpha$ such that $f"(\alpha + \omega - \alpha) = X$. 
$\blacksquare$

Thus, the function $g$ is the hint is well-defined in $V[G]$. Clearly it is one-to-one. 
$\square$

<a name="ex15.14"></a>
## Exercise 15.14.
<i>Solution.</i> Since $\kappa = \beth_\alpha^+$ is regular, $P_\alpha$ is $\beth_\alpha$-closed (see proof of Lemma 15.21). Furthermore, we note that:

$$
\begin{align*}
\lambda^{<\kappa} = \beth_{\alpha+1}^{\beth_\alpha} = (2^{\beth_\alpha})^{\beth_\alpha} = 2^{\beth_\alpha} = \beth_{\alpha+1} = \lambda
\end{align*}
$$

so by Lemma 15.21, $\vert P_\alpha\vert  = \beth_{\alpha+1}$ and therefore the $\beth_{\alpha+1}^+$-chain condition is satisfied. Let $P$ be the Easton product of the $P_\alpha$'s, so direct limit is taken at inaccessible cardinal stages.

<b>Claim.</b>. $P^{\leq\alpha}$ satisfies the $\beth_{\alpha+1}^+$-chain condition. If $\beth_\alpha$ is regular, then $P^{<\alpha}$ satisfies the $\beth_\alpha^+$-chain condition.

<i>Proof.</i> We have:

$$
\begin{align*}
\vert P^{\leq\alpha}\vert  = \prod_{\beta \leq \alpha} \vert P_\beta\vert  = \prod_{\beta \leq \alpha} \beth_\beta = \beth_\alpha^{\vert \alpha\vert } \leq (2^{\beth_\alpha})^{\vert \alpha\vert } = \beth_{\alpha+1}
\end{align*}
$$

so $P^{\leq\alpha}$ satisfies the $\beth_{\alpha+1}^+$-chain condition.

If $\beth_\alpha$ is regular then either $\alpha$ is a successor ordinal, or $\beth_\alpha = \alpha$ is inaccessible. If $\alpha = \beta + 1$, then $P^{<\alpha} = P^{\leq\beta}$ so it satisfies $\beth_\alpha^+$-chain condition by above. If $\alpha$ is inaccessible, then since direct limit is taken at stage $\alpha$ (i.e. $\vert s(p) \cap \alpha\vert  < \alpha$ for every $p \in P^{<\alpha}$), we have that:

$$
\begin{align*}
\vert P^{<\alpha}\vert  \leq \sum_{\beta<\alpha} \prod_{\gamma\leq\beta} \vert P^{\leq\gamma}\vert  = \sum_{\beta<\alpha} \beth_\beta^{\vert \beta\vert } \leq \sum_{\beta<\alpha} \beth_{\beta+1} = \beth_\alpha
\end{align*}
$$

On the other hand, clearly $\vert P^{<\alpha}\vert  \geq \vert P^{\leq\beta}\vert  = \beth_\beta$ for $\beta < \alpha$, so $\vert P^{<\alpha}\vert  = \beth_\alpha$. Therefore $P^{<\alpha}$ satisfies the $\beth_\alpha^+$-chain condition. 
$\blacksquare$

<b>Claim.</b>. $P^{\geq\alpha}$ is $\beth_\alpha$-closed. In particular, $P^{>\alpha}$ is $\beth_{\alpha+1}$-closed.

<i>Proof.</i> The proof is the same as that of $P^{\geq\lambda}$ for Easton forcing: If $C \subseteq P^{>\alpha}$ has pairwise compatible elements and $\vert C\vert  \leq \beth_\alpha$, then $p := \bigcup C$ is a condition in $P^{\geq\alpha}$. (15.10) is preserved for all regular $\gamma \geq \beth_\alpha$ and holds trivially for $\gamma < \beth_\alpha$. 
$\blacksquare$

We now show that for each ordinal $\alpha$, $\aleph_\alpha^{V[G]} = \beth_\alpha$, and $V[G] \models 2^{\aleph_\alpha} = \aleph_{\alpha+1}$.

<u>$\beth_\alpha^+$ is a cardinal in $V[G]$:</u> First assume that $\beth_\alpha$ is regular. Suppose $\beth_\alpha^+$ is not a cardinal in $V[G]$. There exists a function $f \in V[G]$ that is a function on $\beth_\alpha$ onto $\beth_\alpha^+$. By above, we may decompose $V[G] = V[G^{<\alpha} \times G^{\geq\alpha}]$, and we have that $P^{<\alpha}$ satisfies the $\beth_\alpha^+$-chain condition, and $P^{\geq\alpha}$ is $\beth_\alpha$-closed. By Lemma 15.19, we have that $f \in V[G^{<\alpha}]$, so in $V[G^{<\alpha}]$ we have that $\beth_\alpha^+$ is not a cardinal. This is a contradiction, as $\beth_\alpha^+$ is regular and $P^{<\alpha}$ satisfies $\beth_\alpha^+$-chain condition by the above claim, so $\beth_\alpha^+$ is preserved (by Theorem 15.3).

Now suppose that $\beth_\alpha$ is a singular limit cardinal, so $\alpha$ is a singular limit ordinal. Assume for a contradiction that $\beth_\alpha^+$ is not a cardinal in $V[G]$, so again we obtain a function $f \in V[G]$ on $\beth_\alpha$ onto $\beth_\alpha^+$. Now $\vert \beth_\alpha^+\vert ^{V[G]}$ is a cardinal in the ground model $V$ (as the property of cardinal is downward absolute), and we see that $\vert \beth_\alpha^+\vert ^{V[G]} = \vert \beth_\alpha\vert ^{V[G]} \leq \beth_\alpha$ in $V$. On the other hand,

Let $g : \cf(\alpha) \to \beth_\alpha$ be onto (note that $g \in V \subseteq V[G]$, in particular $V[G]$ witnesses that $\beth_\alpha$ is a singular limit ordinal). Consider the onto function $f \circ g : \cf(\alpha) \to \beth_\alpha^+$. Then by Lemma 15.19 again, we have that in fact $g \circ f \in V[G^{\leq\cf(\alpha)}]$

% <u>$\vert \beth_\alpha\vert ^{V[G]} = \aleph_\alpha^{V[G]}$:</u> We induct on $\alpha$. For $\alpha = 0$, this follows from the absoluteness of $\beth_0 = \aleph_0$. For $\alpha$ limit, we simply take supremum on both sides, so it remains to show the successor case.

% Suppose $\vert \beth_\alpha\vert ^{V[G]} = \aleph_\alpha^{V[G]}$. Since $\beth_\alpha^+$ is a cardinal in $V[G]$ and $\beth_\alpha < \beth_\alpha^+$, we have that $\vert \beth_\alpha^+\vert ^{V[G]} > \vert \beth_\alpha\vert ^{V[G]} = \aleph_\alpha^{V[G]}$, so $\vert \beth_\alpha^+\vert ^{V[G]} \geq \aleph_{\alpha+1}^{V[G]}$. On the other hand, let $\kappa < \vert \beth_\alpha^+\vert ^{V[G]}$. Then $\kappa < \beth_\alpha^+$ (as $\vert \beth_\alpha^+\vert ^{V[G]} \leq \beth_\alpha^+$), and since $\kappa$ is a cardinal in the ground model (as "$\kappa$ is a cardinal" is downward absolute), we have that $\kappa \leq \beth_\alpha$. Therefore $\kappa \leq \vert \beth_\alpha\vert ^{V[G]} = \aleph_\alpha^{V[G]}$, so $\vert \beth_\alpha^+\vert ^{V[G]} = \aleph_{\alpha+1}^{V[G]}$

% Note that $V[G] = V[G^{<\alpha}][G^\alpha][G^{>\alpha}]$. Since $P^{>\alpha}$ is $\beth_{\alpha+1}$-closed, we have that $\vert \beth_\alpha^+\vert $
 
$\square$

<a name="ex15.16"></a>
## Exercise 15.16.
<i>Solution.</i> The first hint leads to a solution, but the second only explains why $P$ "does the job of $Q$". The proof of second hint has working very similar to <a href="#ex15.13">Exercise 15.13</a>, so in this solution we expand on the first hint only.

To see that $Q'$ in the first hint is dense, let $q \in Q$. Define $q'$ such that for $\alpha < \sup{\dom(q)}$:

$$
\begin{align*}
q'(\alpha) :=
\begin{cases}
q(\alpha), &\text{if $\alpha \in \dom(q)$} \\
0, &\text{if $\alpha \notin \dom(q)$} \\
\end{cases}
\end{align*}
$$

Clearly $q' \in Q$, and $\dom(q') = \sup{\dom(q)}$, an initial segment of $\omega_1$. Let $P'$ be the set of all $p \in P$ such that $\dom(p)$ is a limit ordinal. By a similar reasoning as above, $P'$ is indeed dense in $P$. We shall recursively construct an isomorphism $\pi : Q' \to P'$, where $P' \subseteq P$ is dense.

Start by fixing an one-to-one and onto enumeration $h : 2^{\aleph_0} \to \lbrace 0,1\rbrace^\omega$. Let $\pi(\emptyset) := \emptyset$. Now suppose $\pi(q)$ is defined for all $\dom(q) = \alpha$. Let $q \in Q'$ such that $\dom(q) = \alpha + 1$. Define:

$$
\begin{align*}
\pi(q) := \pi(q\restrictedto\alpha) \cup \lbrace (\dom(\pi(q\restrictedto\alpha)) + n, h(q(\alpha))(n)) : n \in \omega\rbrace
\end{align*}
$$

Then $\dom(\pi(q))$ is a partial function into $\lbrace 0,1\rbrace$ (as $h(q(\alpha))(n) \in \lbrace 0,1\rbrace$ for all $n$) with domain $\dom(\pi(q\restrictedto\alpha)) + \omega$, which is a limit ordinal. Thus we indeed have $\pi(q) \in P'$. Finally, if $\alpha$ is a limit ordinal, we define $\pi(q) := \bigcup_{\beta<\alpha} \pi(q\restrictedto\alpha)$. Again, $\dom(\pi(q))$ is clearly a limit ordinal.

We now show that $\pi$ is an isomorphism.

<u>$\pi$ respects $<$:</u> From the construction of $\pi$, it's easy to see that if $q_1 \subseteq q_2$ then $\pi(q_1) \subseteq \pi(q_2)$. Thus $q_1 < q_2 \implies \pi(q_1) < \pi(q_2)$. On the other hand, suppose $q_1 \perp q_2$. Let $\alpha$ be the least ordinal such that $q_1(\alpha) \neq q_2(\alpha)$. Let $q := q_1\restrictedto\alpha = q_2\restrictedto\alpha$. Since $h$ is one-to-one, there exists an $n$ such that $h(q_1(\alpha))(n) \neq h(q_2(\alpha))(n)$, so $\pi(q_1\restrictedto(\alpha+1)) \perp \pi(q_2\restrictedto(\alpha+1))$. Since $\pi$ respects $<$, we have that $\pi(q_1) \perp \pi(q_2)$.

<u>$\pi$ is one-to-one:</u> It's also easy to see from the construction that $q_1 \subsetneq q_2 \implies \pi(q_1) \subsetneq \pi(q_2)$, so $\pi$ is one-to-one.

<u>$\pi$ is onto:</u> Let $\alpha$ be a limit ordinal below $\omega_1$. Let $p \in P$ such that $\dom(p) = \alpha$. We induct on $\alpha$. Base case $\alpha = 0$ is clear. If $\alpha = \beta + \omega$ for some limit ordinal $\beta$, then by induction hypothesis there exists some $q \in Q'$ such that $\pi(q) = p\restrictedto\beta$. One may check that:

$$
\begin{align*}
p = \pi(q \cup \lbrace \dom(q)+1,h^{-1}(\lbrace p(\beta+n) : n \in \omega\rbrace)\rbrace)
\end{align*}
$$

If $\alpha \neq \beta + \omega$ for all ordinals $\beta$, then:

$$
\begin{align*}
p = \bigcup_{\substack{\beta < \alpha \\ \beta \text{ is limit}}} p\restrictedto(\beta + \omega)
\end{align*}
$$

so if $\pi(q_\beta) = p\restrictedto(\beta + \omega)$, then let $q := \bigcup_{\beta<\alpha} q_\beta$ and we have that $\pi(q) = p$. 
$\square$

<a name="ex15.17"></a>
## Exercise 15.17.
<i>Solution.</i> Call a tree $T$ an <b>$\alpha$-tree</b> if it is a countable normal tree (as in (15.20)) such that $\height(T) = \alpha$. Let $Q' := \lbrace T \in Q : \height(Q) \text{ is a limit ordinal}\rbrace$, and clearly it is dense in $Q$. Let $R$ be the notion of forcing that collapses $2^{\aleph_0}$ to $\aleph_1$, and let $R' \subseteq R$ be the set of all $r \in R$ such that $\dom(r)$ is an initial segment of $\omega_1$. We shall show that $R'$ and $Q'$ are isomorphic, so by <a href="#ex15.16">Exercise 15.16</a> we have that $B(P) = B(R) = B(Q)$.

<b>Claim.</b>. Let $\alpha$ be a limit ordinal, and let $T$ be an $\alpha$-tree. Then there are exactly $2^{\aleph_0}$ many $(\alpha + \omega)$-trees $T'$ such that $T' < T$.

<i>Proof.</i> Fix an $\alpha$-tree $T$. Note that by (iii) of (15.20), if $T'$ is an $(\alpha + \omega)$-tree and $T' < T$, then $T$ is completely determined by its $\alpha^\text{th}$ level. Thus, it suffices to determine the cardinality of possible $\alpha^\text{th}$ levels of $T'$.

Since $\alpha$ is countable, there are $2^{\aleph_0}$ many functions $t : \alpha \to \omega$.  The $(\alpha + 1)^\text{th}$ level is a countable set of functions $t : \alpha \to \omega$, so there are at most $(2^{\aleph_0})^{\aleph_0} = 2^{\aleph_0}$ many such countable sets.

Conversely, by Lemma 9.21 there exists an almost disjoint family $A$ of functions $t : \alpha \to \omega$ (i.e. for $t_1,t_2 \in A$, $\lbrace \beta : t_1(\beta) = t_2(\beta)\rbrace$ is finite) of size $2^{\aleph_0}$. For each $t \in A$, we define a $(\alpha + 1)^\text{th}$ level $L_\alpha^{(t)}$ by stipulating that:

$$
\begin{align*}
L_\alpha^{(t)} := \lbrace t' \cup t\restrictedto(\alpha - \dom(t')) : t' \in T\rbrace
\end{align*}
$$

Note that since $T$ is countable, so is $L_\alpha^{(t)}$. Let $T_t < T$ be the $(\alpha + \omega)$-tree such that the $\alpha^\text{th}$ level of $T'$ is $L_\alpha^{(t)}$. Then clearly if $t_1,t_2 \in A$ and $t_1 \neq t_2$, then $T_{t_1} \neq T_{t_2}$. Thus we constructed $2^{\aleph_0}$ different many $(\alpha + \omega)$-trees stronger than $T$. 
$\blacksquare$

Let $A$ be the set of almost disjoint family in the claim above, and let $h : 2^{\aleph_0} \to A$ be one-to-one and onto. We may define an isomorphism $\pi : R' \to Q'$ recursively, like in <a href="#ex15.16">Exercise 15.16</a>, as follows: Let $\pi(\emptyset) = \lbrace \emptyset\rbrace$. If $\pi(q) = T$, we let $\pi(q \cup \lbrace \alpha\rbrace) := T_{h(\alpha)}$, where $T_{h(\alpha)}$ as defined in the claim above. Finally, if $\dom(q)$ is a limit ordinal, we let $\pi(q) := \bigcup_{\beta < \dom(q)} \pi(q\restrictedto \beta)$. One may proceed along <a href="#ex15.16">Exercise 15.16</a> to show that $\pi$ is indeed an isomorphism. 
$\square$

<a name="ex15.18"></a>
## Exercise 15.18.
<i>Solution.</i> As in the hint, if $\pi$ is a non-trivial automorphism of $T$ and $\pi$ is extended to an automorphism of $T' < T$, $\height(T') = \alpha + 1$, then as $\pi$ preserves $<$, if $b$ is extended then so must $\pi(b)$.

Let $b$ be a branch (i.e. $b : \alpha \to \omega$, and $b\restrictedto\beta \in T$ for all $\beta < \alpha$) in $T$ such that $\pi(b) \neq b$. Let $c : \alpha \to \omega$ be defined as $c(\beta) := \pi(b)(\beta) + 1$. Let:

$$
\begin{align*}
X := \lbrace t \cup c\restrictedto(\alpha - \dom(t)) : t \in T\rbrace
\end{align*}
$$

Let $T' := T \cup X \cup \lbrace b\rbrace$. Since $T$ is countable, $X$ is countable so $T'$ is a normal $(\alpha + 1)$-tree. Clearly $b$ is extended in $T'$, but we observe that $\pi(b)$ is not - given any branch $d \in T'$, we have that either $d = b$, or $d(\beta) > \pi(b)(\beta)$ for sufficiently large $\beta < \alpha$, so $d \neq \pi(b)$. 
$\square$

<a name="ex15.19"></a>
## Exercise 15.19.
<i>Solution.</i> The hint basically solves the problem: Let $T \in G$ such that $T \forces \dot{\rho}$ is a nontrivial automorphism of $\T$. We may choose $T$ strong enough so that, in $V[G]$, $\pi := \rho\restrictedto T$ is a non-trivial automorphism. Then $T \subseteq \mathcal{T}$, and the set in the hint is dense below $T$ by <a href="#ex15.18">Exercise 15.18</a> (call this set $D$). By genericity of $G$, there exists some $T' \leq T$ in $G$ such that $\pi$ cannot be extended to a non-trivial automorphism of $T'$. This is a contradiction, as we have $T' \subseteq \T$ so $\rho\restrictedto T'$ extends $\pi$, and is a non-trivial automorphism of $T'$. 
$\square$

<a name="ex15.20"></a>
## Exercise 15.20.
<i>Solution.</i> Let $(P,<)$ denote the partial order of all normal countable trees with the property in the hint. We first show that there exists such trees of arbitrarily tall heights. This is necessary to ensure that $\T$ is indeed a Suslin tree (otherwise it would not be of uncountable height).

Let $T$ be an $\alpha$-tree, where $\alpha$ is a limit ordinal, satisfying (vi) and (vii). For $t \in T$, define:

$$
\begin{align*}
\ext(t) := t \cup \lbrace (\beta,0) : \beta \in \alpha - \dom(t)\rbrace
\end{align*}
$$

Let $X := \lbrace \ext(t) : t \in T\rbrace$, and let $T' := T \cup X$. We have seen that $T' < T$ and $T$ is of height $\alpha + 1$ ($X$ is countable as $T$ is, and $t \sqsubseteq \ext(t)$ for all $t \in T$). We now show that $T'$ satisfies (vi) and (vii).
<ol>
<li>[(vi)] Let $b \in X$, and let $b'$ be such that $b \sim b'$. Let $\beta < \alpha$ be such that for all $\beta \leq \gamma < \alpha$, $b'(\gamma) = 0$ (such a $\beta$ exists as $b \sim b'$, and $b$ is eventually zero). Let $t' := b'\restrictedto\beta$. By (iii) of (15.20), we may choose $\gamma$ and $t \in T$ such that $b = \ext(t)$ and $\dom(t) = \gamma$. Then since $b \sim b'$, $t \sim t'$ so $t' \in T$ as $T$ satisfies (vi). Then $b' = \ext(t') \in X$..</li>
<li>[(vii)] Let $b,b' \in X$, so there exist $t,t'$ such that $b = \ext(t)$ and $b' = \ext(t')$. WLOG assume $\dom(t) \geq \dom(t')$. By (iii) of (15.20), there exists a $t" \geq t'$ such that $\dom(t) = \dom(t")$ and $\ext(t') = \ext(t")$. Then $t,t"$ are at the same level, and since $T$ satisfies (vii), $t \sim t"$. Since $t(\beta) = t"(\beta) = 0$ for $\beta \in \alpha - \dom(t)$, $b \sim b'$.</li>
</ol>

<b>Claim.</b>. Every $T \in P$ is homogeneous.

<i>Proof.</i> Let $x,y \in T$ be at the same level. Then $x \sim y$, so let $\alpha_1,\dots,\alpha_n \in \dom(x)$ be all the ordinals such that $x(\alpha_i) \neq y(\alpha_i)$. Define $\pi : T \to T$ such that for $t \in T$ and $\beta \in \dom(t)$:

$$
\begin{align*}
\pi(t)(\beta) :=
\begin{cases}
y(\beta), &\text{if $\beta = \alpha_i$ and $t(\beta) = x(\beta)$} \\
x(\beta), &\text{if $\beta = \alpha_i$ and $t(\beta) = y(\beta)$} \\
t(\beta), &\text{otherwise}
\end{cases}
\end{align*}
$$

It's easy to see that $t \sim \pi(t)$, so $\pi$ is well-defined. It's clear that if $s \sqsubseteq t$ then $\pi(s) \sqsubseteq \pi(t)$. Observing that $\pi^2 = \id$, we have that $\pi$ is one-to-one and onto. Finally, of course $\pi(x) = \pi(y)$. 
$\blacksquare$

We shall call this construction the <b>eventually-zero construction</b>.

We now show that the Suslin tree $\T$ is homogeneous. Let $x,y \in \T$, so there exists some $T \in G$ such that $x,y \in T$ (say $\dom(x) = \alpha$). $T$ is homogeneous by the above claim,  so there exists an automorphism $\pi : T \to T$ such that $\pi(x) = y$. We then extend $\pi$ to $\pi' : \T \to \T$ by stipulating that for $t \in \T$, $\pi'(t) := \pi(t\restrictedto\alpha) \cup (t - t\restrictedto\alpha)$, and clearly $\pi'$ remains an automorphism. Thus $\T$ is homogeneous. 
$\square$

<a name="ex15.21"></a>
## Exercise 15.21.
\begin{setup}[<a href="#ex15.21">Exercise 15.21</a>, <a href="#ex15.22">Exercise 15.22</a>]
Let $(P,<)$ be the notion of forcing consisting of finite trees $(T,<_T)$ such that $T \subseteq \omega_1$, and such that $\alpha < \beta$ if $\alpha <_T \beta$; $(T_1,<_{T_1})$ is stronger than $(T_2,<_{T_2})$ if and only if $T_1 \supseteq T_2$ and $<_{T_1} \; = \; <_{T_2} \cap \, (T_2 \times T_2)$ [sic]\footnote{Replace "$<_{T_1} \; = \; <_{T_2} \cap \, (T_2 \times T_2)$" with "$<_{T_2} \; = \; <_{T_1} \cap \, (T_2 \times T_2)$".}. If $G$ is a generic set of conditions, then $\T = \bigcup\lbrace T : T \in G\rbrace$ is a Suslin tree. The crucial properties to verify are: (a) $(P,<)$ satisfies the countable chain condition, and (b) $\T$ has no uncountable antichain.
\end{setup}

$(P,<)$ satisfies c.c.c.

\begin{hint}
Given an uncountable set $W$ of conditions, use $\Delta$-Lemma to find an uncountable $Z \subseteq W$ such that any $X,Y \in Z$ are compatible.
\end{hint}

<a name="lem15.21.A"></a>
<b>Lemma 15.21.A.</b> Let $(P,<_P)$ and $(Q,<_Q)$ be two partial orders with $P,Q \subseteq \boldsymbol{\mathrm{ORD}}$. Fix $x_0 \in P$ and $y_0 \in Q$. Suppose that:
<ol>[label=(\alph*)]
<li> If $x <_P y$ or $x <_Q y$, then $x < y$..</li>
<li> For all $x \in P \cap Q$, we have $\pred_P(x) = \pred_Q(x)$.</li>

<li> $(\pred_P(x_0) \cup \lbrace x_0\rbrace) \cap Q = (\pred_Q(y_0) \cup \lbrace y_0\rbrace) \cap P$..</li></ol>
Then there exists a partial order $(R,<_R)$ satisfying (i) above such that:
<ol>
<li> $R = P \cup Q$.</li>

<li> $<_P \, = \, <_R \cap \, (P \times P)$..</li>
<li> $<_Q \, = \, <_R \cap \, (Q \times Q)$.</li>

<li> $x_0$ and $y_0$ are comparable..</li></ol>
The lemma still holds if we omit condition (c), and remove the result (iv).

<i>Proof.</i> Fix $x_0 \in P$ and $y_0 \in Q$. Consider the following relation on $R$:
\begin{small}

$$
\begin{gather*}
S := \, <_P \cup <_Q \cup \, \underbrace{\lbrace (x,y) : x \leq_P x_0 \wedge y \leq_Q y_0 \wedge x < y\rbrace}_{=:A} \cup \underbrace{\lbrace (x,y) : x \leq_Q y_0 \wedge y \leq_P x_0 \wedge x < y\rbrace}_{=:B}
\end{gather*}
$$

\end{small}

Let $<_R$ denote the transitive closure of $S$. We see that if $x <_R y$, then there exists a sequence $(x,z_0),(z_0,z_1),\dots,(z_n,y)$ all in $S$. But we see that this implies $x < z_0$, $z_i < z_{i+1}$ and $z_n < y$, so $x < y$. In particular, $x \not<_R x$. Furthermore, $<_R$ is transitive by definition of transitive closure. Therefore, $(R,<_R)$ does define a partial order which (a) holds. Also, clearly $x_0 \leq_R y_0$.

It remains to show that the properties (ii) and (iii). The proof of each is the same, so we just show for (ii). Before that, we make the following observations:
<ol>
<li> If $x <_P y$ and $y <_P z$, then immediately we have $x <_P z$.</li>

<li> If $x <_Q y$ and $y <_P z$, then in particular we have $y \in P$. But since $\pred_Q(y) = \pred_P(y)$, we also have $x <_P y$, so $x <_P z$..</li>
<li> If $(x,y) \in A$ and $y <_P z$, then $y \leq_Q y_0$ and $y \in P$. By (c), this implies that $y \leq_P x_0$ and $y \in Q$. Since $x \leq_P x_0$ and $x < y$, we therefore have $x <_P y$ necessarily (as $\pred_P(x_0)$ is well-ordered by $<_P$). Therefore $x <_P z$.</li>

<li> By symmetry, we may reduce the case of $y <_Q z$ and ($x <_P y$ or $x <_Q y$ or $(x,y) \in B$) to just $x <_Q z$..</li>
<li> If $x <_P y$ and $(y,z) \in A$, then $x <_P y \leq_P x_0$ and $x < z$, so $(x,z) \in A$.</li>

<li> If $x <_Q y$ and $(y,z) \in A$, then since $y \in P$ and $\pred_Q(y) = \pred_P(y)$, we have that $x <_P y$ so $(x,z) \in A$ by above..</li>
<li> If $(x,y) \in A$ and $(y,z) \in A$, then in particular we have $x,y \leq_P x_0$ and $x < y$. This implies that $x <_P y$, so by above we have that $(x,z) \in A$.</li>

<li> If $(x,y) \in B$ and $(y,z) \in A$, then in particular we have $x \leq_P x_0$ and $z \leq_P x_0$ and $x < z$, so we must have $x <_P z$..</li>
<li> By symmetry, we may reduce the case of $(y,z) \in B$ and $x <_R y$ to the case of $x <_Q z$ or $(x,z) \in B$.</li>
</ol>
The only cases which cannot be easily reduced are the case where $(x,y) \in B$ and $y <_P z$, and $(x,y) \in A$ and $y <_Q z$.

Now suppose $x <_R y$ and $x,y \in P$, so there exist a sequence $(x,z_0),(z_0,z_1),\dots,(z_n,y)$ all in $S$. Note that since $y \in P$, we have $z <_P y$ iff $z <_Q y$. By the above observations, we may reduce it to either one of the following:
<ol>[label=(\arabic*)]
<li> $(x,y) \in A$..</li>
<li> $(x,y) \in B$.</li>

<li> $(x,z) \in B$ and $z <_P y$..</li></ol>
For (1) and (2), since $x,y \in P$ we have that $x < y$ and $x,y \leq_P x_0$, so $x <_P y$. For (3), since $x \in P$, $x \leq_Q y_0$ implies $x \leq_P x_0$ by (c). But $z \leq_P x_0$ and $x < z$, so $x <_P z$. Therefore $x <_P y$. Thus, $<_P \, = \, <_R \cap \, (P \times P)$. 
$\blacksquare$

<i>Solution.</i> By the hint, we shall show that $(P,<)$ in fact has the (K) property. Let $W \subseteq P$ be an uncountable set of conditions. Since the trees $T \in P$ are finite, by the $\Delta$-Lemma we first obtain an uncountable set $Z \subseteq W$ such that for all $S,T \in Z$, $S \cap T = R$ for some finite set $R$.

Fix $\alpha \in R$. For all $T \in Z$, consider $\pred_T(\alpha) := \lbrace \beta \in T : \beta <_T \alpha\rbrace$. Since this is a finite subset of $\alpha$, there are only countably many possibilities of $\pred_T(\alpha)$. Thus, there exists an uncountable set $Z' \subseteq Z$ such that for all $S,T \in Z'$, $\pred_S(\alpha) = \pred_T(\alpha)$. We repeat this for all $\alpha\in R$, and since $R$ is finite we obtain a final uncountable set $Z_0 \subseteq W$ such that for all $\alpha \in R$ and for all $S,T \in Z_0$, $\pred_S(\alpha) = \pred_T(\alpha)$. By <a href="#lem15.21.A">Lemma 15.21.A</a>, this implies that $(S \cup T, <_S \, \cup \, <_T) \in P$ and is stronger than both $(S,<_S)$ and $(T,<_T)$, so $S$ and $T$ are compatible, as desired. 
$\square$

<a name="ex15.22"></a>
## Exercise 15.22.
<i>Solution.</i> Following the hint, suppose $T_0 \forces \dot{A}$ is uncountable. We first construct an uncountable set of pairs $(T_\eta,\alpha_\eta)$, where $\eta < \omega_1$, as follows: Suppose $(T_\xi,\alpha_\xi)$ has been constructed for $\xi < \eta$. Let $T_\eta \leq T$ be such that $T_\eta \forces (\exists \beta > \sup_{\xi<\eta} \alpha_\xi) \, \beta \in \dot{A}$ (this is possible as $\eta$ is countable). Let $\alpha_\eta$ be such $\beta$. We may choose $T_\eta$ such that $T_\eta \neq T_\xi$ for all $\xi < \eta$. We may also assume WLOG that $\alpha_\eta \in T_\eta$, since otherwise we may replace $(T_\eta, <_{T_\eta})$ with $(T_\eta \cup \lbrace \alpha_\eta\rbrace, <_{T_\eta})$.

Now $W := \lbrace T_\eta : \eta < \omega_1\rbrace$ is an uncountable subset of $P$, and as we saw in the proof of <a href="#ex15.21">Exercise 15.21</a> we obtain an uncountable $Z \subseteq W$ such that for all $S,T \in Z$, $(S \cup T,<_S \, \cup \, <_T)$ is a condition stronger than both $S$ and $T$.

<b>Claim.</b>. There exists an uncountable $Z' \subseteq Z$ such that for all $T_\eta,T_\delta \in Z'$, $\alpha_\delta \notin T_\eta$ and $\alpha_\eta \notin T_\delta$.

<i>Proof.</i> Let $\xi < \omega_1$ be $0$ or a limit ordinal. Let $X_n := \lbrace \eta < \omega_1 : \alpha_{\xi + n} \notin T_\eta\rbrace$. We see that we must have $X_n$ is uncountable for some $n$ - otherwise, $\bigcup_n X_n$ is countable, so $\omega_1 - \bigcup_n X_n = \bigcap_n \omega_1 - X_n$ is uncountable, in particular non-empty. This means that for some $\eta$, we have that $\alpha_{\xi + n} \in T_\eta$ for all $n$, contradicting that $T_\eta$ is finite.

For $\zeta < \omega_1$, define $Z_\zeta,Y_\zeta \subseteq \omega_1$ inductively as follows:
<ol>
<li> Let $Z_0 := \emptyset$, $Y_0 := \omega_1$.</li>

<li> Suppose $Z_\zeta$,$Y_\zeta$ has been defined with $Y_\zeta$ uncountable. Let $\xi$ be the least limit ordinal such that $\xi > \sup{Z_\zeta}$, and for all $\eta \in Z_\zeta$ we have that $\alpha_\xi > \sup{T_\eta}$. By repeating the proof in the first paragraph, there exists some $n$ such that the set of $\delta \in Y_\zeta$ in which $\alpha_{\xi+n} \notin T_\delta$ is uncountable. Let $Y_{\zeta+1}$ be this uncountable set, and let $Z_{\zeta+1} := Z_\zeta \cup \lbrace \xi+n\rbrace$..</li>
<li> If $\zeta$ is a limit ordinal, let $Z_\zeta := \bigcup_{\eta<\zeta} Z_\eta$.</li>
</ol>
Given $\zeta < \omega_1$, let $\eta,\delta \in Z_\zeta$, and suppose $\eta < \delta$. Then we see that if $\eta$ is chosen in the $\zeta^\text{th}$ stage (i.e. $Z_{\zeta+1} = Z_\zeta \cup \lbrace \eta\rbrace$), then $\delta \in Y_{\zeta+1}$ necessarily, so $\alpha_\eta \notin T_\delta$. On the other hand, if $\delta$ is chosen at the $(\zeta')^\text{th}$ stage, then we note that $\alpha_\delta > \sup{T_\eta}$, so in particular $\alpha_\delta \notin T_\eta$.

Now let $Z' := \bigcup_{\zeta<\omega_1} Z_\zeta$. Then $Z'$ is an unbounded subset of $\omega_1$, hence uncountable, and by the previous paragraph we note that for $T_\eta,T_\delta \in Z'$, $\alpha_\eta \notin T_\delta$ and $\alpha_\delta \notin T_\eta$. 
$\blacksquare$

Now for each $\xi \in Z'$, consider the set $\lbrace \pred_{T_\xi}(\alpha_\xi) : \xi < \omega_1\rbrace \cap R$. This is a finite subset of $R$, so there are only finitely many possibilities. Therefore, we may obtain another $Z" \subseteq Z'$ such that $\lbrace \pred_{T_\xi}(\alpha_\xi) : \xi < \omega_1\rbrace \cap R$ is equal for all $T_\xi \in Z"$. Then the full premise of <a href="#lem15.21.A">Lemma 15.21.A</a> is satisfied, so for all $T_\eta,T_\delta \in Z"$ there exists some tree $T$ such that $(T,<_T)$ is stronger than both $(T_\eta,<_{T_\eta})$ and $(T_\delta,<_{T_\delta})$. Since $\alpha_\eta$ and $\alpha_\delta$ are compatible in $T$, $T \forces \alpha_{T_\eta}$ is compatible with $\alpha_{T_\delta}$, so in particular $T \forces \dot{A}$ is not an antichain. 
$\square$

<a name="ex15.23"></a>
## Exercise 15.23.
\begin{setup}{<a href="#ex15.23">Exercise 15.23</a>, <a href="#ex15.24">Exercise 15.24</a>}
Let $Q$ consists of all countable sequences $p = \c{S_\xi : \xi < \alpha}$ ($\alpha < \omega_1$) where $S_\xi \subseteq \xi$ for all $\xi < \alpha$; let $p \leq q$ if and only if $p$ extends $q$. $Q$ is $\aleph_0$-closed.
\end{setup}

Let $G$ be $Q$-generic. Then $V[G] \models \diamond$.

\begin{hint}
If $p \forces$ ($\dot{C}$ is closed unbounded set and $\dot{X} \subseteq \omega_1$), find $q \leq p$ such that $q = \c{S_\xi : \xi \leq \alpha}$ and $q \forces (\alpha \in \dot{C} \text{ and } \dot{X} \cap \alpha = S_\alpha)$.
\end{hint}

<a name="lem15.23.A"></a>
<b>Lemma 15.23.A.</b> Let $P$ be an $\omega$-closed partial order, and let $\lbrace p_n : n < \omega\rbrace \subseteq P$. Then there exists a $q \in P$ such that for all $n$, either $q \leq p_n$, or $q$ and $p_n$ are incompatible.

<i>Proof.</i> Define a sequence $\c{q_n : n < \omega}$ as follows: Start with $q_0 := p_0$. Suppose $q_n$ is defined, and we consider two cases:
<ol>
<li> If $q_n$ and $p_{n+1}$ are incompatible, let $q_{n+1} := q_n$..</li>
<li> If $q_n$ and $p_{n+1}$ are compatible, let $q_{n+1} \in P$ such that $q_{n+1} \leq q_n$ and $q_{n+1} \leq p_{n+1}$.</li>
</ol>
Since $P$ is $\omega$-closed, there exists a $q \in P$ such that $q \leq p_n$ for all $n$. It's easy to see that $q$ is the desired condition. 
$\blacksquare$

<a name="lem15.23.B"></a>
<b>Lemma 15.23.B.</b> Let $P$ be an $\omega$-closed partial order. Let $\dot{X}$ be a name such that $\forces \dot{X} \subseteq \omega_1$. For any $\alpha < \omega_1$, there exists a $p \in P$ such that $p$ decides $X \cap \alpha$ - that is, there exists a $A \subseteq \alpha$ (in the ground model) such that $p \forces \dot{X} \cap \alpha = \check{A}$.

<i>Proof.</i> We may assume WLOG that $\dot{X} = \lbrace (\check{\gamma},p_\gamma) : \gamma < \omega_1\rbrace$, where $p_\gamma \in P$ for all $\gamma$. By <a href="#lem15.23.A">Lemma 15.23.A</a>, there exists a $p \in P$ such that for all $\gamma < \alpha$, $p \leq p_\gamma$ or $p$ is incompatible with $p_\gamma$. In other words, if $G,H$ are $P$-generic such that $p \in G$ and $p \in H$, then for all $\gamma$, either $p_\gamma \in G$ and $p_\gamma \in H$, or $p_\gamma \notin G$ and $p_\gamma \notin H$. Therefore, $p$ decides the membership of $\gamma$ in $\dot{X}$ for all $\gamma < \alpha$. Since $P$ is $\omega$-closed, no countable subsets are added in the generic extension, so the decided set $\dot{X} \cap \alpha$ must be in the ground model. 
$\blacksquare$

<i>Solution.</i> Start with a condition $p \in G$ such that $p \forces$ ($\dot{C}$ is closed unbounded set and $\dot{X} \subseteq \omega_1$). Let:

$$
\begin{align*}
D := \lbrace q \leq p : q \forces (\alpha \in \dot{C} \text{ and } \dot{X} \cap \alpha = S_\alpha)\rbrace
\end{align*}
$$

We shall show that $D$ is dense below $p$. Indeed, let $p' \leq p$, and suppose $p' = \c{S_\xi : \xi < \gamma}$. Define sequences $\c{q_n : n < \omega}$ and $\c{\alpha_n : n < \omega}$ as follow: Let $q_0 = p'$ and $\alpha_0 = \gamma$. Suppose $q_n,\alpha_n$ are defined. Now $q_n \forces (\exists \beta > \check{\alpha}_n) \, \beta \in \dot{C}$, so there exists $\alpha_{n+1} > \dom(q_n)$ and $q_{n+1}'$, with $\dom(q_{n+1}') > \alpha_{n+1}$, such that $q_{n+1}' \forces \check{\alpha}_{n+1} \in \dot{C}$. By <a href="#lem15.23.B">Lemma 15.23.B</a>, there exists some $q_{n+1} \leq q_{n+1}'$ and $A_{\alpha_{n+1}} \subseteq \alpha_{n+1}$ in the ground model such that $q_{n+1} \forces \dot{X} \cap \alpha_{n+1} = \check{A}_{\alpha_{n+1}}$. Note that $A_{\alpha_n} \subseteq A_{\alpha_{n+1}}$ necessarily.

Now let $q := \bigcup_n q_n$, and $\alpha := \lim_n \alpha_n$. Then $q \forces (\forall n \in \omega) \, \check{\alpha}_n \in \dot{C}$, and since $q \forces \dot{C}$ is closed, we also have that $q \forces \check{\alpha} \in \dot{C}$. Noting that $\alpha_1 < \dom(q_1) < \alpha_2 < \dom(q_2) < \dots$, we have $\dom(q) = \alpha$, say $q = \c{S_\xi : \xi < \alpha}$. Then let $q' := \c{S_\xi : \xi \leq \alpha}$, and $S_\alpha := \bigcup_{n<\omega} A_{\alpha_n}$. Then $q' \forces (\forall n < \omega) \, \dot{X} \cap \alpha_n = A_{\alpha_n}$, so $q' \forces \dot{X} \cap \alpha = S_\alpha$. Thus $q' \forces (\alpha \in \dot{C} \text{ and } \dot{X} \cap \alpha = S_\alpha)$, as desired. 
$\square$

<a name="ex15.24"></a>
## Exercise 15.24.
<i>Solution.</i> By <a href="#ex15.16">Exercise 15.16</a>, we let $(R,<)$ denote the notion of forcing that collapses $2^{\aleph_0}$ to $\aleph_1$, and it suffices to show that $B(Q) = B(R)$. For each infinite $\alpha < \omega_1$, we let $h_\alpha$ be a one-to-one correspondence between the cardinal $2^{\aleph_0}$ and $P(\alpha)$.

<u>$B(R) \subseteq B(Q)$:</u> Define $f : R \to Q$ by stipulating that $f(p) = \c{S_\xi : \xi < \dom(p)}$, where:

$$
\begin{align*}
S_\xi :=
\begin{cases}
\emptyset, &\text{if $\xi < \omega$} \\
h_\beta(p(\beta)), &\text{if $\xi = \omega + \beta$ for some ordinal $\beta$}
\end{cases}
\end{align*}
$$

Since $h_\beta$ is one-to-one for all $\beta$, $f$ is also one-to-one and $p < q$ iff $f(p) < f(q)$. Thus, $R$ is isomorphic to a subset of $Q$, so $B(R) \subseteq B(Q)$.

<u>$B(Q) \subseteq B(R)$:</u> Define $g : Q \to R$ by stipulating that $g(\c{S_\xi : \xi < \alpha}) = p$, where $\dom(p) = \alpha$ and for all $\xi < \alpha$, $p(\xi) := h_\xi^{-1}(S_\xi)$. Then it's easy to see that $g$ is one-to-one and respects $<$, so $Q$ is isomorphic to a subset of $R$. Hence $B(Q) \subseteq B(R)$. 
$\square$

<a name="ex15.25"></a>
## Exercise 15.25.
<a name="lem15.25.A"></a>
<b>Lemma 15.25.A.</b> A purely combinatorial argument can be used to show that $\diamond$ is equivalent to the following statement:
<ol>
<li>[$\diamond'$] There exists a sequence of functions $h_\alpha$, $\alpha < \omega_1$, such that for every $f : \omega_1 \to \omega_1$, the set $\lbrace \alpha < \omega_1 : f\restrictedto\alpha = h_\alpha\rbrace$ is stationary..</li></ol>

<i>Proof.</i> We prove the equivalence.

<u>$\diamond \implies \diamond'$:</u> We first make a few claims.

<b>Claim.</b>. Let $\kappa$ be a uncountable regular cardinal. Let $f : \kappa \to \kappa \times \kappa$ be a one-to-one correspondence. Then the set $C := \lbrace \alpha < \kappa : f"(\alpha) = \alpha \times \alpha\rbrace$ is closed unbounded.

<i>Proof.</i> <u>$C$ is closed:</u> Let $\alpha < \kappa$ such that $C \cap \alpha$ is unbounded. Then:

$$
\begin{align*}
f"(\alpha) = \bigcup_{\beta \in C \cap \alpha} f"(\beta) = \bigcup_{\beta \in C \cap \alpha} \beta \times \beta = \alpha \times \alpha
\end{align*}
$$

<u>$C$ is unbounded:</u> Fix any $\alpha < \kappa$. Let $\beta_0 := \alpha$, and choose $\beta_n$'s such that we get:

$$
\begin{align*}
f"(\beta_0) \subseteq \beta_1 \times \beta_1 \subseteq f"(\beta_2) \subseteq \beta_3 \times \beta_3 \subseteq \dots
\end{align*}
$$

Let $\beta := \lim_n \beta_n$, and clearly we get $f"(\beta) = \beta$. 
$\blacksquare$

<b>Claim.</b>. Assume $\diamond$. There exists a sequence of sets $A_\alpha \subseteq \alpha \times \alpha$, where $\alpha < \omega_1$, such that for all $A \subseteq \omega_1 \times \omega_1$, the set $\lbrace \alpha < \omega_1 : A \cap (\alpha \times \alpha) = A_\alpha\rbrace$ is stationary.

<i>Proof.</i> Fix any one-to-one correspondence $f : \omega_1 \to \omega_1 \times \omega_1$. Let $C := \lbrace \alpha < \omega_1 : f"(\alpha) = \alpha \times \alpha\rbrace$. By the previous claim, $C$ is closed unbounded. Let $\c{S_\alpha : \alpha < \omega_1}$ be a $\diamond$-sequence. We define:

$$
\begin{align*}
A_\alpha := f"(S_\alpha) \cap (\alpha \times \alpha)
\end{align*}
$$

We shall show that $\c{A_\alpha : \alpha < \omega_1}$ is the desired sequence. Fix $A \subseteq \omega_1 \times \omega_1$, and let $S := \lbrace \alpha < \omega_1 : A \cap (\alpha \times \alpha) = A_\alpha\rbrace$. It suffices to show that $S \cap C$ is stationary. Indeed, we have that $T := \lbrace \alpha < \omega_1 : f_{-1}(A) \cap \alpha = S_\alpha\rbrace$ is stationary, so $T \cap C$ is stationary. Observe that, given that $\alpha \in C$, we have:

$$
\begin{align*}
\alpha \in T &\iff f_{-1}(A) \cap \alpha = S_\alpha \\
&\iff f"(f_{-1}(A) \cap \alpha) = f"(S_\alpha) \\
&\iff A \cap f"(\alpha) = f"(S_\alpha) \cap (\alpha \times \alpha) \\
&\iff A \cap (\alpha \times \alpha) = A_\alpha \\
&\iff \alpha \in S
\end{align*}
$$

So $S \cap C = T \cap C$ is stationary. Note that $f"(S_\alpha) \subseteq \alpha \times \alpha$ as $f"(\alpha) = \alpha \times \alpha$. 
$\blacksquare$

We now prove the $\implies$ direction. Let $\c{A_\alpha : \alpha < \omega_1}$ be the sequence of sets in the second claim. For each $\alpha$, let $h_\alpha := A_\alpha$ if $A_\alpha \subseteq \alpha \times \alpha$ is a function, and $h_\alpha = \emptyset$ otherwise. Fix a function $f : \omega_1 \to \omega_1$, and let $C := \lbrace \alpha < \omega_1 : f\restrictedto\alpha = f \cap (\alpha \times \alpha)\rbrace$.

We shall show that $C$ is closed unbounded. The argument is very much similar to that of the first claim - to see that $C$ is closed, suppose $C \cap \alpha$ is unbounded. Then $f\restrictedto\alpha = \bigcup_{\beta \in C \cap \alpha} f\restrictedto\beta = \bigcup_{\beta \in C \cap \alpha} f \cap (\beta \times \beta) = f \cap (\alpha \times \alpha)$. To see that $C$ is unbounded, fix any $\alpha < \omega_1$. Let $\beta_0 := \alpha$, and construct a sequence of ordinals $\beta_n$ such that:

$$
\begin{align*}
f\restrictedto\beta_0 \subseteq f \cap (\beta_1 \times \beta_1) \subseteq f\restrictedto\beta_2 \subseteq f \cap (\beta_3 \times \beta_3) \subseteq \dots
\end{align*}
$$

Then $\beta := \lim_n\beta_n \in C$. Now since $S := \lbrace \alpha < \omega_1 : f \cap (\alpha \times \alpha) = A_\alpha\rbrace$, we have $f\restrictedto \alpha = f \cap (\alpha \times \alpha) = h_\alpha$ on $S \cap C$, as desired.

<u>$\diamond' \implies \diamond$:</u> Let $\c{h_\alpha : \alpha < \omega_1}$ be a $\diamond'$-sequence. For each $\alpha$, let $S_\alpha := \lbrace \beta < \alpha : h_\alpha(\beta) = 1\rbrace$. For any $A \subseteq \omega_1$, let $f_A : \omega_1 \to 2$ be such that $f_A(\alpha) = 1$ iff $\alpha \in A$. Then $S := \lbrace \alpha < \omega_1 : f_A\restrictedto\alpha = h_\alpha\rbrace$ is stationary. Since:

$$
\begin{align*}
f_A\restrictedto\alpha = h_\alpha &\iff (\forall \beta < \alpha)(f_A(\beta) = 1 \leftrightarrow h_\alpha(\beta) = 1) \\
&\iff A \cap \alpha = \lbrace \beta < \alpha : h_\alpha(\beta) = 1\rbrace \\
&\iff A \cap \alpha = S_\alpha
\end{align*}
$$

so $\c{S_\alpha : \alpha < \omega_1}$ is a $\diamond$-sequence. 
$\blacksquare$

$V = L$ implies $\diamond'$.

<i>Solution.</i> It is proved in Theorem 13.21 that $V = L$ implies $\diamond$, so by <a href="#lem15.25.A">Lemma 15.25.A</a> we have that $V = L$ implies $\diamond'$. 
$\square$

<a name="ex15.26"></a>
## Exercise 15.26.
<a name="lem15.26.A"></a>
<b>Lemma 15.26.A.</b> For each regular cardinal $\kappa$, there exists an unbounded set $X \subseteq \kappa$, consisting only of limit ordinals, that is not stationary.

<i>Proof.</i> Let $C$ be the set of all limit ordinals below $\kappa$, and let $X := \lbrace \alpha + \omega : \alpha < \kappa\rbrace$. Clearly $X$ and $C - X$ are both unbounded. Furthermore, we see that $C - X$ is closed - otherwise, suppose we have $\lbrace \beta_n : n < \omega\rbrace$ is some increasing sequence in $C - X$ such that $\beta_n \to \alpha + \omega$ for some $\alpha < \kappa$. Then we must have $\alpha + k < \beta_n < \alpha + \omega$ for some $k \in \omega$, so $\beta_n = \alpha + k'$ for some $k' \in \omega$, contradicting that $\beta_n$ is a limit ordinal. Hence $X$ is non-stationary. 
$\blacksquare$

<i>Solution.</i> Consider the Suslin tree constructed in Theorem 15.26. Let $\vec{S} := \c{S_\alpha : \alpha < \omega_1}$ be a $\diamond$-sequence. Given another sequence $\vec{T} := \c{T_\alpha : \alpha < \omega_1}$ with $T_\alpha \subseteq \alpha$, we say that $\vec{T}$ <b>almost equal</b> $\vec{S}$ if $T_\alpha = S_\alpha$ for all but non-stationary many $\alpha$'s. We then observe that $\vec{T}$ remains a $\diamond$-sequence - indeed, given any $A \subseteq \omega_1$, let $S$ be the stationary set such that $A \cap \alpha = S_\alpha$ for all $\alpha \in S$. Let $X$ be the non-stationary set such that $T_\alpha = S_\alpha$ for all $\alpha \notin X$. Then $T := S - X$ remains stationary, so $A \cap \alpha = T_\alpha$ for $\alpha \in T$.

Now let $C$ be the closed unbounded set in Lemma 15.27 with the maximal antichain $A$, and let $S$ be the stationary set such that $A \cap \alpha = S_\alpha$ for all $\alpha \in S$. Let $X$ be the unbounded, non-stationary set $X$ in <a href="#lem15.26.A">Lemma 15.26.A</a> consisting only of countable limit ordinals. By the first paragraph, we may let $\vec{T} := \c{T_\alpha : \alpha < \omega_1}$ be the $\diamond$-sequence, almost equal to a $\diamond$-sequence $\vec{S}$, such that $T_\alpha = \emptyset$ for all $\alpha \in X$. Thus, we may run the construction of the Suslin tree $\T$ in Theorem 15.26 using $\vec{T}$. Since in this construction, we are only restricted to build $T_{\alpha+1}$ such that $S_\alpha$ is a maximal antichain in $T_{\alpha+1}$ for all $\alpha \in T \cap C$ and $T \cap C \cap X = \emptyset$, we are free to construct $T_{\alpha+1}$ for all $\alpha \in X$ (as long as $T_{\alpha+1}$ is a normal $(\alpha + 1)$-tree).

We shall describe the construction of $T_{\alpha+1}$ for $\alpha \in X$. Let:

$$
\begin{align*}
J := \lbrace (s,t) : s \neq t \wedge (&\exists \beta < \omega_1)(\beta \text{ is limit} \wedge s \in T_\beta \wedge t \in T_\beta \\
&\wedge \exists \pi \,(\pi : T_\beta \to T_\beta \text{ is an automorphism} \wedge \pi(s) = t))\rbrace
\end{align*}
$$

We see that $J \subseteq \omega_1 \times \omega_1$ so $\vert J\vert  \leq \aleph_1$. Let $f : \omega_1 \to J$ be onto. Let $Y = \lbrace \beta_\gamma : \gamma < \omega_1\rbrace \subseteq X$ be unbounded such that for all $\alpha < \omega_1$, if $f(\alpha) = (s,t)$ then $s,t \in T_{\beta_\alpha}$. Then, for each $\beta_\alpha \in Y$, repeat the construction of $T_{\beta_\alpha+1}$ in <a href="#ex15.18">Exercise 15.18</a> so that there does not exist an automorphism $\pi : T_{\beta_\alpha+1} \to T_{\beta_\alpha+1}$ such that $\pi(s) = t$, where $f(\alpha) = (s,t)$.

We shall show that $\T$ is rigid. Suppose not, so there exists a non-trivial automorphism $\pi$ of $\T$. Then we have $\pi(s) = t$ for some $s,t \in \T$. Let $\beta$ be the least limit ordinal such that $s,t \in T_\beta$. Then $f(\alpha) = (s,t)$ for some $\alpha$, so $\pi\restrictedto T_{\beta_\alpha}$ is an automorphism of $T_{\beta_\alpha}$ satisfying $T(s) = t$. Then $\pi\restrictedto T_{\beta_\alpha+1}$ is an automorphism of $T_{\beta_\alpha+1}$ such that $T(s) = t$, contradicting the construction in the previous paragraph. 
$\square$

\section{Exercise 15.27. (IP)}
If $V = L$ then there exists a homogeneous Suslin tree.

<i>Solution.</i> Consider the construction of a Suslin tree in Theorem 15.26.

% Let $\vec{S} = \c{S_\alpha : \alpha < \omega_1}$ be a $\diamond$-sequence, and consider the Suslin tree constructed in Theorem 15.26. Let $C$ be the closed unbounded set (w.r.t. a maximal antichain $A$) in Lemma 15.27, and let $S$ be the stationary set such that $A \cap \alpha = S_\alpha$ for all $\alpha \in S \cap C$. We shall describe how we may construct $\T$ so that $T_\alpha$ is homogeneous for all $\alpha$. If $\alpha$ is a limit ordinal and $\alpha \notin S \cap C$, then we may follow the eventually-zero construction in <a href="#ex15.20">Exercise 15.20</a>. If $\alpha \in S \cap C$, then we follow the same construction in Lemma 15.25.

% <b>Claim.</b>. %     $T_\alpha$ is homogeneous for all $\alpha$. Furthermore, if $\beta < \alpha$ and $\pi$ is an automorphism of $T_\beta$, then there exists an automorphism of $T_\alpha$ extending $\pi$.
% 

% <i>Proof.</i> %     For simplicity of this proof, shall take $\T$ as a subset of set of functions $t : \alpha \to \omega$, where $\alpha < \omega_1$ is a countable ordinal.

%     We induct on $\alpha$. The base case $\alpha = 0$ is trivial. If $\alpha = \beta + 2$, then let $s,t \in T_\alpha$ be such that $\dom(s) = \dom(t) = \beta + 1$. Let $s' := s\restrictedto\beta$ and $t' := t\restrictedto\beta$. By induction hypothesis, there exists an automorphism $\pi : T_{\beta+1} \to T_{\beta+1}$ such that $\pi(s') = t'$. We define $\rho : T_\alpha \to T_\alpha$ by stipulating that:
%     
$$
\begin{align*}
%         \rho(u) := \pi(u\restrictedto\beta)^\frown\rho'(u(\beta))
%     \end{align*}
$$

%     where:
%     
$$
\begin{align*}
%         \rho'(\gamma) :=
%         \begin{cases}
%             \gamma, &\text{if $\gamma \notin \lbrace s(\beta),t(\beta)\rbrace$} \\
%             s(\beta), &\text{if $\gamma = t(\beta)$} \\
%             t(\beta), &\text{if $\gamma = s(\beta)$}
%         \end{cases}
%     \end{align*}
$$

%     and clearly $\rho$ is an automorphism of $T_\alpha$ extending $\pi$ such that $\rho(s) = t$. This also shows that every automorphism of $T_{\beta+1}$ can be extended to one of $T_\alpha$.

%     If $\alpha$ is a limit ordinal, then given $s,t \in T_\alpha$ we have that $s,t \in T_\beta$ for some $\beta < \alpha$. By induction hypothesis, let $\pi : T_\beta \to T_\beta$ be an automorphism such that $\pi(s) = t$. By induction hypothesis again, for each $\beta \leq \gamma < \alpha$, we let $\pi_\beta := \pi$, and define $\pi_\gamma$ such that $\pi_\gamma$ extends $\pi_\delta$ for all $\beta \leq \delta < \gamma$. Let $\rho := \bigcup_{\beta \leq \gamma < \alpha} \pi_\gamma$, and we see that $\rho : T_\alpha \to T_\alpha$ is an automorphism extending $\pi$ such that $\pi(s) = t$, so $T_\alpha$ is homogeneous and any automorphism of $T_\beta$ is extended.

%     Now suppose $\alpha = \beta + 1$ where $\beta$ is a limit ordinal. Let $s,t \in T_\alpha$, with $\dom(s) = \dom(t) = \beta + 1$. We consider two cases.
%     <ol>
%         <li> Suppose $\beta \in S \cap C$.

%         <u>Homogeneity:</u> This implies that $s = b_u$ and $t = b_v$ for some $u,v \in $

%     </ol>
% \end{midproof}

% We thus do this for all limit ordinals, and therefore $T_\alpha$ is homogeneous for all $\alpha$. By <a href="#ex15.20">Exercise 15.20</a>, we see that $\T$ must be homogeneous.

% \question{Not yet} 
$\square$

<a name="ex15.28"></a>
## Exercise 15.28.
<i>Solution.</i> Let $A$ be the set in the hint. Clearly $A$ is uncountable, so we shall show that the elements are pairwise incompatible. Let $x \neq y$ be two elements in $T$, and suppose $(p_x,q_x)$ and $(p_y,q_y)$ are compatible. Then there exists some $z \in T$ such that $(p_x,q_x) > (p_z,q_z)$ and $(p_y,q_y) > (p_z,q_z)$. $p_x,p_y < p_z$ and $q_x,q_y < q_z$. But since the set of branches below $p_z$ (resp. $q_z$) are well-ordered, we must have that:

$$
\begin{align*}
(p_x < p_y \text{ or } p_x > p_y) \text{ and } (q_x < q_y \text{ or } q_x > q_y)
\end{align*}
$$

Since $p_x,q_x$ share the same level (and so do $p_y,q_y$), we in turn have $(p_x,q_x) < (p_y,q_y)$ or $(p_x,q_x) > (p_y,q_y)$. WLOG assume it's the first. Then $p_x \leq y$ and $q_x \leq y$. Since $p_x,q_x$ share the same level and the branches below $y$ are well-ordered, we must have $p_x = q_x$, a contradiction. 
$\square$

<a name="ex15.29"></a>
## Exercise 15.29.
<i>Solution.</i> Note that $P$ here refers to the forcing notion described in Example 14.2. It is in fact sufficient to show that $P$ is isomorphic to a dense subset of $P \times P$. Let $P' := P - \lbrace \emptyset\rbrace$, which is clearly dense in $P$ (so $P' \times P'$ is dense in $P \times P$). Let $\Gamma : \omega \times \omega \to \omega$ be the canonical well-ordering restricted to $\omega$. Define a function $F : P' \times P' \to P'$ as follows: Given $(p,q) \in P' \times P'$, define $r := F(p,q)$ such that:
<ol>
<li> $\dom(r) = \Gamma(\max{\dom(p)},\max{\dom(q)}) + 1$ (note that $\max{\dom(p)} = \dom(p) - 1$).</li>

<li> Let $k \in \dom(r)$, and suppose $\Gamma(i,j) = k$. Note that then $i \in \dom(p)$ and $j \in \dom(q)$, as $k < \dom(r)$ implies that $(i,j) < (\max{\dom(p)},\max{\dom(q)})$. Then define $r(k) := \Gamma(p(i),q(j))$..</li></ol>
We note that $F$ is invertible, as given $r \in P$ we may define $(p,q) := F^{-1}(r)$ by:
<ol>
<li> If $\Gamma(m,n) + 1 = \dom(r)$, then $\dom(p) = m + 1$ and $\dom(q) = n + 1$.</li>

<li> If $i \in \dom(p)$ and $j \in \dom(q)$ (so $\Gamma(i,j) < \dom(r)$), let $a,b$ be such that $\Gamma(a,b) = r(\Gamma(i,j))$. Then $p(i) := a$ and $q(j) := b$..</li></ol>
Finally, to see that $F$ respects $\leq$, suppose $(p,q) \leq (p',q')$, so $p \leq p'$ and $q \leq q'$. Then $\dom(r) = \Gamma(\max{\dom(p)},\max{\dom(q)}) + 1 \leq \Gamma(\max{\dom(p')},\max{\dom(q')}) + 1 = \dom(r')$. Furthermore, for $k < \dom(r)$, if $\Gamma(i,j) = j$ then $i \in \dom(p)$ and $j \in \dom(q)$. This implies that $p(i) = p'(i)$ and $q(i) = q'(i)$. Therefore $r'(k) = r(k)$, so $r' \geq r$. The converse is similar.

Thus, we have that $V[x] = V[x_1][x_2]$ as in the hint, which implies that $x$ is not minimal over the ground model. 
$\square$

<a name="ex15.30"></a>
## Exercise 15.30.
<i>Solution.</i> Let $P$ denote the Sacks forcing notion (i.e. the forcing notion of perfect trees). We first define a function $F : P \times \omega \to \omega$ as follows:

$$
\begin{align*}
F(p,n) := \min\lbrace k \in \omega : (&\forall t \in p)(\dom(t) = n \to \\
&(\exists s \in p)(\dom(s) \leq k \wedge s \supseteq t \wedge s^\frown 0 \in p \wedge s^\frown 1 \in p)\rbrace
\end{align*}
$$

Intuitively, we let $F(p,n)$ be the smallest natural number $k$ such that every $t \in P$ splits by the $k^\text{th}$ level. This is well-defined as $p$ is a perfect tree and there are only finitely many $t \in P$ with $\dom(t) = n$.

Fix an $f : \omega \to \omega$ in $V[a]$. Let $p \in P$ be such that $p \forces \dot{f} : \omega \to \omega$. We define a sequence of perfect trees $q_n \in P$, a function $g : \omega \to \omega$ (in $V$), and natural numbers $k_n \in \omega$ inductively as follows: First let $q_0 := p$, $g(0)$ be any natural number and $k_n := F(p,0)$. Now suppose $q_n,g(n),k_n$ have been defined. Let

$$
\begin{align*}
r_{k,n+1} := \bigcup\lbrace r \leq q_n : r \forces \dot{f}(n+1) < k\rbrace
\end{align*}
$$

Of course union of perfect trees is a perfect tree, so $r_{k,n+1} \in P$ for all $k,n$. It's easy to see that $r_{k,n+1} \subseteq r_{k+1,n+1}$ and $\bigcup_{k < \omega} q_{k,n+1} = q_n$ (as $q_n \forces \dot{f} : \omega \to \omega$). Thus, we let $k_{n+1} := F(q_n,k_n) + 1$, and we may let $g(n+1)$ be large enough so that:

$$
\begin{align*}
\lbrace t\restrictedto k_{n+1} : t \in q_{g(n+1),n+1}\rbrace = \lbrace t\restrictedto k_{n+1} : t \in q_n\rbrace
\end{align*}
$$

This is possible as the sets above are finite. We thus let $q_{n+1} := q_{g(n+1),n+1}$.

Let $q := \bigcap_n q_n$. We shall show that $q$ is a perfect tree. Indeed, let $t \in q$, and suppose $\dom(t) = n$. We have that $t \in q_n$. Noting that $k_n \geq n$, by definition of $F(q_n,k_n)$ we have that there exists some $s \subseteq t$, with $\dom(s) \leq F(q_n,k_n)$, such that $s^\frown 0 \in q_n$ and $s^\frown 1 \in q_n$. Since $\lbrace t\restrictedto k_{n+1} : t \in q_n\rbrace = \lbrace t\restrictedto k_{n+1} : t \in q_{n+1}\rbrace$, we have that $s^\frown 0,s^\frown 1 \in q_{n+1}$, and since $k_m > k_{n+1}$ for all $m > n + 1$, we have that $s^\frown 0,s^\frown 1 \in q_m$ for all $m \geq n + 1$. Therefore, $s^\frown 0,s^\frown 1 \in q$ so $q$ is perfect.

Thus, we obtain a $q \in P$ such that $q \leq q_n$ for all $n$, so $q \forces (\forall n \in \omega)(\dot{f}(n) < \check{g}(n))$. Therefore $g$ dominates $f$ and $g$ is in the ground model. 
$\square$

<a name="ex15.31"></a>
## Exercise 15.31.
<i>Solution.</i> By Theorem 15.38, it suffices to show that every $f : \kappa \to P(\kappa)$ in the generic extension is in the ground model. Following the hint, consider the set $X := \lbrace (\alpha,\beta) : \beta \in f(\alpha)\rbrace \in P(\kappa \times \kappa)$. Define, in the generic extension $g : \kappa \times \kappa \to 2$ by stipulating that $g(\alpha,\beta) = 1$ iff $(\alpha,\beta) \in X$. Since $B$ is $(\kappa,2)$-distributive, $g$ is in the ground model, and so $X$ is in the ground model. Then we may define $f$ in the ground model by:

$$
\begin{align*}
f(\alpha) := \lbrace \beta < \kappa : (\alpha,\beta) \in X\rbrace
\end{align*}
$$

so $f$ is also in the ground model. 
$\square$

<a name="ex15.32"></a>
## Exercise 15.32.
<i>Solution.</i> Let $g : \cf(\kappa) \to V[G]$ be the function $\alpha \mapsto f\restrictedto\kappa_\alpha$, where $\sup_{\alpha < \cf(\kappa)} \kappa_\alpha = \kappa$. Since $\kappa$ is singular, $\cf(\kappa) < \kappa$, so $g \in V$. Then $f := \bigcup_{\alpha < \cf(\kappa)} g(\alpha) \in V$. 
$\square$

<a name="ex15.33"></a>
## Exercise 15.33.
<i>Solution.</i> By Lemma 15.39, $B(P)$ is weakly $(\omega,\omega)$-distributive iff every $f : \omega \to \omega$ in $V[G]$ is dominated by some $g : \omega \to \omega$ in $V$, which we know is false by Lemma 15.30(ii). 
$\square$

<a name="ex15.34"></a>
## Exercise 15.34.
<i>Solution.</i> <u>$\implies$:</u> Assume $B$ is weakly $(\omega,\omega_1)$-distributive. Suppose for a contradiction $\omega_1$ ceases to be a cardinal in $V[G]$. Then, in $V[G]$, there exists some onto mapping $f : \omega \to \omega_1$. By Lemma 15.39, there exists a $g : \omega \to \omega_1$ in $V$ such that $g(\alpha) > f(\alpha)$ for all $\alpha$. Then in particular $g$ must be cofinal in $\omega_1$, so $\cf^V(\omega_1) = \omega$, a contradiction.

<u>$\impliedby$:</u> Assume $\omega_1$ remains a cardinal in $V[G]$. Let $f : \omega \to \omega_1$ in $V[G]$. Since $\omega_1^{V[G]} = \omega_1$, $f$ must be bounded, there exists some $\alpha < \omega_1$ such that $f(n) < \alpha$ for all $n$. Then the constant map $n \mapsto \alpha$ is in $V$, and dominates $f$. 
$\square$

<a name="ex15.35"></a>
## Exercise 15.35.
<a name="lem15.35.A"></a>
<b>Lemma 15.35.A.</b> Let $B$ be a $\lambda$-saturated complete Boolean algebra. For any $X \subseteq B$:
<ol>
<li> There exists a $Y \subseteq X$, $\vert Y\vert  < \lambda$, such that $\sum X = \sum Y$.</li>

<li> There exists a $Y \subseteq X$, $\vert Y\vert  < \lambda$, such that $\prod X = \prod Y$..</li></ol>

<i>Proof.</i> Note that all sums/products here are well-defined as $B$ is complete.
<ol>
<li> Let $x := \sum X$. Suppose $X = \lbrace x_\alpha : \alpha < \vert X\vert \rbrace$. Let $y_\alpha := x_\alpha - \sum_{\beta<\alpha} x_\beta$. Then $\lbrace y_\alpha : \alpha < \vert X\vert \rbrace$ is an antichain. Clearly $\sum_{\alpha<\vert X\vert } y_\alpha = \sum_{\alpha<\vert X\vert } x_\alpha$. Let $Y := \lbrace \alpha < \vert X\vert  : y_\alpha \neq 0\rbrace$, so we have that $\lbrace y_\alpha : \alpha < \vert X\vert \rbrace \cup \lbrace 1 - x\rbrace$ is a partition of $B$. Since $B$ is $\lambda$-saturated, $\vert Y\vert  < \lambda$. Then $\sum_{\alpha \in Y} y_\alpha = x$, and since $y_\alpha \leq x_\alpha \leq x$ for all $\alpha$, we have that $\sum_{\alpha \in Y} x_\alpha = x$.</li>

<li> Let $-X := \lbrace -x : x \in X\rbrace$. By <a href="https://clementyung.github.io/jech-solutions/chapter-7#ex7.27(ii)">Exercise 7.27(ii)</a>, we have $\prod X = -\sum (-X)$. By (i), there exists some $Y \subseteq X$, $\vert Y\vert  < \lambda$, such that $\sum (-X) = \sum (-Y)$. Then $\prod X = -\sum (-X) = -\sum (-Y) = \prod Y$.</li>
</ol> 
$\blacksquare$

<i>Solution.</i> Let $B$ be a complete Boolean algebra that is $\kappa$-generated and $\lambda$-saturated. Let $X \subseteq B$ such that $\vert X\vert  \leq \kappa$ and $X$ generates $B$. By a working similar to <a href="https://clementyung.github.io/jech-solutions/chapter-7#ex7.18">Exercise 7.18</a>, we may conclude that for all $x \in B$, there exist $X_\alpha \subseteq X$, where $\alpha < \mu$ for some cardinal $\mu$, such that:

$$
\begin{align*}
x = \sum_{\alpha < \mu} \prod X_\alpha
\end{align*}
$$

By <a href="#lem15.35.A">Lemma 15.35.A</a>, we may take $\mu < \lambda$, and $X_\alpha$ such that $\vert X_\alpha\vert  < \lambda$ for each $\alpha < \mu$. Therefore, there are $\kappa^{<\lambda}$ many possible such $\prod X_\alpha$'s, so there are $(\kappa^{<\lambda})^\mu = \kappa^{<\lambda}$ many such $\sum_{\alpha<\mu} \prod X_\alpha$. Since $\mu < \lambda$, this implies that there are $\kappa^{<\lambda}$ many such expressions of the form $\sum_{\alpha<\mu} \prod X_\alpha$, therefore $\vert B\vert  \leq \kappa^{<\lambda}$. 
$\square$

<a name="ex15.36"></a>
## Exercise 15.36.
<i>Solution.</i> By <a href="#ex15.35">Exercise 15.35</a>, we have that $\vert B\vert  \leq \aleph_0^{<\aleph_1} = 2^{\aleph_0}$. On the other hand, by <a href="https://clementyung.github.io/jech-solutions/chapter-7#ex7.32">Exercise 7.32</a> we have that $\vert B\vert  = \vert B\vert ^{\aleph_0} \geq 2^{\aleph_0}$. Therefore $\vert B\vert  = 2^{\aleph_0}$. 
$\square$

<a name="ex15.37"></a>
## Exercise 15.37.
<i>Solution.</i> Suppose $< \, \in U$ is a linear order on $A$. Let $E$ be the support of $<$, i.e. $\pi(<) = \, <$ for all $\pi \in \func{fix}(E)$.

<u>Example 15.49:</u> Pick $a,b \in A - E$, and assume WLOG that $a < b$ (as $<$ is a linear order). Let $\pi \in \func{fix}(E)$ such that $\pi(a) = b$ and $\pi(b) = a$. Then $\pi(a) \, \pi(<) \, \pi(b) \implies b < a$, a contradiction.

<u>Example 15.50:</u> We define $f : \lbrace P_n : n \in \omega\rbrace \to P$ as follows:

$$
\begin{align*}
f(P_n) := \min{P_n}
\end{align*}
$$

This is well-defined as $a_n,b_n$ are compatible for each $n \in \omega$. Then $f$ is a choice function on $\lbrace P_n : n \in \omega\rbrace$, a contradiction. 
$\square$