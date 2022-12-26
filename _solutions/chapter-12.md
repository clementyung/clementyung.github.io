---
title: "12) Models of Set Theory
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-12
excerpt: ""
---

{ % include commands.html % }

<a name="ex12.1"></a>
## Exercise 12.1.
<i>Solution.</i> <b>Step 1 - Construct isomorphism $f$:</b> We define $f : \A_a \to \Ult_U\lbrace \A_x : x \in S\rbrace$ as follows: Fix any $y_x \in \A_x$ for each $x \in S - \lbrace a\rbrace$. For each $y \in \A_a$, define $g_y : S \to \prod_{x \in S} \A_x$ by stipulating that:

$$
\begin{align*}
g_y(x) =
\begin{cases}
y, &\text{if $x = a$} \\
y_x, &\text{otherwise}
\end{cases}
\end{align*}
$$

Finally, we may define $f$ by:

$$
\begin{align*}
f(y) = [g_y]
\end{align*}
$$

We now shall that $f$ is an isomorphism.

<b>Step 2 - Prove $f$ is bijective:</b> We first see that it injective, as:

$$
\begin{align*}
f(y) = f(y') &\implies [g_y] = [g_{y'}] \\
&\implies \lbrace x \in S : g_y(x) = g_{y'}(x)\rbrace \in U && \text{by \L o\'{s} Theorem} \\
&\implies g_y(a) = g_{y'}(a) \\
&\implies y = y'
\end{align*}
$$

It is also surjective, as for any $h : S \to \prod_{x \in S} \A_x$, we have $[h] = [g_{h(a)}]$, since:

$$
\begin{align*}
h(a) = g_{h(a)}(a) \implies \lbrace x \in S : h(x) = g_{h(a)}(x)\rbrace \in U \implies [h] = [g_{h(a)}]
\end{align*}
$$

<b>Step 3 - Prove $f$ is elementary:</b> We now show that it respects predicates, functions and constants. Let $P$ be a predicate symbol. Then:

$$
\begin{align*}
P^{\A}(f(x_1),\dots,f(x_1)) &\iff P^{\A}([g_{x_1}],\dots,[g_{x_n}]) \\
&\iff \lbrace x \in S : P^{\A_x}(g_{x_1}(x),\dots,g_{x_n}(x))\rbrace \in U \\
&\iff P^{\A_a}(g_{x_1}(a),\dots,g_{x_n}(a)) \\
&\iff P^{\A_a}(x_1,\dots,x_n)
\end{align*}
$$

If $F$ is a function symbol, then:

$$
\begin{align*}
F^{\A}(f(x_1),\dots,f(x_n)) &= F^{\A}([g_{x_1}],\dots,[g_{x_n}]) \\
&= [x \mapsto F^{\A_x}(g_{x_1}(x),\dots,g_{x_1}(x))] \\
&= \lbrace f : f(a) = F^{\A_a}(g_{x_1}(a),\dots,g_{x_n}(a))\rbrace \\
&= \lbrace f : f(a) = F^{\A_a}(x_1,\dots,x_n)\rbrace \\
&= [g_{F^{\A_a}(x_1,\dots,x_n)}] \\
&= f(F^{\A_a}(x_1,\dots,x_n))
\end{align*}
$$

Finally, if $c$ is a constant symbol, then:

$$
\begin{align*}
c^{\A} = [x \mapsto c^{\A_x}] = \lbrace f : f(a) = c^{\A_a}\rbrace = [g_{c^{\A_a}}] = f(c^{\A_a})
\end{align*}
$$
 
$\square$

<a name="ex12.2"></a>
## Exercise 12.2.
<i>Solution.</i> Suppose $U$ is a principal ultrafilter on the set $S$.

<b>Step 1 - Prove that $j$ is bijective:</b> We see that it is injective, as:

$$
\begin{align*}
j(x) = j(x') &\implies [c_x] = [c_{x'}] \\
&\implies \lbrace y \in S : c_x(y) = c_{x'}(y)\rbrace \in U \\
&\implies \lbrace y \in S : x = x'\rbrace \in U \\
&\implies \lbrace y \in S : x = x'\rbrace \neq \emptyset \\
&\implies x = x'
\end{align*}
$$

It is surjective, as for any $f : S \to A$, we have $[f] = [c_{f(a)}]$.

<b>Step 2 - Prove that $j$ is elementary:</b> We now show that it respects predicates, functions and constants. Let $P$ be a predicate symbol. Then:

$$
\begin{align*}
P^{\Ult_U\A}(j(x_1),\dots,j(x_1)) &\iff P^{\Ult_U\A}([c_{x_1}],\dots,[c_{x_n}]) \\
&\iff \lbrace y \in S : P^{\A}(c_{x_1}(y),\dots,g_{x_n}(y))\rbrace \in U \\
&\iff \lbrace y \in S : P^{\A}(x_1,\dots,x_n)\rbrace \in U \\
&\iff P^{\A}(x_1,\dots,x_n)
\end{align*}
$$

The proof for function and constant symbols are similar. 
$\square$

<a name="ex12.3"></a>
## Exercise 12.3.
<a name="ex12.3(i)"></a>
### Exercise 12.3(i).
<i>Solution.</i> Let $f,g,h : \kappa \to \kappa$ be three functions. Clearly $[f] \not<^\ast  [f]$, as $\lbrace \alpha \in \kappa : f(\alpha) < f(\alpha)\rbrace = \emptyset \notin U$. Since:

$$
\begin{align*}
[f] <^\ast  [g] &\iff \lbrace \alpha \in \kappa : f(\alpha) < g(\alpha)\rbrace \in U \\
[g] <^\ast  [h] &\iff \lbrace \alpha \in \kappa : g(\alpha) < h(\alpha)\rbrace \in U
\end{align*}
$$

We have that, if $[f] <^\ast  [g]$ and $[g] <^\ast  [h]$ then:

$$
\begin{align*}
\lbrace \alpha \in \kappa : f(\alpha) < h(\alpha)\rbrace \subseteq \lbrace \alpha \in \kappa : f(\alpha) < g(\alpha)\rbrace \cap \lbrace \alpha \in \kappa : g(\alpha) < h(\alpha)\rbrace \in U
\end{align*}
$$

so $[f] <^\ast  [h]$ as well. Hence, $<^\ast $ is a partial ordering.

To see that it is a linear ordering, define:

$$
\begin{align*}
X_R := \lbrace \alpha \in \kappa : f(\alpha) \; R \; g(\alpha)\rbrace
\end{align*}
$$

where $R \in \lbrace =,<,>\rbrace$. Clearly $\kappa = X_< \sqcup X_= \sqcup X_>$. Thus, we must have that exactly one of $X_<,X_=,X_>$ is in $U$, which corresponds to $[f] <^\ast  [g]$, $[f] =^\ast  [g]$ and $[f] >^\ast  [g]$ respectively. 
$\square$

<a name="ex12.3(ii)"></a>
### Exercise 12.3(ii).
<i>Solution.</i> We mimic the proof of Lemma 17.2. If $(A,<^\ast )$ was not a well-ordering, then there exists $f_i :  \kappa \to \kappa$, where $i \in \omega$, such that $[f_0] >^\ast  [f_1] >^\ast  \cdots$. For each $i$, denote:

$$
\begin{align*}
X_i := \lbrace \alpha \in \kappa : f_0(\alpha) > f_1(\alpha)\rbrace
\end{align*}
$$

Then $X_i \in U$ for all $i$. Since $U$ is $\sigma$-complete, $X := \bigcap_{i<\omega} X_i \in U$. Then for any $\alpha \in X$, we have $f_0(\alpha) > f_1(\alpha) > \cdots$, contradicting that $\kappa$ is well-ordered.

Hence, $(A,<^\ast )$ is isomorphic to its order-type. 
$\square$

<a name="ex12.3(iii)"></a>
### Exercise 12.3(iii).
<i>Solution.</i> Recall from Corollary 12.5 that $j$ is an elementary embedding. Thus, we have that $j(\alpha)$ is an ordinal for all $\alpha$. Since $j$ preserves $\in$, by transfinite induction one have that $j(\alpha) \geq \alpha$ for each $\alpha$.

On the other hand, suppose $[f] < j(\alpha)$ for some $f : \kappa \to \kappa$, then $f(\beta) < \alpha$ for almost all $\beta < \kappa$. By $\alpha$-completeness (since $\alpha < \kappa$), we have that $f(\beta) = \gamma$ for some $\gamma < \alpha$. Thus, $[f] < \alpha$, and hence $j(\alpha) \leq \alpha$. 
$\square$

<a name="ex12.3(iv)"></a>
### Exercise 12.3(iv).
<i>Solution.</i> Given a function $f : \kappa \to \kappa$, consider the property:

$$
\begin{align}
\label{eq12.3(iv).1}
\forall \gamma < \kappa[\lbrace \alpha : f(\alpha) > \gamma\rbrace \in U] \tag{12.3(iv).1}
\end{align}
$$

Note that $d(\alpha)$ is an ordinal for all $\alpha < \kappa$, so $[d]$ is an ordinal. We first note that $d$ satisfies (\ref{eq12.3(iv).1}), as $\vert \lbrace \alpha : d(\alpha) \leq \gamma\rbrace\vert  < \kappa$ and $U$ is $\kappa$-complete. Thus, $j(\gamma) = \gamma < [d]$ for all $\gamma < \kappa$, and hence $[d] \geq \kappa$.

For the latter claim, <a href="https://clementyung.github.io/jech-solutions/chapter-10#ex10.5">Exercise 10.5</a> tell us that $U$ is a normal measure iff $d$ is the least such function. Since if $\kappa = [f]$ then $f$ must satisfy the property (\ref{eq12.3(iv).1}), the equivalence follows. 
$\square$

<a name="ex12.4"></a>
## Exercise 12.4.
<i>Solution.</i> That follows from the definition of $M$ being extensional and of $\sigma^M$. 
$\square$

<a name="ex12.5"></a>
## Exercise 12.5.
<i>Solution.</i> We borrow some of the formulas which are proven to be $\Delta_0$ in Lemma 12.10.

<u>$x$ is an ordered pair:</u>

$$
\begin{align*}
\bb{\exists y \in \bigcup x}\bb{\exists z \in \bigcup x} \, z = (x,y)
\end{align*}
$$

Note that if $x = (y',z') = \lbrace \lbrace y'\rbrace,\lbrace y',z'\rbrace\rbrace$, then in the formula on RHS we may set $y = z = y'$.

<u>$x$ is an partial ordering of $y$:</u>
\begin{small}

$$
\begin{gather*}
(\forall w \in y) \, (w,w) \notin x \wedge (\forall w \in y)(\forall v \in y)(\forall u \in y) \, ((w,v) \in x \wedge (v,u) \in x \to (w,u) \in x)
\end{gather*}
$$

\end{small}

<u>$x$ is an linear ordering of $y$:</u>

$$
\begin{align*}
\text{$x$ is a partial ordering of $y$} \wedge (\forall w \in y)(\forall v \in y) \, (w,v) \in x \vee (v,w) \in x
\end{align*}
$$

<u>$x$ and $y$ are disjoint:</u>

$$
\begin{align*}
x \cap y \text{ is empty}
\end{align*}
$$

<u>$z = x \cup y$:</u>

$$
\begin{align*}
x \subseteq z \wedge y \subseteq z \wedge (\forall w \in z) \, w \in x \vee w \in y
\end{align*}
$$

<u>$y = x \cup \lbrace x\rbrace$:</u>

$$
\begin{align*}
z \in y \leftrightarrow z \in x \vee z = x
\end{align*}
$$

<u>$x$ is an inductive set:</u>

$$
\begin{align*}
\emptyset \in x \wedge (\forall w \in x) \, w \cup \lbrace w\rbrace \in x
\end{align*}
$$

<u>$f$ is a function of $X$ into $Y$:</u>

$$
\begin{align*}
\text{$f$ is a function} \wedge \dom(f) = X \wedge \ran(f) \subseteq Y
\end{align*}
$$

<u>$f$ is a one-to-one function of $X$ into $Y$:</u>

$$
\begin{align*}
\text{$f$ is a function of $X$ into $Y$} \wedge (\forall w \in X)(\forall v \in X)(f(w) = f(v) \to w = v)
\end{align*}
$$

<u>$f$ is a function of $X$ onto $Y$:</u>

$$
\begin{align*}
\text{$f$ is a function of $X$ into $Y$} \wedge (\forall w \in X)(\exists v \in Y)(v = f(w))
\end{align*}
$$

<u>$f$ is an increasing ordinal function:</u>

$$
\begin{align*}
\dom(f) \text{ is an ordinal} \wedge (\forall w \in \dom(f))(\forall v \in \dom(f))(w \in v \to f(w) \in f(v))
\end{align*}
$$

<u>$f$ is a normal function:</u>

$$
\begin{gather*}
\text{$f$ is an increasing ordinal function} \\
\wedge \\
(\forall w \in \dom(f))(w \text{ is a limit ordinal} \to ((\forall v \in f(w))(\exists u \in w) \, v \in f(u)))
\end{gather*}
$$
 
$\square$

<a name="ex12.6"></a>
## Exercise 12.6.
<a name="ex12.6(i)"></a>
### Exercise 12.6(i).
<i>Solution.</i> We have that $M \models \vert X\vert  \leq \vert Y\vert $ iff $M \models \exists f \,(f \text{ is a one-to-one function of $X$ into $Y$})$. By <a href="#ex12.5">Exercise 12.5</a>, $f$ remains a one-to-one function of $X$ into $Y$ in $V$, so $\vert X\vert  \leq \vert Y\vert $. 
$\square$

<a name="ex12.6(ii)"></a>
### Exercise 12.6(ii).
<i>Solution.</i> We have $\alpha$ is a cardinal iff:

$$
\begin{align*}
\neg (\exists f \underbrace{(\exists \beta \in \alpha)\, (\text{$f$ is a function of $\alpha$ onto $\beta$})}_{\text{$\Delta_0$ formula, by <a href="#ex12.5">Exercise 12.5</a>}})
\end{align*}
$$

Thus "$\alpha$ is a cardinal" is downward absolute, so $M \models \alpha$ is a cardinal. 
$\square$

<a name="ex12.7"></a>
## Exercise 12.7.
<i>Solution.</i> We use <a href="#lem12.7.A">Lemma 12.7.A</a>.

<u>Extensionality:</u> This follows from that $V_\alpha$ is transitive.

<u>Pairing:</u> Let $a,b \in V_\alpha$, and suppose $\rank(a) = \beta < \alpha$ and $\rank(b) = \gamma < \alpha$. Then $\rank(\lbrace a,b\rbrace) = \max\lbrace \beta,\gamma\rbrace + 1 < \alpha$ as $\alpha$ is limit, so $\lbrace a,b\rbrace \in V_\alpha$.

<u>Separation:</u> It suffices to show that $V_\alpha$ is closed under taking subsets. But this follows from that if $X \subseteq Y$ and $Y \in V_\alpha$ then $\rank(X) \leq \rank(Y) < \alpha$ so $X \in V_\alpha$.

<u>Union:</u> Let $X \in V_\alpha$, so $\rank(X) < \alpha$. By <a href="https://clementyung.github.io/jech-solutions/chapter-6#ex6.4">Exercise 6.4</a> we have $\rank\bb{\bigcup X} = \bigcup \rank(x) < \alpha$, so $\bigcup X \in V_\alpha$.

<u>Power Set:</u> Let $X \in V_\alpha$, so $\rank(X) < \alpha$. By <a href="https://clementyung.github.io/jech-solutions/chapter-6#ex6.4">Exercise 6.4</a> again, $\rank(P(X)) = \rank(X) + 1 < \alpha$, so $P(X) \in V_\alpha$. Note furthermore that $P(X) \cap V_\alpha = P(X)$, so $P(X) \cap V_\alpha = P(X)$.

<u>Choice:</u> Let $S \in V_\alpha$ be a family of sets, $\emptyset \notin S$. Note that if $\rank(S) = \beta < \alpha$, then $\rank\bb{\bigcup S} = \bigcup \beta$. If in $V$ $\AC$ holds then there exists a function $f$ on $S$ such that $f(X) \in X$ for all $X \in S$. Now since $f \subseteq S \times \bigcup S$ and we have shown that $V_\alpha$ is closed under subsets, we have $f \in S \times \bigcup S$. Note that $A \times B \subseteq P(P(A \cup B))$. 
$\square$

<a name="ex12.8"></a>
## Exercise 12.8.
<i>Solution.</i> This follows from <a href="#lem12.7.A">Lemma 12.7.A</a> and that $\omega \in V_\alpha$. 
$\square$

<a name="ex12.9"></a>
## Exercise 12.9.
<i>Solution.</i> By <a href="#ex12.7">Exercise 12.7</a>, we're left to check Replacement. Let $X \in V_\omega$ and let $F$ be a function on $V_\omega$. In the universe $V$ we have the set $Y := \lbrace F(x) : x \in X\rbrace$. By <a href="https://clementyung.github.io/jech-solutions/chapter-3#ex3.1(iv)">Exercise 3.1(iv)</a> $Y$ is finite, and since $\ran(F) \subseteq V_\omega$, $F(x)$ is finite for all $x \in X$. Thus $Y$ is hereditarily finite, and $Y \in V_\omega$. Of course $V_\omega \models Y = F(X)$. 
$\square$

<a name="ex12.10"></a>
## Exercise 12.10.
<i>Solution.</i> By <a href="https://clementyung.github.io/jech-solutions/chapter-2#ex2.4">Exercise 2.4</a> we have that $V_\omega$ does not satisfy Infinity as $\omega \notin V_\omega$. Thus, we have that Infinity is independent of $\ZFC$ minus Infinity.

Suppose it can be shown (with just $\ZFC$ minus Infinity) that existence of an infinite set is consistent. Then $\Con(\ZFC - \text{Infinity}) \to \Con(\ZFC)$. However, in every model $M$ of $\ZFC$, $V_\omega^M$ is a model of $\ZFC$ minus Infinity, so we have $\ZFC \vdash \Con(\ZFC - \text{Infinity})$. Thus $\ZFC \vdash \Con(\ZFC)$, contradicting G\"{o}del's second incompleteness theorem. 
$\square$

<a name="ex12.11"></a>
## Exercise 12.11.
<i>Solution.</i> First note that since $\omega \in V_\kappa$ and $\omega$ is countable in all models containing it, and $E \subseteq \omega \times \omega$ so $\rank(E) \leq \omega + 2$. Thus $\A \in V_\kappa$ and $V_\kappa \models$ $\A$ is countable. To see that $V_\kappa \models$ ($\A$ is a model of $\ZFC$), we simply observe that for each axiom of $\ZFC$ $\sigma$, we have $\sigma^{\omega,E}$ is $\Delta_0$ (with all parameters in $V_\kappa$), so it is transitive between $V$ and $V_\kappa$. 
$\square$

<a name="ex12.12"></a>
## Exercise 12.12.
<a name="lem12.12.A"></a>
<b>Lemma 12.12.A.</b> Let $\c{M_\gamma : \gamma < \beta}$ be an increasing sequence of elementary submodels of $\c{V_\kappa,\in}$. Let $\c{\alpha_\gamma : \gamma < \beta}$ be such that $M_\gamma \subseteq V_{\alpha_\gamma}$, and suppose $\alpha := \lim_{\gamma<\beta} \alpha_\gamma < \kappa$. Then $\c{V_\alpha,\in} \prec \c{V_\kappa,\in}$.

<i>Proof.</i> we induct on $m$ that $M_\gamma \prec_{\Sigma_m} V_\alpha \prec_{\Sigma_m} V_\kappa$, and if $\sigma$ is a $\Sigma_m$ (or $\Pi_m$) sentence such that $M_\gamma \models \sigma$ for all $\gamma$ large enough, then $V_\alpha \models \sigma$. The case $m = 0$ is trivial, as $\Delta_0$ sentences are always absolute among transitive models. Suppose this is true for $m$.
<ol>
<li> Suppose $\sigma$ is $\exists y \, \phi(x,y)$ and $V_\kappa \models \sigma$, where $\phi$ is $\Pi_m$ and $x \in V_\alpha$. Let $\gamma$ be large enough so that $x \in M_\gamma$. Then $M_\gamma \models \phi(x,y)$ as $M_\gamma \prec V_\kappa$. By induction hypothesis, $M_\gamma \prec_{\Sigma_m} V_\alpha$, so $V_\alpha \models \phi(x,y)$. Then $V_\alpha \models \exists y \, \phi(x,y)$..</li>
<li> Suppose $\sigma$ is $\forall y \, \psi(x,y)$, where $\psi$ is $\Sigma_m$ and $x \in V_\alpha$. For any $y \in V_\alpha$, we have $V_\alpha \models \psi(x,y)$ as $V_\alpha \prec_{\Sigma_m} V_\kappa$ by induction hypothesis. Thus $V_\alpha \models \forall y \, \psi(x,y)$.</li>
</ol> 
$\blacksquare$

\begin{lemma}{12.12.B}[Tarski-Vaught Criterion]

Let $\A = (A,\dots)$ and $\B = (B,\dots)$ be two structures. The following are equivalent:
<ol>
<li> $\A \prec \B$..</li>
<li> For all formulas of the form $\exists y \, \varphi(x,y)$, where $x \in A$, if $\B \models \exists y \, \varphi(x,y)$ then there exists a $y \in A$ such that $\A \models \varphi(x,y)$.</li>
</ol>

<i>Proof.</i> (i) $\implies$ (ii) is immediate. For (ii) $\implies$ (i), we first observe that (ii) implies that for all $\Sigma_n$ formulas $\varphi(x)$ and $x \in A$, we have $\A \models \varphi(x)$ iff $\B \models \varphi(x)$. Now suppose $\varphi(x)$ is $\Pi_n$. We induct on $n$. If $n = 0$, then $\varphi(x)$ is $\Delta_0$ and hence absolute. Suppose $\varphi(x)$ is $\Pi_{n+1}$, so we write $\varphi(x) = \exists y \, \psi(x,y)$, where $\psi$ is $\Sigma_n$. Since $\psi(x,y)$ is absolute by (ii), $\varphi(x)$ is downward absolute, so $\B \models \varphi(x)$ implies $\A \models \varphi(x)$. On the other hand, if $\B \not\models \varphi(x)$, then $\B \models \neg\varphi(x)$. But $\neg\varphi(x)$ is $\Sigma_{n+1}$, so $\A \models \neg\varphi(x)$. Hence $\A \not\models \varphi(x)$. 
$\blacksquare$

<i>Solution.</i> There are two things which we need to show:
<ol>
<li> (Unboundedness) If there exists an elementary submodel $\c{M,\in} \prec \c{V_\kappa,\in}$ and $M \subseteq V_\alpha$, then there exists $\alpha' > \alpha$ such that $\c{V_{\alpha'},\in} \prec \c{V_\kappa,\in}$..</li>
<li> (Closedness) If $\c{\alpha_\gamma : \gamma < \beta}$, where $\beta < \kappa$, is a sequence of ordinals such that $\c{V_{\alpha_\gamma},\in} \prec \c{V_\kappa,\in}$ for all $\gamma < \beta$, then $\c{V_\alpha,\in} \prec \c{V_\kappa,\in}$ where $\alpha := \lim_{\gamma\to\beta} \alpha_\gamma$.</li>
</ol>

Closedness follows immediately from <a href="#lem12.12.A">Lemma 12.12.A</a>, by letting $M_\gamma = V_{\alpha_\gamma}$. Then $\alpha < \kappa$ as $\kappa$ is regular.

Begin with a elementary submodel $\c{M,\in} \prec \c{V_\kappa,\in}$. Let $\alpha_0 := \sup\lbrace \rank(x) + 1 : x \in M\rbrace$. Then $\rank(x) < \kappa$ for all $x \in M$, and since $\vert M\vert  < \kappa$ and $\kappa$ is regular, $\alpha_0 < \kappa$. Then $M \subseteq V_{\alpha_0}$.

Now suppose $\alpha_n$ is defined. Let $\lbrace h_k : k < \omega\rbrace$ denote the set of all Skolem functions for $V_\kappa$. For each $h_k$, we note that for $x_1,\dots,x_m \in V_{\alpha_n}$, we have $h_k(x_1,\dots,x_m) \in V_{\alpha_n}$. Now:

$$
\begin{align*}
\rank(h_k(V_{\alpha_n})) = \sup\lbrace \rank(h_k(x_1,\dots,x_m)) + 1 : x_1,\dots,x_m \in V_{\alpha_n}\rbrace
\end{align*}
$$

Since $\alpha_n < \kappa$, we have $\beth_{\alpha_n} < \kappa$. Thus, $\rank(h_k(V_{\alpha_n}))$ is the sup of $<\beth_{\alpha_n}$ many ordinals below $\kappa$, so $\rank(h_k(V_{\alpha_n})) < \kappa$ by regularity of $\kappa$. Therefore, there exists $\alpha_{n+1} < \kappa$ such that $\bigcup_{k=0}^\infty h_k(V_{\alpha_n}) \subseteq V_{\alpha_{n+1}}$. We may also choose $\alpha_{n+1} > \alpha_n$.

<b>Claim.</b>. $\c{V_\alpha,\in} \prec \c{V_\kappa,\in}$.

<i>Proof.</i> We use Tarski-Vaught criterion (<a href="#lem12.12.B">Lemma 12.12.B</a>). Let $\exists y \, \phi(x,y)$ be an existential formula, with $x \in V_\alpha$, and suppose $V_\kappa \models \exists y \, \phi(x,y)$. Then $V_\kappa \models \phi(h_\phi(x),x)$. Now $x \in V_{\alpha_n}$ for some $n$, so $h_\phi(x) \in h(V_{\alpha_n}) \subseteq V_{\alpha_{n+1}} \subseteq V_\alpha$. Thus $V_\alpha \models \exists y \, \phi(x,y)$. 
$\blacksquare$

Thus, we have proved the unboundedness property as $\alpha > \alpha_0$. 
$\square$

<a name="ex12.13"></a>
## Exercise 12.13.
<i>Solution.</i> In this proof we shall borrow <a href="https://clementyung.github.io/jech-solutions/chapter-6#lem6.6(i).A">Lemma 6.6(i).A</a> and <a href="#lem12.7.A">Lemma 12.7.A</a>.

<u>Extensionality:</u> This is because $H_\kappa$ is transitive.

<u>Pairing:</u> Given $a,b \in H_\kappa$, we have:

$$
\begin{align*}
\vert \TC(\lbrace a,b\rbrace)\vert  = \mod{\lbrace a,b\rbrace \cup \TC(a) \cup \TC(b)} \leq \vert \lbrace a,b\rbrace\vert  + \vert \TC(a)\vert  + \vert \TC(b)\vert  < \kappa
\end{align*}
$$

so $\lbrace a,b\rbrace \in H_\kappa$.

<u>Separation:</u> It suffices to show that $V_\alpha$ is closed under taking subsets. But this follows from that $X \subseteq Y \implies \vert \TC(X)\vert  \leq \vert \TC(Y)\vert $.

<u>Union:</u> Let $X \in H_\kappa$. Observe that:

$$
\begin{align*}
\TC\bb{\bigcup X} &= \bb{\bigcup X} \cup \bigcup_{x \in \bigcup X} \TC(x) \\
&= \bb{\bigcup X} \cup \bigcup_{(\exists y \in X) \, x \in y} \TC(x) \\
&= \bb{\bigcup_{y \in X} y} \cup \bigcup_{y \in X} \bigcup_{x \in y} \TC(x)  \\
&= \bigcup_{y \in X} \bb{y \cup \bigcup_{x \in y} \TC(x)} \\
&= \bigcup_{y \in X} \TC(y)
\end{align*}
$$

Now $\vert \TC(y)\vert  < \kappa$ for all $y \in X$. Since $\vert X\vert  < \kappa$, we have that $\mod{\bigcup_{y \in X} \TC(y)} < \kappa$. Hence $\bigcup X \in H_\kappa$.

<u>Infinity:</u> Clearly $\omega \in H_\kappa$.

<u>Replacement:</u> Let $F$ be a function on $H_\kappa$ into $H_\kappa$, and let $X \in H_\kappa$. We have:

$$
\begin{align*}
\TC(F(X)) = \lbrace F(x) : x \in X\rbrace \cup \bigcup_{x \in X} \TC(F(x))
\end{align*}
$$

Since $F(x) \in H_\kappa$ for all $x \in H_\kappa$, $\vert \TC(F(x))\vert  < \kappa$. Note also that $\vert F(X)\vert  \leq \vert X\vert  < \kappa$, and therefore $\vert \TC(F(X))\vert  < \kappa$. Therefore $\TC(F(X)) \in H_\kappa$.

<u>Regularity:</u> Immediate from <a href="#lem12.7.A">Lemma 12.7.A</a>.

<u>Choice:</u> Let $S \in H_\kappa$ be a family of sets, $\emptyset \notin S$. Let $f$ be a choice function. Observe that:

$$
\begin{align*}
\TC(f) &= f \cup \bigcup_{x \in \dom(f)} \TC((x,f(x)))
\end{align*}
$$

For each $x \in \dom(f)$, we have:

$$
\begin{align*}
\TC((x,f(x)) &= \TC(\lbrace \lbrace x\rbrace,\lbrace x,f(x)\rbrace) \\
&= \lbrace \lbrace x\rbrace,\lbrace x,f(x)\rbrace\rbrace \cup \TC(\lbrace x\rbrace) \cup \TC(\lbrace x,f(x)\rbrace) \\
&= \lbrace \lbrace x\rbrace,\lbrace x,f(x)\rbrace\rbrace \cup \TC(x) \cup \TC(f(x))
\end{align*}
$$

Since $x,f(x) \in H_\kappa$, we have $\vert \TC(x)\vert  < \kappa$ and $\vert \TC(f(x))\vert  < \kappa$ for all $x \in \dom(f)$. Thus $\vert \TC((x,f(x)))\vert  < \kappa$. Furthermore, we have that $\vert f\vert  = \vert \dom(f)\vert  < \kappa$, and since $\kappa$ is regular we have that $\mod{\bigcup_{x \in \dom(f)} \TC((x,f(x)))} < \kappa$. Therefore $\vert \TC(f)\vert  < \kappa$, so $f \in H_\kappa$. 
$\square$

<a name="ex12.14"></a>
## Exercise 12.14.
<i>Solution.</i> We induct on the complexity of $\varphi$. If $\varphi$ is atomic (i.e. $x \in y$ or $x = y$), then they are in particular $\Delta_0$ and hence is reflected by all of $V_\alpha$, where $\alpha \geq \omega$. As in the hint, we have $C_{\varphi \wedge \psi} = C_\varphi \cap C_\psi$. Clearly $C_{\neg\varphi} = C_\varphi$.

We shall now show that for all $\alpha \in C_\varphi \cap K_\varphi$, then $V_\alpha$ reflects $\exists x \, \varphi$. Note that this does not imply that all such $\alpha$'s are in $C_\varphi \cap K_\varphi$ - we simply claim that there exists a closed unbounded subclass of such $\alpha$'s.

<u>$K_\psi$ is closed unbounded:</u> We note that unboundedness follows from Reflection Principle (Theorem 12.14(i)), as $M_0$ may be chosen to be arbitrarily large. To see that it is closed, let $\lbrace \alpha_\gamma : \gamma < \beta\rbrace \subseteq K_\psi$ and let $\alpha := \lim_{\gamma\to\beta} \alpha_\gamma$. Let $x_1,\dots,x_n \in V_\alpha$, and suppose $\exists x \, \varphi(x,x_1,\dots,x_n)$. If $x_i \in V_{\alpha_{\gamma_i}}$, then $x_1,\dots,x_n \in V_{\alpha'}$ where $\alpha' := \max\lbrace \alpha_1,\dots,\alpha_n\rbrace$. Since $\alpha' \in K_\psi$, we have $(\exists x \in V_{\alpha'}) \, \varphi(x,x_1,\dots,x_n)$ holds. Thus $(\exists x \in V_\alpha) \, \varphi(x,x_1,\dots,x_n)$ holds as $V_{\alpha'} \subseteq V_\alpha$.

Let $\alpha \in C_\psi \cap K_\psi$. Suppose $\exists x \, \psi(x,x_1,\dots,x_n)$ holds, where $x_1,\dots,x_n \in V_\alpha$. Since $\alpha \in K_\psi$, there exists $x' \in V_\alpha$ such that $\psi(x',x_1,\dots,x_n)$ holds. Since $\alpha \in C_\psi$, $\psi$ is reflected so $\psi^{V_\alpha}(x',x_1,\dots,x_n)$ holds. Therefore $(\exists x \, \psi)^{V_\alpha}$ holds.

Conversely suppose $V_\alpha \models \exists x \, \psi(x,x_1,\dots,x_n)$, where $x_1,\dots,x_n \in V_\alpha$. Let $x' \in V_\alpha$ such that $\psi^{V_\alpha}(x',x_1,\dots,x_n)$. Since $\alpha \in C_\psi$ we have that $\psi(x',x_1,\dots,x_n)$ holds, and therefore $\exists x \, \psi(x,x_1,\dots,x_n)$ holds.

Therefore, $V_\alpha$ reflects $\exists x \, \psi$. 
$\square$

<a name="ex12.15"></a>
## Exercise 12.15.
<i>Solution.</i> We may make small modifications to the proof of Theorem 12.15 by letting, in (12.26):

$$
\begin{align*}
C := \lbrace x \in M : \varphi(u_1,\dots,u_n,x)\rbrace
\end{align*}
$$

Then $M_i$'s constructed later remain subsets of $M$ by transitivity. The rest of the proof is verbatim. 
$\square$

<a name="ex12.16"></a>
## Exercise 12.16.
<i>Solution.</i> Again we may modify the proof of Theorem 12.15. We let, in (12.26):

$$
\begin{align*}
C := \lbrace x \in W : \varphi(u_1,\dots,u_n,x)\rbrace
\end{align*}
$$

Replace each $M_i$ with $W_\alpha$, where $\alpha$ is the least ordinal such that $M_i \subseteq W_\alpha$. The rest of the proof passes again by transitivity of $W$. 
$\square$