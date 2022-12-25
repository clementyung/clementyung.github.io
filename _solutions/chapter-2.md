---
title: "2) Ordinal Numbers"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-2
excerpt: ""
---

{% include commands.html %}

<a name="ex2.1"></a>
## Exercise 2.1.
The relation "$(P,<)$ is isomorphic to $(Q,<)$" is an equivalence relation (on the class of all partially ordered sets).

<i>Solution.</i> Suppose $f : P \to Q$ and $g : Q \to R$ are two isomorphisms.

<b>Reflexive:</b> The identity $\id : P \to P$ is clearly an isomorphism.

<b>Symmetry:</b> By definition of an isomorphism, it's easy to see if $f : P \to Q$ is an isomorphism then so is $f^{-1} : Q \to P$.

<b>Transitive:</b> Composition of isomorphisms are isomorphisms, as they remain bijective and:

$$
\begin{align*}
x < y \implies f(x) < f(y) \implies g(f(x)) < g(f(y))
\end{align*}
$$
 
$\square$

<a name="ex2.2"></a>
## Exercise 2.2.
$\alpha$ is a limit ordinal if and only if $\beta < \alpha$ implies $\beta + 1 < \alpha$, for every $\beta$.

<i>Solution.</i> Note that $\beta < \alpha$ iff $\beta + 1 \leq \alpha$.

<u>$\implies$:</u> Suppose $\beta \in \alpha$. Since $\alpha = \bigcup \alpha$, $\beta \in \gamma$ for some $\gamma \in \alpha$. Then $\beta + 1 \subseteq \gamma$. Since $\gamma \in \alpha$, $\beta + 1 \in \alpha$.

<u>$\impliedby$:</u> If $\beta \in \bigcup \alpha$, then $\beta \in \gamma$ for some $\gamma \in \alpha$. By transitivity of ordinals, $\gamma \subseteq \alpha$, so $\beta \in \alpha$. Thus, $\bigcup \alpha \subseteq \alpha$ (we have not used the hypothesis).

On the other hand, let $\beta \in \alpha$. By hypothesis, $\beta + 1 \in \alpha$, so $\beta + 1 \subseteq \bigcup\alpha$. Hence $\beta \in \bigcup\alpha$. 
$\square$

<a name="ex2.3"></a>
## Exercise 2.3.
If a set $X$ is inductive, then $X \cap \boldsymbol{\mathrm{ORD}}$ is inductive. The set $\boldsymbol{N} = \bigcap\lbrace X : \text{$X$ is inductive}\rbrace$ is the least limit ordinal $\neq 0$.

<i>Solution.</i> We shall show that if $A$ and $B$ are inductive, then so is $A \cap B$. Since $\boldsymbol{\mathrm{ORD}}$ is an inductive class, it follows that $X \cap \boldsymbol{\mathrm{ORD}}$ is also inductive.

Clearly $\emptyset \in A \cap B$. Let $x \in A \cap B$. Then since $A$ and $B$ are inductive, $x \cup \lbrace x\rbrace \in A$ and $x \cup \lbrace x\rbrace \in B$, so $x \cup \lbrace x\rbrace \in A \cap B$. Thus $A \cap B$ is inductive.

Since $\boldsymbol{N}$ is the smallest inductive set, $\boldsymbol{N} = \boldsymbol{N} \cap \boldsymbol{\mathrm{ORD}}$, i.e. $\boldsymbol{N} \subseteq \boldsymbol{\mathrm{ORD}}$. Since $\boldsymbol{N}$ is transitive by [Exercise 1.3](#ex1.3), and is well-ordered, it is an ordinal.

Finally, to see that $\boldsymbol{N}$ is a limit ordinal, suppose not, so $\boldsymbol{N} = n \cup \lbrace n\rbrace$ for some $n \in \boldsymbol{N}$. By the inductive property of $\boldsymbol{N}$, we have that $\boldsymbol{N} = n \cup \lbrace n\rbrace \in \boldsymbol{N}$, contradicting the Axiom of Regularity. 
$\square$

<a name="ex2.4"></a>
## Exercise 2.4.
(Without the Axiom of Infinity). Let $\omega = $ least limit $\alpha \neq 0$ if it exists, $\omega = \boldsymbol{\mathrm{ORD}}$ otherwise. Prove that the following statements are equivalent:
<ol>
<li> There exists an inductive set.</li>

<li> There exists an infinite set.</li>

<li> $\omega$ is a set.</li>
</ol>

\begin{hint}
For (ii) $\to$ (iii), apply Replacement to the set of all finite subsets of $X$.
\end{hint}

<i>Solution.</i> <u>(i) $\implies$ (ii):</u> If $X$ is inductive, then $\boldsymbol{N} \subseteq X$. Then there exists an injective map $\boldsymbol{N} \to X$, which is the inclusion map. Then $\mod{\boldsymbol{N}} \leq \mod{X}$, so $X$ is infinite.

<u>(ii) $\implies$ (iii):</u> Let $X$ be an infinite set. Consider the map on $\Sb{X}^{<\omega}$ (the set of all finite subsets of $X$) defined by:

$$
\begin{align*}
Y \mapsto \mod{Y}
\end{align*}
$$

This is well-defined, as $\mod{Y}$ is well-defined for finite sets without Axiom of Infinity. By Axiom of Replacement, the image of this map is a set. Since $X$ is infinite, we have that for all $n \in \omega$, there exists $Y \subseteq X$ such that $\mod{Y} = n$. Then $Y \mapsto n$, the image of this map is $\omega$. Hence $\omega$ is a set.

<u>(iii) $\implies$ (i):</u> $\omega$ is inductive by definition. 
$\square$

<a name="ex2.5"></a>
## Exercise 2.5.
If $W$ is a well-ordered set, then there exists no sequence $\c{a_n : n \in \boldsymbol{N}}$ in $W$ such that $a_0 > a_1 > a_2 > \dots$.

<i>Solution.</i> If such a sequence exists, then $\lbrace a_n : n \in \boldsymbol{N}\rbrace \subseteq \boldsymbol{N}$ has no minimal element, contradicting the definition of well-order. 
$\square$

<a name="ex2.6"></a>
## Exercise 2.6.
There are arbitrarily large limit ordinals; i.e. $\forall \alpha \, \exists \beta > \alpha \, (\beta \text{ is a limit})$.

\begin{hint}
Consider $\lim_{n \to \omega} \alpha_n$, where $\alpha_{n+1} = \alpha_n + 1$.
\end{hint}

<i>Solution.</i> For any ordinal $\alpha$, consider the sequence $\alpha_0 := \alpha$ and $\alpha_{n+1} := \alpha_n + 1$. Let $\beta := \lim_{n \to \omega} \alpha_n$. Then $\beta$ is a limit of a (strictly) increasing sequence of ordinals, and is hence a limit ordinal (as $\bigcup\beta = \beta$). 
$\square$

<a name="ex2.7"></a>
## Exercise 2.7.
Every normal sequence $\c{\gamma_\alpha : \alpha \in \boldsymbol{\mathrm{ORD}}}$ has arbitrarily large <b>fixed points</b>, i.e. $\alpha$ such that $\gamma_\alpha = \alpha$.

\begin{hint}
Let $\alpha_{n+1} = \gamma_{\alpha_n}$, and $\alpha = \lim_{n \to \omega} \alpha_n$.
\end{hint}

<i>Solution.</i> For any $\alpha_0 \in \boldsymbol{\mathrm{ORD}}$, define $\alpha_{n+1} = \gamma_{\alpha_n}$ as in the hint. Let $\alpha = \lim_{n \to \omega} \alpha_n$. Then, by normality of the sequence:

$$
\begin{align*}
\gamma_\alpha = \lim_{n \to \omega} \gamma_{\alpha_n} = \lim_{n \to \omega} \alpha_{n+1} = \alpha
\end{align*}
$$
 
$\square$

<a name="ex2.8"></a>
## Exercise 2.8.
For all $\alpha,\beta$ and $\gamma$:

<a name="lem2.8.A"></a>
<b>Lemma 2.8.A.</b> If $\beta$ is a limit ordinal, then so are $\alpha + \beta$, $\alpha \cdot \beta$ and $\alpha^\beta$.

<i>Proof.</i> Let $F(\alpha,\beta)$ denote $\alpha + \beta$, $\alpha \cdot \beta$ or $\alpha^\beta$. In all three cases, we have $F(\alpha,\beta) = \lim_{\xi \to \beta} F(\alpha,\xi)$. Since $F(\alpha,\beta)$ is a limit ordinal iff $F(\alpha,\beta) = \lim_{\delta \to F(\alpha,\beta)} \delta$, it suffices to show that for all $\delta < F(\alpha,\beta)$, there exists some $\xi < \beta$ such that $\delta \leq F(\alpha,\xi$). But this is obviously true, for if $\delta > F(\alpha,\xi)$ for all $\xi < \beta$ then $\delta \geq \lim_{\xi \to \beta} F(\alpha,\xi) = F(\alpha,\beta)$ by definition. 
$\blacksquare$

<a name="ex2.8(i)"></a>
### Exercise 2.8(i).
$\alpha \cdot (\beta + \gamma) = \alpha \cdot \beta + \alpha \cdot \gamma$.

<i>Solution.</i> We induct on $\gamma$. For $\gamma = 0$, we have:

$$
\begin{align*}
\alpha \cdot (\beta + 0) = \alpha \cdot \beta = \alpha \cdot \beta + \alpha \cdot 0
\end{align*}
$$

Suppose $\gamma = \delta + 1$ and $\alpha \cdot (\beta + \delta) = \alpha \cdot \beta + \alpha \cdot \delta$. Then:

$$
\begin{align*}
\alpha \dot (\beta + (\delta + 1)) &= \alpha \dot (\beta + (\delta + 1)) \\
&= \alpha \cdot ((\beta + \delta) + 1) \\
&= \alpha \cdot (\beta + \delta) + \alpha \\
&= (\alpha \cdot \beta + \alpha \cdot \delta) + \alpha && \text{by induction hypothesis} \\
&= \alpha \cdot \beta + (\alpha \cdot \delta + \alpha) \\
&= \alpha \cdot \beta + \alpha \cdot (\delta + 1)
\end{align*}
$$

If $\gamma$ is a limit ordinal, then note that $\beta + \gamma$ is also a limit ordinal by [Lemma 2.8.A](https://clementyung.github.io/jech-solutions/chapter-2#lem2.8.A). Thus:

$$
\begin{align*}
\alpha \cdot (\beta + \gamma) &= \alpha \cdot \lim_{\xi \to \gamma} (\beta + \xi) \\
&= \lim_{\xi \to \gamma} \alpha \cdot (\beta + \xi) \text{} && \text{as $\beta + \gamma$ is limit} \\
&= \lim_{\xi \to \gamma} (\alpha \cdot \beta + \alpha \cdot \xi) && \text{by induction hypothesis} \\
&= \alpha \cdot \beta + \lim_{\xi \to \gamma} \alpha \cdot \xi &&\text{as $\alpha \cdot \gamma$ is limit, by [Lemma 2.8.A](https://clementyung.github.io/jech-solutions/chapter-2#lem2.8.A)} \\
&= \alpha \cdot \beta + \alpha \cdot \gamma
\end{align*}
$$
 
$\square$

<a name="ex2.8(ii)"></a>
### Exercise 2.8(ii).
$\alpha^{\beta + \gamma} = \alpha^\beta \cdot \alpha^\gamma$.

<i>Solution.</i> We induct on $\gamma$. For $\gamma = 0$, we have:

$$
\begin{align*}
\alpha^\beta \cdot \alpha^0 = \alpha^\beta \cdot 1 = \alpha^\beta = \alpha^{\beta + 0}
\end{align*}
$$

Suppose $\gamma = \delta + 1$ and $\alpha^{\beta+\gamma} = \alpha^\beta \cdot \alpha^\gamma$. Then:

$$
\begin{align*}
\alpha^{\beta + (\delta + 1)} &= \alpha^{(\beta + \delta) + 1} \\
&= \alpha^{\beta + \delta} \cdot \alpha \\
&= (\alpha^\beta \cdot \alpha^\delta) \cdot \alpha && \text{by induction hypothesis} \\
&= \alpha^\beta \cdot (\alpha^\delta \cdot \alpha) \\
&= \alpha^\beta \cdot \alpha^{\delta+1}
\end{align*}
$$

Suppose $\gamma$ is a limit ordinal. Then $\alpha^\gamma$ and $\alpha^{\beta+\gamma}$ is a limit ordinal, so:

$$
\begin{align*}
\alpha^{\beta+\gamma} &= \lim_{\xi \to \gamma} \alpha^{\beta+\xi} \\
&= \lim_{\xi \to \gamma} \alpha^\beta \cdot \alpha^\xi && \text{by induction hypothesis} \\
&= \alpha^\beta \cdot \lim_{\xi \to \gamma} \alpha^\xi && \text{as $\alpha^\gamma$ is a limit ordinal} \\
&= \alpha^\beta \cdot \alpha^\gamma
\end{align*}
$$
 
$\square$

<a name="ex2.8(iii)"></a>
### Exercise 2.8(iii).
$(\alpha^\beta)\gamma = \alpha^{\beta\cdot\gamma}$.

<i>Solution.</i> We induct on $\gamma$. If $\gamma = 0$, then:

$$
\begin{align*}
\alpha^{\beta \cdot 0} = \alpha^0 = 1 = (\alpha^\beta)^0
\end{align*}
$$

If $\gamma = \delta + 1$, then:

$$
\begin{align*}
(\alpha^\beta)^{\delta + 1} &= (\alpha^\beta)^\delta \cdot \alpha^\beta \\
&= \alpha^{\beta \cdot \delta} \cdot \alpha^\beta && \text{by induction hypothesis} \\
&= \alpha^{\beta \cdot \delta + \beta} && \text{by [Exercise 2.8(ii)](https://clementyung.github.io/jech-solutions/chapter-2#ex2.8(ii))} \\
&= \alpha^{\beta \cdot (\delta + 1)}
\end{align*}
$$

If $\gamma$ is a limit ordinal, then:

$$
\begin{align*}
(\alpha^\beta)^\gamma &= \lim_{\xi \to \gamma} (\alpha^\beta)^\xi \\
&= \lim_{\xi \to \gamma} \alpha^{\beta\cdot\xi} && \text{by induction hypothesis} \\
&= \alpha^{\beta \cdot \gamma} &&\text{as $\beta \cdot \gamma$ is limit, and therefore so is $\alpha^{\beta \cdot \gamma}$}
\end{align*}
$$
 
$\square$

<a name="ex2.9"></a>
## Exercise 2.9.
<a name="ex2.9(i)"></a>
### Exercise 2.9(i).
Show that $(\omega + 1) \cdot 2 \neq \omega \cdot 2 + 1 \cdot 2$.

<i>Solution.</i> We first note that:

$$
\begin{align*}
1 + \omega = \sup_{n < \omega} (1 + n) = \omega
\end{align*}
$$

Now we have $(\omega + 1) \cdot 2 = \omega + 1 + \omega + 1 = \omega + \omega + 1 = \omega \cdot 2 + 1$. By Lemma 2.25(i), we have $\omega \cdot 2 + 1 < \omega \cdot 2 + 2$. 
$\square$

<a name="ex2.9(ii)"></a>
### Exercise 2.9(ii).
Show that $(\omega \cdot 2)^2 \neq \omega^2 \cdot 2^2$.

<i>Solution.</i> Observe that:

$$
\begin{align*}
2 \cdot \omega = \sup_{n < \omega} 2 \cdot n = \omega
\end{align*}
$$

We have $(\omega \cdot 2)^2 = \omega \cdot 2 \cdot \omega \cdot 2 = \omega \cdot \omega \cdot 2 = \omega^2 \cdot 2$. By Lemma 2.25(iii), we have that $\omega^2 \cdot 2 < \omega^2 \cdot 4$. 
$\square$

<a name="ex2.10"></a>
## Exercise 2.10.
If $\alpha < \beta$ then $\alpha + \gamma \leq \beta + \gamma$, $\alpha \cdot \gamma \leq \beta \cdot \gamma$, and $\alpha^\gamma \leq \beta^\gamma$.

<i>Solution.</i> We induct on $\gamma$.

<u>$\alpha + \gamma \leq \beta + \gamma$:</u> If $\gamma = 0$ then this follows from $\alpha < \beta$. If $\gamma = \delta + 1$, then by Lemma 2.25(i) we have that:

$$
\begin{align*}
\alpha + \delta \leq \beta + \delta \implies \alpha + \delta + 1 \leq \beta + \delta + 1 \implies \alpha + \gamma \leq \beta + \gamma
\end{align*}
$$

If $\gamma$ is a limit ordinal, then:

$$
\begin{align*}
\alpha + \gamma &= \lim_{\xi \to \gamma} (\alpha + \xi) \\
&\leq \lim_{\xi \to \gamma} (\beta + \xi) && \text{by induction hypothesis} \\
&= \beta + \gamma
\end{align*}
$$

<u>$\alpha \cdot \gamma \leq \beta \cdot \gamma$:</u> If $\gamma = 0$ then $\alpha \cdot 0 = 0 = \beta \cdot 0$. If $\gamma = \delta + 1$, then:

$$
\begin{align*}
\alpha \cdot (\delta + 1) &= \alpha \cdot \delta + \alpha \\
&\leq \beta \cdot \delta + \alpha && \text{by above and induction hypothesis} \\
&\leq \beta \cdot \delta + \beta && \text{by $\alpha < \beta$ and Lemma 2.25(i)} \\
&= \beta \cdot (\delta + 1)
\end{align*}
$$

If $\gamma$ is a limit ordinal, then:

$$
\begin{align*}
\alpha \cdot \gamma &= \lim_{\xi \to \gamma} \alpha \cdot \xi \\
&\leq \lim_{\xi \to \gamma} \beta \cdot \xi && \text{by induction hypothesis} \\
&= \beta \cdot \gamma
\end{align*}
$$

<u>$\alpha^\gamma \leq \beta^\gamma$:</u> If $\gamma = 0$ then $\alpha^0 = 1 = \beta^0$. If $\gamma = \delta + 1$ then by above and Lemma 2.25:

$$
\begin{align*}
\alpha^{\delta+1} &= \alpha^\delta \cdot \alpha \\
&\leq \beta^\delta \cdot \alpha && \text{by above and induction hypothesis} \\
&\leq \beta^\delta \cdot \beta && \text{by $\alpha < \beta$ and Lemma 2.25(iii)} \\
&= \beta^{\delta+1}
\end{align*}
$$

If $\gamma$ is a limit ordinal, then:

$$
\begin{align*}
\alpha^\gamma &= \lim_{\xi \to \gamma} \alpha^\xi \\
&\leq \lim_{\xi \to \gamma} \beta^\xi && \text{by induction hypothesis} \\
&= \beta^\gamma
\end{align*}
$$
 
$\square$

<a name="ex2.11"></a>
## Exercise 2.11.
Find $\alpha$, $\beta$, $\gamma$ such that:

<a name="ex2.11(i)"></a>
### Exercise 2.11(i).
$\alpha < \beta$ and $\alpha + \gamma = \beta + \gamma$.

<i>Solution.</i> As we saw in the proof of [Exercise 2.9(i)](https://clementyung.github.io/jech-solutions/chapter-2#ex2.9(i)), $0 < 1$ but $0 + \omega = \omega = 1 + \omega$. 
$\square$

<a name="ex2.11(ii)"></a>
### Exercise 2.11(ii).
$\alpha < \beta$ and $\alpha \cdot \gamma = \beta \cdot \gamma$.

<i>Solution.</i> As we saw in the proof of [Exercise 2.9(ii)](https://clementyung.github.io/jech-solutions/chapter-2#ex2.9(ii)), $1 < 2$ but $1 \cdot \omega = \omega = 2 \cdot \omega$. 
$\square$

<a name="ex2.11(iii)"></a>
### Exercise 2.11(iii).
$\alpha < \beta$ and $\alpha^\gamma = \beta^\gamma$.

<i>Solution.</i> $2 < 3$ but:

$$
\begin{align*}
2^\omega = \sup_{n < \omega} 2^n = \omega = \sup_{n < \omega} 3^n = 3^\omega
\end{align*}
$$
 
$\square$

<a name="ex2.12"></a>
## Exercise 2.12.
Let $\varepsilon_0 = \lim_{n \to \omega} \alpha_n$ where $\alpha_0 = \omega$ and $\alpha_{n+1} = \omega^{\alpha_n}$ for all $n$. Show that $\varepsilon_0$ is the least ordinal $\varepsilon$ such that $\omega^\varepsilon = \varepsilon$.

<i>Solution.</i> We first show that $\omega^{\varepsilon_0} = \varepsilon_0$. Indeed:

$$
\begin{align*}
\omega^{\varepsilon_0} = \lim_{n \to \omega} \omega^{\alpha_n} = \lim_{n \to \omega} \alpha_{n+1} = \varepsilon_0
\end{align*}
$$

Now suppose $\varepsilon$ is another ordinal such that $\omega^\varepsilon = \varepsilon$. Note that $\varepsilon \neq 0$, as $\omega^0 = 1 \neq 0$. Thus, $\varepsilon \geq \omega \alpha_0$. If $\varepsilon \geq \alpha_n$, then by [Exercise 2.10](https://clementyung.github.io/jech-solutions/chapter-2#ex2.10):

$$
\begin{align*}
\alpha_{n+1} = \omega^{\alpha_n} \leq \omega^{\varepsilon} = \varepsilon
\end{align*}
$$

So $\varepsilon \geq \alpha_n$ for all $n$. Thus $\varepsilon$ is an upper bound of the sequence $\c{\alpha_n : n \in \omega}$, so $\varepsilon_0 \leq \varepsilon$. 
$\square$

<a name="ex2.13"></a>
## Exercise 2.13.
\begin{definition}
A limit ordinal $\gamma > 0$ is called <b>indecomposable</b> if there exist no $\alpha < \gamma$ and $\beta < \gamma$ such that $\alpha + \beta = \gamma$.
\end{definition}

A limit ordinal $\gamma > 0$ is indecomposable if and only if $\alpha + \gamma = \gamma$ for all $\alpha < \gamma$ if and only iff $\gamma = \omega^\alpha$ for some $\alpha$.

<i>Solution.</i> Call those definitions (i), (ii) and (iii) respectively.

<u>(i) $\implies$ (ii):</u> Let $\alpha < \gamma$. By Lemma 2.25(ii), there exists some $\delta$ such that $\alpha + \delta = \gamma$. Since $\alpha$ is indecomposable, $\delta \geq \gamma$. If $\delta > \gamma$, then by Lemma 2.25(i) and [Exercise 2.10](https://clementyung.github.io/jech-solutions/chapter-2#ex2.10) we have $\alpha + \delta > \alpha + \gamma \geq \gamma$. Thus $\delta = \gamma$.

<u>(ii) $\implies$ (i):</u> For $\alpha < \gamma$ and $\beta < \gamma$, by Lemma 2.25(i) we have $\alpha + \beta < \alpha + \gamma = \gamma$.

<u>(ii) $\implies$ (iii):</u> By Cantor's Normal Form (Theorem 2.26), we may write:

$$
\begin{align*}
\gamma = \omega^{\beta_1} \cdot k_1 + \dots + \omega^{\beta_n} \cdot k_n
\end{align*}
$$

where $\gamma \geq \beta_1 > \cdots > \beta_n$, and $k_1,\dots,k_n$ are non-zero natural numbers. Observe that:

$$
\begin{align*}
\gamma + \gamma &= \omega^{\beta_1} \cdot k_1 + \dots + \omega^{\beta_n} \cdot k_n + \gamma \\
&= \omega_{\beta_1} + (\omega^{\beta_1} \cdot (k_1 - 1) + \dots + \omega^{\beta_n} \cdot k_n + \gamma) \\
&= \omega^{\beta_1} + \gamma
\end{align*}
$$

as $\omega^{\beta_1} \cdot (k_1 - 1) + \dots + \omega^{\beta_n} \cdot k_n < \gamma$ by uniqueness of Cantor's Normal Form. Thus $\gamma = \omega^{\beta_1}$ (i.e. $n = 1$ and $k_1 = 1$).

<u>(iii) $\implies$ (ii):</u> We induct on $\beta$ where $\gamma = \omega^\beta$. If $\beta = 0$, then $\omega^0 = 1$, so the only $\alpha < \gamma$ is $\alpha = 0$, in which then of course $0 + \omega^\beta = \omega^\beta$.

If $\beta = \delta + 1$, then for $\alpha < \gamma$ we write its Cantor's Normal Form $\alpha = \omega^{\beta_1} \cdot k_1 + \dots + \omega^{\beta_n} \cdot k_n$. Since $\alpha < \gamma$, $\beta_1 < \delta + 1$ so $\beta_1 \leq \delta$. Then:

$$
\begin{align*}
\alpha + \omega^{\delta+1} &= \omega^{\beta_1} \cdot k_1 + \dots + \omega^{\beta_n} \cdot k_n + \omega^\delta \cdot \omega \\
&\leq \omega^\delta \cdot (k_1 + \dots + k_n) + \omega^\delta \cdot \omega \\
&= \omega^\delta \cdot (k_1 + \dots + k_n + \omega) \\
&= \omega^\delta \cdot \omega \\
&= \omega^{\delta+1}
\end{align*}
$$

If $\beta$ is a limit ordinal, then for $\alpha < \omega^\beta$ we have that $\alpha < \omega^\xi$ for some $\xi < \beta$. By induction hypothesis, $\alpha + \omega^\xi = \omega^\xi$. Thus we have that $\omega^\beta = \lim_{\xi \to \beta} (\alpha + \omega^\xi) = \lim_{\xi \to \beta} \omega^\xi = \omega^\beta$ for $\alpha < \omega^\beta$. 
$\square$

<a name="ex2.14"></a>
## Exercise 2.14.
If $E$ is a well-founded relation on $P$, then there is no sequence $\c{a_n : n \in \boldsymbol{N}}$ in $P$ such that $a_1 \; E \; a_0$, $a_2 \; E \; a_1$, $a_3 \; E \; a_2$, $\dots$.

<i>Solution.</i> Suppose such a sequence exists. Consider $X := \lbrace a_n : n \in \boldsymbol{N}\rbrace \subseteq P$. Since $E$ is well-founded, $X$ has some $E$-minimal element, which is $a_n$ for some $n \in \boldsymbol{N}$. Yet $a_n \; E \; a_{n+1}$, a contradiction. 
$\square$

<a name="ex2.15"></a>
## Exercise 2.15.
<b>(Well-Founded Recursion).</b> Let $E$ be a well-founded relation on a set $P$, and let $G$ be a function. Then there exists a function $F$ such that for all $x \in P$, $F(x) = G(x,F\restrictedto\lbrace y \in P : y \; E \; x\rbrace)$.

<i>Solution.</i> The proof of Theorem 2.15 can be mimicked. Define the function $F$ such that $F(x) = X$ iff there is a sequence $\c{a_y : y \; E \; x}$ (where $a_x := G(\c{a_y : y \; E \; x})$) such that:
<ol>
<li> $(\forall y \; E \; x) \, a_y = F(\c{a_z : z \; E \; y})$.</li>

<li> $x = G(\c{a_y : y \; E \; x})$.</li>
</ol>
The proof of Theorem 2.15 can be followed similarly to show that the $F$ above works. 
$\square$