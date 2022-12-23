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
<i>Solution.</i> Suppose $f : P \to Q$ and $g : Q \to R$ are two isomorphisms.
    
<b>Reflexive:</b> The identity $\id : P \to P$ is clearly an isomorphism.
    
<b>Symmetry:</b> By definition of an isomorphism, it's easy to see if $f : P \to Q$ is an isomorphism then so is $f^{-1} : Q \to P$.
    
<b>Transitive:</b> Composition of isomorphisms are isomorphisms, as they remain bijective and:
$$
  x < y \implies f(x) < f(y) \implies g(f(x)) < g(f(y))
$$

<a name="ex2.2"></a>
## Exercise 2.2.
Note that $\beta < \alpha$ iff $\beta + 1 \leq \alpha$.

<u>$\implies$:</u> Suppose $\beta \in \alpha$. Since $\alpha = \bigcup \alpha$, $\beta \in \gamma$ for some $\gamma \in \alpha$. Then $\beta + 1 \subseteq \gamma$. Since $\gamma \in \alpha$, $\beta + 1 \in \alpha$.
    
<u>$\impliedby$:</u> If $\beta \in \bigcup \alpha$, then $\beta \in \gamma$ for some $\gamma \in \alpha$. By transitivity of ordinals, $\gamma \subseteq \alpha$, so $\beta \in \alpha$. Thus, $\bigcup \alpha \subseteq \alpha$ (we have not used the hypothesis).
    
On the other hand, let $\beta \in \alpha$. By hypothesis, $\beta + 1 \in \alpha$, so $\beta + 1 \subseteq \bigcup\alpha$. Hence $\beta \in \bigcup\alpha$.

<a name="ex2.3"></a>
## Exercise 2.3.
<i>Solution.</i>  We shall show that if $A$ and $B$ are inductive, then so is $A \cap B$. Since $\ORD$ is an inductive class, it follows that $X \cap \ORD$ is also inductive.
    
Clearly $\emptyset \in A \cap B$. Let $x \in A \cap B$. Then since $A$ and $B$ are inductive, $x \cup \{x\} \in A$ and $x \cup \{x\} \in B$, so $x \cup \{x\} \in A \cap B$. Thus $A \cap B$ is inductive.
    
Since $\bm{N}$ is the smallest inductive set, $\bm{N} = \bm{N} \cap \ORD$, i.e. $\bm{N} \subseteq \ORD$. Since $\bm{N}$ is transitive by Exercise \ref{ex1.3}, and is well-ordered, it is an ordinal. 
    
Finally, to see that $\bm{N}$ is a limit ordinal, suppose not, so $\bm{N} = n \cup \{n\}$ for some $n \in \bm{N}$. By the inductive property of $\bm{N}$, we have that $\bm{N} = n \cup \{n\} \in \bm{N}$, contradicting the Axiom of Regularity.

<a name="ex2.4"></a>
## Exercise 2.4.
<i>Solution.</i> <u>(i) $\implies$ (ii):</u> If $X$ is inductive, then $\bm{N} \subseteq X$. Then there exists an injective map $\bm{N} \to X$, which is the inclusion map. Then $|\bm{N}| \leq |X|$, so $X$ is infinite.
    
<u>(ii) $\implies$ (iii):</u> Let $X$ be an infinite set. Consider the map on $[X]^{<\omega}$ (the set of all finite subsets of $X$) defined by:

$$
\begin{align*}
    Y \mapsto |Y|
\end{align*}
$$

This is well-defined, as $|Y|$ is well-defined for finite sets without Axiom of Infinity. By Axiom of Replacement, the image of this map is a set. Since $X$ is infinite, we have that for all $n \in \omega$, there exists $Y \subseteq X$ such that $|Y| = n$. Then $Y \mapsto n$, the image of this map is $\omega$. Hence $\omega$ is a set.
    
<u>(iii) $\implies$ (i):</u> $\omega$ is inductive by definition.

<a name="ex2.5"></a>
## Exercise 2.5.
<i>Solution.</i>  If such a sequence exists, then $\{a_n : n \in \bm{N}\} \subseteq \bm{N}$ has no minimal element, contradicting the definition of well-order.

<a name="ex2.6"></a>
## Exercise 2.6.
<i>Solution.</i>  For any ordinal $\alpha$, consider the sequence $\alpha_0 := \alpha$ and $\alpha_{n+1} := \alpha_n + 1$. Let $\beta := \lim_{n \to \omega} \alpha_n$. Then $\beta$ is a limit of a (strictly) increasing sequence of ordinals, and is hence a limit ordinal (as $\bigcup\beta = \beta$).

<a name="ex2.7"></a>
## Exercise 2.7.
<i>Solution.</i>  For any $\alpha_0 \in \ORD$, define $\alpha_{n+1} = \gamma_{\alpha_n}$ as in the hint. Let $\alpha = \lim_{n \to \omega} \alpha_n$. Then, by normality of the sequence:

$$
\begin{align*}
        \gamma_\alpha = \lim_{n \to \omega} \gamma_{\alpha_n} = \lim_{n \to \omega} \alpha_{n+1} = \alpha
\end{align*}
$$

<a name="ex2.8"></a>
## Exercise 2.8.
<a name="lem2.8.A"></a>
If $\beta$ is a limit ordinal, then so are $\alpha + \beta$, $\alpha \cdot \beta$ and $\alpha^\beta$.

<i>Proof.</i> Let $F(\alpha,\beta)$ denote $\alpha + \beta$, $\alpha \cdot \beta$ or $\alpha^\beta$. In all three cases, we have $F(\alpha,\beta) = \lim_{\xi \to \beta} F(\alpha,\xi)$. Since $F(\alpha,\beta)$ is a limit ordinal iff $F(\alpha,\beta) = \lim_{\delta \to F(\alpha,\beta)} \delta$, it suffices to show that for all $\delta < F(\alpha,\beta)$, there exists some $\xi < \beta$ such that $\delta \leq F(\alpha,\xi$). But this is obviously true, for if $\delta > F(\alpha,\xi)$ for all $\xi < \beta$ then $\delta \geq \lim_{\xi \to \beta} F(\alpha,\xi) = F(\alpha,\beta)$ by definition.

<a name="ex2.8(i)"></a>
# Exercise 2.8(i).
<i>Solution.</i> We induct on $\gamma$. For $\gamma = 0$, we have:
    \begin{align*}
        \alpha \cdot (\beta + 0) = \alpha \cdot \beta = \alpha \cdot \beta + \alpha \cdot 0
    \end{align*}
    Suppose $\gamma = \delta + 1$ and $\alpha \cdot (\beta + \delta) = \alpha \cdot \beta + \alpha \cdot \delta$. Then:
    \begin{align*}
        \alpha \dot (\beta + (\delta + 1)) &= \alpha \dot (\beta + (\delta + 1)) \\
        &= \alpha \cdot ((\beta + \delta) + 1) \\
        &= \alpha \cdot (\beta + \delta) + \alpha \\
        &= (\alpha \cdot \beta + \alpha \cdot \delta) + \alpha && \text{by induction hypothesis} \\
        &= \alpha \cdot \beta + (\alpha \cdot \delta + \alpha) \\
        &= \alpha \cdot \beta + \alpha \cdot (\delta + 1) 
    \end{align*}
    If $\gamma$ is a limit ordinal, then note that $\beta + \gamma$ is also a limit ordinal by Lemma \ref{lem2.8.A}. Thus:
    \begin{align*}
        \alpha \cdot (\beta + \gamma) &= \alpha \cdot \lim_{\xi \to \gamma} (\beta + \xi) \\
        &= \lim_{\xi \to \gamma} \alpha \cdot (\beta + \xi) \text{} && \text{as $\beta + \gamma$ is limit} \\
        &= \lim_{\xi \to \gamma} (\alpha \cdot \beta + \alpha \cdot \xi) && \text{by induction hypothesis} \\
        &= \alpha \cdot \beta + \lim_{\xi \to \gamma} \alpha \cdot \xi &&\text{as $\alpha \cdot \gamma$ is limit, by Lemma \ref{lem2.8.A}} \\
        &= \alpha \cdot \beta + \alpha \cdot \gamma
    \end{align*} 

<a name="ex2.9"></a>
## Exercise 2.9.
<i>Solution.</i>  

<a name="ex2.10"></a>
## Exercise 2.10.
<i>Solution.</i>  

<a name="ex2.11"></a>
## Exercise 2.11.
<i>Solution.</i>  

<a name="ex2.12"></a>
## Exercise 2.12.
<i>Solution.</i>  

<a name="ex2.13"></a>
## Exercise 2.13.
<i>Solution.</i>  

<a name="ex2.14"></a>
## Exercise 2.14.
<i>Solution.</i>  

<a name="ex2.15"></a>
## Exercise 2.15.
<i>Solution.</i>  