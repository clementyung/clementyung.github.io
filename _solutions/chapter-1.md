---
title: "1) Axioms of Set Theory"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-1
excerpt: ""
---

{% include commands.html %}

<a name="ex1.1"></a>
## Exercise 1.1.
<i>Solution.</i> $\impliedby$ is clear. For $\implies$, suppose $(a,b) = \{\{a\},\{a,b\}\} = \{\{c\},\{c,d\}\} = (c,d)$. Then $\{a\} \in \{\{c\},\{c,d\}\}$, so $\{a\} = \{c\}$ or $\{a\} = \{c,d\}$. We consider two cases.
<ol>
<li> If $c = d$, then either way we have $\{a\} = \{c\}$, so we have $a = c$. We see that in this case, $\{\{a\},\{a,b\}\} = \{\{c\}\}$. Then $\{a,b\} = \{c\} = \{a\}$, so $\{a,b\} \subseteq \{a\} \implies b = a$. Hence $a = b = c = d$.</li>

<li> If $c \neq d$, then we must have $\{a\} = \{c\}$ and $\{c\} \neq \{c,d\}$. This also implies that $\{a,b\} = \{c,d\}$. Since $a = c$, ($b = c$ or $b = d$) and $c \neq d$, we must have $b = d$.
</ol> 
$\square$

<a name="ex1.2"></a>
## Exercise 1.2.
<i>Solution.</i> If such an $X$ exists, then $X \in P(X) \subseteq X$, contradicting Axiom of Regularity (see Page 63 of the textbook). 
$\square$

<a name="ex1.3"></a>
## Exercise 1.3.
<i>Solution.</i> Let $Y := \{x \in X : x \subseteq X\}$. Since $X$ is inductive, $\emptyset \in X$ and $\emptyset \subseteq X$ trivially, so $\emptyset \in Y$. Now suppose $x \in Y \subseteq X$. Note that since $X$ is inductive, $x \cup \{x\} \in X$. Then $x \subseteq X$, and since $x \in X$ we have $\{x\} \in X$. Thus, $x \cup \{x\} \subseteq X$ and hence $x \cup \{x\} \in Y$. So $Y$ is indeed inductive.

Since $\boldsymbol{N}$ is the smallest inductive set, it follows that $\boldsymbol{N} = \{x \in \boldsymbol{N} : x \subseteq \boldsymbol{N}\}$, i.e. $\boldsymbol{N}$ is transitive. 
$\square$

<a name="ex1.4"></a>
## Exercise 1.4.
<i>Solution.</i> Let $Y := \{x \in X : x \text{ is transitive}\}$. Clearly $\emptyset$ is transitive, so $\emptyset \in Y$. Now suppose $x \in X$ and $x$ is transitive. We wish to show that $x \cup \{x\}$ is transitive, which would complete the proof.

Let $y \in x \cup \{x\}$. If $y \in x$, then $y \subseteq x \subseteq x \cup \{x\}$. Otherwise, $y \in \{x\}$ so $y = x$. Then clearly $x \subseteq x \cup \{x\}$. Thus $x \cup \{x\}$ is transitive. 
$\square$

<a name="ex1.5"></a>
## Exercise 1.5.
<i>Solution.</i> Clearly $\emptyset$ is transitive and $\emptyset \notin \emptyset$ as $\emptyset$ has no elements. Now suppose $x \in X$. In the proof of [Exercise 1.4](#ex1.4) we have already seen that $x \cup \{x\}$ is transitive. It remains to show that $x \cup \{x\} \notin x \cup \{x\}$.

Suppose not, so $x \cup \{x\} \in x \cup \{x\}$. We consider two cases. If $x \cup \{x\} \in x$, then since $x$ is transitive, $x \cup \{x\} \subseteq x$. In particular, $x \in x$, a contradiction. Otherwise, we have $x \cup \{x\} \in \{x\}$, i.e. $x \cup \{x\} = x$. But this also implies that $x \in x$, a contradiction. 
$\square$

<a name="ex1.6"></a>
## Exercise 1.6.
<i>Solution.</i> Clearly $\emptyset$ is transitive and since it has no non-empty subset, the second requirement holds trivially. Now suppose $x$ is transitive and every non-empty $z \subseteq x$ has an $\in$-minimal element. In the proof of [Exercise 1.4](#ex1.4) we have already seen that $x \cup \{x\}$ is transitive.

Let $z \subseteq x \cup \{x\}$ be non-empty. We consider two cases. If $z \subseteq x$, then by induction hypothesis on $x$ we have that $z$ has an $\in$-minimal element. Otherwise, we have $z = z' \cup \{x\}$ for some $z' \subseteq x$. Let $t \in z'$ be $\in$-minimal in $z'$. If $t$ is $\in$-minimal in $z$, then we're done. Otherwise, we must have $x \in t$. Since $t \in x$ and $x$ is transitive, we have that $x \in x$. This means that $t$ is not $\in$-minimal in $z'$, a contradiction. 
$\square$

<a name="ex1.7"></a>
## Exercise 1.7.
<i>Solution.</i> Let $n \in X$. Then $X \cap n \subseteq n$, and by [Exercise 1.6](#ex1.6) we have that $X \cap n$ has a $\in$-minimal element. Let $m \in X \cap n$ be such a $\in$-minimal element. We shall show that $m$ is the $\in$-minimal element in $X$.

Suppose not, so there exists a $m' \in X$ such that $m' \in m$. By [Exercise 1.3](#ex1.3), we have that $m = \{p \in \boldsymbol{N} : p \in m\}$. Since $m \in n$, by the same Exercise we have $p \in n$. Thus, $m' \in X \cap n$, so $m$ is not $\in$-minimal in $X \cap n$, a contradiction. 
$\square$

<a name="ex1.8"></a>
## Exercise 1.8.
<i>Solution.</i> $\emptyset$ is in the set by definition, and if $x$ is in the set then $x \cup \{x\}$ is in the set by definition (precisely because $x$ is in the set). 
$\square$

<a name="ex1.9"></a>
## Exercise 1.9.
<i>Solution.</i> This follows from that $\boldsymbol{N}$ is inductive and [Exercise 1.8](#ex1.8). 
$\square$

<a name="ex1.10"></a>
## Exercise 1.10.
<i>Solution.</i> Let $A := \{n \in \boldsymbol{N} : n \text{ is T-finite}\}$. Clearly $0 = \emptyset \in A$ as it is vacuously T-finite. Suppose $n$ is T-finite. We shall show that $n + 1$ has $n$ as its $\subseteq$-maximal element, and is hence T-finite. Let $m \in n + 1 = n \cup \{n\}$. If $m \in \{n\}$, then $m = n$ so $m \subseteq n \cup \{n\}$ immediately. If $m \in n$, then let $m' \in n$ be its $\subseteq$-maximal element. Since $n$ is transitive by [Exercise 1.4](#ex1.4), we have $m \subseteq m' \subseteq n \subseteq n + 1$. Thus $n + 1$ is T-finite. By induction ([Exercise 1.9](#ex1.9)), $A = \boldsymbol{N}$ so every $n \in \boldsymbol{N}$ is T-finite. 
$\square$

<a name="ex1.11"></a>
## Exercise 1.11.
<i>Solution.</i> Suppose $\boldsymbol{N}$ is T-finite. Let $n \in \boldsymbol{N}$ be $\subseteq$-maximal. Then $n \cup \{n\} \in \boldsymbol{N}$ and therefore $n \cup \{n\} \subseteq n$. Hence $n \in n$, contradicting [Exercise 1.4](#ex1.4). 
$\square$

<a name="ex1.12"></a>
## Exercise 1.12.
<a name="lem1.12.A"></a>
<b>Lemma 1.12.A.</b> Let $X$ be a finite set and suppose $X$ has $n + 1$ elements for some $n \in \boldsymbol{N}$. Then, for any $x_0 \in X$, we have $X - \{x_0\}$ has $n$ elements.

\begin{proof}
Let $f : X \to n + 1$ be a bijection, and fix $x_0 \in X$. Let $x' = f^{-1}(n)$. Define $g : X \to X$ by:

$$
\begin{align*}
g(x) =
\begin{cases}
x_0, &\text{if $x = x'$} \\
x', &\text{if $x = x_0$} \\
x, &\text{otherwise}
\end{cases}
\end{align*}
$$

Then $f \circ g : X \to n + 1$ is a bijection such that $(f \circ g)(x_0) = n$. Then $(f \circ g)\restrictedto X - \{x_0\} : X - \{x_0\} \to n$ is a bijection, as desired.
\end{proof}

<i>Solution.</i> Let $A = \{n \in \boldsymbol{N} : \text{If $X$ has $n$ elements then $X$ is T-finite}\}$. Clearly $0 \in A$ as the empty set is vacuously T-finite. Suppose sets with $n$ elements are T-finite.  Let $X$ be a set with $n + 1$ element, and suppose $X$ is not T-finite. Let $x_0 \in X$, so $X \setminus \{x_0\}$ has $n$ elements by [Lemma 1.12.A](#lem1.12.A). Then by induction hypothesis, $X \setminus \{x_0\}$ is T-finite, so let $x \in X \setminus \{x_0\}$ be an element $\subseteq$-maximal in $X \setminus \{x_0\}$. Since it is not $\subseteq$-maximal in $X$, we must have $x \subsetneq x_0$. But $x_0$ is not $\subseteq$-maximal either, so $x_0 \subsetneq x'$ for some $x' \in X \setminus \{x_0\}$. Then $x \subsetneq x'$, so $x$ is not $\subseteq$-maximal in $X \setminus \{x_0\}$, a contradiction. 
$\square$

<a name="ex1.13"></a>
## Exercise 1.13.
<a name="lem1.13.A"></a>
<b>Lemma 1.13.A.</b> Let $X$ be a finite set and suppose $X$ has $n$ elements for some $n \in \boldsymbol{N}$. Then, for any $x_0 \notin X$, we have $X \cup x_0$ has $n + 1$ elements.

\begin{proof}
Let $f : X \to n$ be a bijection, and fix a set $x_0$. Define $g : X \to n + 1$ by:

$$
\begin{align*}
g(x) =
\begin{cases}
n, &\text{if $x = x_0$} \\
f(x), &\text{otherwise}
\end{cases}
\end{align*}
$$

It's easy to see that $g$ is indeed a bijection as desired.
\end{proof}

<i>Solution.</i> Let $S$ be infinite and let $X$ be the set in the hint. Let $u \in X$. Since $u$ is finite and $X$ is infinite, $u \neq X$. Thus, there exists some $x \in X \setminus u$. By [Lemma 1.13.A](#lem1.13.A), $u \cup \{x\}$ has $n + 1$ and is in particular finite, so $u \cup \{x\}$. Then $u \subsetneq u \cup \{x\}$. 
$\square$

<a name="ex1.14"></a>
## Exercise 1.14.
<i>Solution.</i> The hint basically solves the problem. If $\varphi(x,p)$ is a property with parameter $p$, then for any $p$ we may define $F := \{(x,x) : \varphi(x,p)\}$ instead. 
$\square$

<a name="ex1.15"></a>
## Exercise 1.15.
<i>Solution.</i> <u>Axiom of Union:</u> If $X$ is a set, and $Y$ is a set such that $\bigcup X \subseteq Y$, then:

$$
\begin{align*}
\bigcup X = \{x \in Y : (\forall u \in x)(\exists v \in X) \, u \in v\}
\end{align*}
$$

<u>Axiom of Power Set:</u> If $X$ is a set, and $Y$ is a set such that $P(X) \subseteq Y$, then:

$$
\begin{align*}
P(X) = \{x \in Y : (\forall u \in x) \, u \in X\}
\end{align*}
$$

<u>Axiom schema of Replacement:</u> Let $F$ be a function, and fix a set $X$. Let $Y$ be such that $F(X) \subseteq Y$. Then:

$$
\begin{align*}
F(X) = \{x \in Y : (\exists u \in X) \, x = F(u)\}
\end{align*}
$$

Note that if we denote $\varphi(u,x)$ as the formula "$x = F(u)$" then $\varphi$ is a property, so we may indeed apply Axiom Schema of Separation. 
$\square$