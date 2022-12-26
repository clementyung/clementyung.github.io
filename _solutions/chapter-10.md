---
title: "10) Measurable Cardinals"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-10
excerpt: ""
---

{% include commands.html %}

<a name="ex10.1"></a>
## Exercise 10.1.
<i>Solution.</i> Suppose $M$ is Lebesgue measurable. Then, by translational invariance, $\mu(M_q) = \mu(M)$ for all $q \in \Q$. The $M_q$'s are pairwise disjoint, for if $x \in M_q \cap M_p$ then $x = x_1 + q = x_2 + p$ for some $x_1,x_2 \in M$, so $x_1 - x_2 = p - q \in \Q$, contradicting the construction of $M$.

The identity $[0,1] \subseteq \bigcup\lbrace M_q : q \in \Q \cap [-1,1]\rbrace \subseteq [-1,2]$ is easy to see. This implies that:

$$
\begin{align*}
\mu([0,1]) = 1 \leq \sum_{q \in \Q} \mu(M_q) = \sum_{i=1}^\infty \mu(M) \leq 3 = \mu([-1,2])
\end{align*}
$$

This is a contradiction - if $\mu(M) = 0$, then $\sum_{i=1}^\infty \mu(M) = 0$, violating the identity. If $\mu(M) > 0$, then $\sum_{i=1}^\infty \mu(M) = +\infty$, also violating the identity. 
$\square$

<a name="ex10.2"></a>
## Exercise 10.2.
<i>Solution.</i> We follow the hint and prove their first claim.

<b>Claim.</b>. Let $X \in T$ be such that $\mu(Y \cap X) \neq 0$. Let $X_1,X_2$ be two immediate successors of $X$. Then either $\mu(Y \cap X_1) = 0$ or $\mu(Y \cap X_2) = 0$.

Of course, one of them must be non-zero as well.

<i>Proof.</i> For $i \in \lbrace 1,2\rbrace$, we note that:

$$
\begin{align*}
\mu(Y \cap X_i) &\leq \mu(f_{-1}(Z) \cap f_{-1}(f"(X_i))) \\
&= \mu(f_{-1}(Z \cap f"(X_i))) \\
&= \nu(Z \cap f"(X_i))
\end{align*}
$$

We observe that $f"(X_1) \cap f"(X_2) = \emptyset$. Indeed, if $\alpha \in f"(X_1) \cap f"(X_2)$, then $\alpha = f(x_1) = f(x_2)$ for some $x_i \in X_i$. This implies that $x_i \in Z_\alpha$, so $X_i \cap Z_\alpha \neq \emptyset$ for each $i$. Now since $Z_\alpha = \bigcap b_\alpha$, and $b_\alpha$ can't be extended further by definition, we must have (since $X_i \in T$) $X_i \cap Z_\alpha \neq \emptyset \implies Z_\alpha \subseteq X_i$, for otherwise we may split it further to $Z_\alpha \cap X_i$ and $Z_\alpha - X_i$. This implies that $X_1 \cap X_2 \supseteq Z_\alpha \neq \emptyset$, a contradiction. 
$\blacksquare$

<b>Claim.</b>. For each $\alpha < \omega_1$, there is a unique $X \in \L_\alpha(T)$ (the $\alpha^\text{th}$ level of $T$) such that $\mu(Y \cap X) \neq 0$.

<i>Proof.</i> We induct on $\alpha$. The base case is trivial (we only have $X = S$), and the successor case was exactly the previous claim. For the limit case, let $X_\beta$ be the $X$ for the $\beta^\text{th}$ level, and let $X_\alpha = \bigcap_{\beta < \alpha}$. We have $\alpha$ is countable, so we have that:

$$
\begin{align*}
\mu(Y \cap X_\alpha) = \mu\bb{Y \cap \bigcap_{\beta < \alpha} X_\beta} = \inf_{\beta < \alpha} \mu(Y \cap X_\beta) = \inf_{\beta < \alpha}\mu(Y) = \mu(Y)
\end{align*}
$$
 
$\blacksquare$
Then $\lbrace X_\alpha : \alpha < \omega_1\rbrace$ forms a branch in $T$ of height $\omega_1$, which is a contradiction (proof of Theorem 10.9(i) explains why this is a contradiction). 
$\square$

<a name="ex10.3"></a>
## Exercise 10.3.
<a name="lem10.3.A"></a>
<b>Lemma 10.3.A.</b> Let $\mu$ be an atomless measure on $S$. For all $\epsilon > 0$ and $X \subseteq S$, there exists $Y \subseteq S$ such that $0 < \mu(Y) < \epsilon$.

<i>Proof.</i> By the atomless property, we may split $X$ into $X_0 \sqcup X_1$ such that $0 < \mu(X_0) \leq \frac{\mu(X)}{2}$ or $0 < \mu(X_1) \leq \frac{\mu(X)}{2}$. Assume the former. Then, repeat the argument to give $X_{0,0} \subseteq X_0$ such that $0 < \mu(X_{0,0}) \leq \frac{\mu(X_0)}{2} \leq \frac{\mu(X)}{4}$. Repeat this inductively and we have that for all $n \in \bb{N}$, there exists a $Y_n \subseteq X$ such that $\mu(Y_n) \leq \frac{\mu(X)}{2^n}$. Now choose $n$ large enough so that $\frac{\mu(X)}{2^n} < \epsilon$. 
$\blacksquare$

<i>Solution.</i> The construction in the hint is clear except for the successor case. Given $S_\alpha$ with $\mu(S_\alpha) \geq \frac{1}{2}$, assume $\mu(S_\alpha) = \frac{1}{2} + \epsilon > \frac{1}{2}$ (otherwise we have found our $Z$). By <a href="#lem10.3.A">Lemma 10.3.A</a>, there exists $S_{\alpha+1}' \subseteq S_\alpha$ such that $0 < \mu(S_{\alpha+1}') < \epsilon$. Let $S_{\alpha+1} := S_\alpha - S_{\alpha+1}'$, and we have that $\frac{1}{2} \leq \mu(S_{\alpha+1}) < \mu(S_\alpha)$.

Now the sequence $\c{x_\alpha : \alpha < \omega_1}$, where $x_\alpha := \mu(S_\alpha)$, is a strictly decreasing $\omega_1$-sequence that stay above $\frac{1}{2}$. Since it is uncountable, it must stay constant after some stage $\alpha < \omega+1$. Then $x_\alpha = \frac{1}{2}$, for if $x_\alpha > \frac{1}{2}$ then $x_{\alpha+1} < x_\alpha$ by construction. 
$\square$

<a name="ex10.4"></a>
## Exercise 10.4.
<i>Solution.</i> Let $\mu,U$ be a two-valued measure/ultrafilter over a set $X$.

<u>$\implies$:</u> Let $\lbrace X_\alpha : \alpha < \kappa\rbrace \subseteq U$. Then $\mu(X_\alpha) = 1$, and since $\mu$ is two-valued, $\mu(X - X_\alpha) = 0$ for all $\alpha$. Then, by $\kappa$-additivity of $\mu$:

$$
\begin{align*}
0 = \sum_{\alpha < \kappa} \mu(X - X_\alpha) = \mu\bb{\bigcup_{\alpha<\kappa} X - X_\alpha} = \mu\bb{X - \bigcap_{\alpha < \kappa} X_\alpha}
\end{align*}
$$

So $\mu\bb{\bigcap_{\alpha<\kappa} X_\alpha} = 1$, hence $\bigcap_{\alpha<\kappa} X_\alpha \in U$. Thus $U$ is $\kappa$-complete.

<u>$\impliedby$:</u> Let $\lbrace X_\alpha : \alpha < \kappa\rbrace$ be subsets of $X$. If $\mu(X_\alpha) = 1$ for some $\alpha < \kappa$, then $X_\alpha \in U$ so $\bigcup_{\alpha<\kappa} X_\alpha \in U$ by upward closure. Hence $\mu\bb{\bigcup_{\alpha<\kappa} X_\alpha} = 1$.

If $\mu(X_\alpha) = 0$ for all $\alpha < \kappa$, then $\mu(X - X_\alpha) = 1$ for all $\alpha < \kappa$. By $\kappa$-completeness of $U$, we have that $\bigcap_{\alpha < \kappa} X - X_\alpha = X - \bigcup_{\alpha < \kappa} X_\alpha \in U$. Thus, $\mu\bb{X - \bigcup_{\alpha < \kappa} X_\alpha} = 1$, so $\mu\bb{\bigcup_{\alpha < \kappa} X_\alpha} = 0 = \sum_{\alpha < \kappa} \mu(X_\alpha)$.
l\end{solution}

<a name="ex10.5"></a>
## Exercise 10.5.
<i>Solution.</i> By "least" here we refer to the ordering $<$ on the set of all functions on $\kappa$ in the proof of Theorem 10.20. That is:

$$
\begin{align*}
f < g \iff \lbrace \alpha < \kappa : f(\alpha) < g(\alpha)\rbrace \in U
\end{align*}
$$

<u>$\implies$:</u> Suppose $f < d$ under the ordering above. Let $X = \lbrace \alpha < \kappa : f(\alpha) < d(\alpha) = \alpha\rbrace \in U$. Then $f$ is regressive on $X$, so by <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.8">Exercise 8.8</a> there exists $Y \in U$ such that $f\restrictedto Y$ is constant, say $f(\alpha) = \gamma$ for all $\alpha \in Y$. $\lbrace \alpha < \kappa : f(\alpha) > \gamma\rbrace \supseteq X^c$, so $\lbrace \alpha < \kappa : f(\alpha) > \gamma\rbrace \notin U$.

<u>$\impliedby$:</u> Suppose $d$ is the least function with the said property. We shall show that (by <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.8">Exercise 8.8</a> again) every regressive function on a set of measure one is constant on a set of measure one. We note that if $f$ is regressive on $X \in U$, then $f < d$ via the set $X$. Since $d$ is the least function with said property, there exists $\gamma < \kappa$ such that $\lbrace \alpha : f(\alpha) \leq \gamma\rbrace \in U$. Since $U$ is $\kappa$-complete, we have that for some $\delta < \gamma$, $\lbrace \alpha : f(\alpha) = \delta\rbrace \in U$. Thus $f$ is constant on a set of measure one. 
$\square$

<a name="ex10.6"></a>
## Exercise 10.6.
<i>Solution.</i> For $n \in \omega$, we call a function $f : [\kappa]^n \to \kappa$ <b>regressive</b> if for all $x \in [\kappa]^{<\omega}$, $f(x) = 0$ or $f(x) < \min{x}$. The case where $f : [\kappa]^{<\omega} \to \kappa$. Note that for $n = 1$, $f$ is regressive in this sense iff $f$ is regressive as in Definition 8.6.

Following the hint we mimic the proof of Theorem 10.22. It suffices to show that for each $n \in \omega$ there is a $H_n \in D$ such that $f$ is constant on $[H_n]$, so $\bigcap_{n=1}^\infty H_n$ is homogeneous for $f$ (which is inside $D$ as it is $\kappa$-complete).

We induct on $n$ that for every $g : [\kappa]^n \to \kappa$, we have $g$ is constant on $[H]^n$ for some $H \in D$. The case $n = 1$ follows from <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.8">Exercise 8.8</a>. Suppose this holds for the case of $n$. Given $f : [\kappa]^{n+1} \to \kappa$ regressive, define $f_\alpha : [\kappa - \lbrace \alpha\rbrace]^n \to n$ by $f_\alpha(s) := f(\lbrace \alpha\rbrace \cup s)$.

By induction hypothesis and the regressive property, let $X_\alpha \in D$ such that $f_\alpha$ has the constant value $\gamma_\alpha < \alpha$ on $[X_\alpha]^n$. Let $X := \bigtriangle_{\alpha<\kappa} X_\alpha$, which is in $D$ by normality. We then see that if $\delta < \alpha_1 < \dots < \alpha_n$ are in $X$, then $\lbrace \alpha_1,\dots,\alpha_n\rbrace \in [X_\delta]^n$, so:

$$
\begin{align*}
f(\lbrace \delta,\alpha_1,\dots,\alpha_n\rbrace) = f_\delta(\lbrace \alpha_1,\dots,\alpha_n\rbrace) = \gamma_\delta
\end{align*}
$$

Now the map $\alpha \mapsto \gamma_\alpha$ is regressive on $X \in D$, so by <a href="https://clementyung.github.io/jech-solutions/chapter-8#ex8.8">Exercise 8.8</a> there exists some $H \subseteq X$, $H \in D$ $\gamma$ such that $\gamma_\alpha = \gamma$ for all $\alpha \in H$. Then $H$ is the homogeneous set we want. 
$\square$

<a name="ex10.7"></a>
## Exercise 10.7.
<i>Solution.</i> Let $D$ be a normal measure on $\kappa$. Define a measure $U$ on $P_\kappa(\kappa)$ by stipulating that for $P \subseteq P_\kappa(\kappa)$:

$$
\begin{align*}
P \in U \iff P \cap \kappa \in D
\end{align*}
$$

We shall show that $D$ is a normal measure on $P_\kappa(\kappa)$.

<u>$U$ is a filter:</u> Clearly $U$ is upward closed. We have $P_\kappa(\kappa) \in U$ as $P_\kappa(\kappa) \cap \kappa = \kappa \in D$. Finally, if $P,Q \in U$, then $P \cap \kappa,Q \cap \kappa \in D$, so $(P \cap Q) \cap \kappa \in D$ and therefore $P \cap Q \in U$.

<u>$U$ extends $F$:</u> It suffices to show that $\hat{P} \in U$ for all $P \in P_\kappa(\kappa)$. Indeed, given $P \in P_\kappa(\kappa)$, we have that $\lbrace \alpha < \kappa : \alpha \geq \sup{P}\rbrace$ has bounded complement (note that $\sup{P} < \kappa$ by regularity), so $\lbrace \alpha < \kappa : \alpha \geq \sup{P}\rbrace \in D$. Clearly $\lbrace \alpha < \kappa : \alpha \geq \sup{P}\rbrace \subseteq \hat{P} \cap \kappa$, so $\hat{P} \in U$.

<u>$U$ is an ultrafilter:</u> If $P \subseteq P_\kappa(\kappa)$ and $P \notin U$, then $P \cap \kappa \notin D$. This implies that:

$$
\begin{align*}
\kappa - P \cap \kappa = P_\kappa(\kappa) \cap \kappa - P \cap \kappa = (P_\kappa(\kappa) - P) \cap \kappa \in D
\end{align*}
$$

so $P_\kappa(\kappa) - P \in U$.

<u>$U$ is normal:</u> Given a sequence $\c{P_\alpha : \alpha < \kappa}$ of subsets of $P_\kappa(\kappa)$, we have:

$$
\begin{align*}
\bigtriangle_{\alpha < \kappa} P_\alpha \in U &\iff \bb{\bigtriangle_{\alpha < \kappa} P_\alpha} \cap \kappa \in D \\
&\iff \ss{x \in P_\kappa(\kappa) : x \in \bigcap_{\beta \in x} P_\beta} \cap \kappa \in D \\
&\iff \ss{\alpha \in \kappa : x \in \bigcap_{\beta \in \alpha} P_\beta} \in D \\
&\iff \bigtriangle_{\alpha < \kappa} (P_\alpha \cap \kappa) \in D
\end{align*}
$$

in which the last assertion holds by normality of $D$. 
$\square$