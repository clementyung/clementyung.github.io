---
title: "19)Iterated Ultrapowers and $L[U]$
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-19
excerpt: ""
---

{ % include commands.html % }

    <a name="ex19.1"></a>
## Exercise 19.1.
<i>Solution.</i> Let $M$ be the direct limit. Following the hint, it suffices to show that $M \models i_{n,\omega}(\kappa) > i_{n+1,\omega}(\kappa)$. By elementarity and commutativity of $i_{m,n}$'s it suffices to show that $M_{n+1} \models i_{n,n+1}(\kappa) > \kappa$. Since $i_{n,n+1} = j\restrictedto M_{n+1}$, this is equivalent to asserting that $j(\kappa) > \kappa$, which we know is true. 
$\square$

<a name="ex19.2"></a>
## Exercise 19.2.
<i>Solution.</i> This is the Representation Lemma 19.13 for $\alpha = m$ and $\beta = n$. 
$\square$

<a name="ex19.3"></a>
## Exercise 19.3.
<i>Solution.</i> The proof is identical to that of the standard \L o\'{s}'s Theorem (Theorem 12.3), except we replace all functions by functions of finite support. 
$\square$

<a name="ex19.4"></a>
## Exercise 19.4.
<i>Solution.</i> Fix $n \geq 0$. In the notation of the proof of Lemma 19.11, let $F_n$ be a function on $\kappa^n$ defined by $F_{n+1}(t) = (d_{n+1})_{(t)}$ for all $t \in \kappa^n$. Then $\Ult_{D_n} = \Ult^{(n)} \models [F_n]_{D_n}$ is a function with domain $\kappa^{(n)}$, and let $\tilde{d}_n$ be this function. Furthermore, observe that for all $t \in \kappa^n$ we have that $F_{n+1}(t)(\alpha) = \alpha$ for all $\alpha < \kappa$. Thus, we have that:

$$
\begin{align*}
&\iffbreak \forall^\ast  t \in D_n \, \lbrace \alpha < \kappa : F_{n+1}(t)(\alpha) = \alpha\rbrace \in D \\
&\iff \Ult_{D_n} \models \lbrace \alpha < \kappa^{(n)} : [F_n]_{U_n}(\alpha) = \alpha\rbrace \in D^{(n)} \\
&\iff \Ult_{D_n} \models \lbrace \alpha < \kappa^{(n)} : \tilde{d}_{n+1}(\alpha) = \alpha\rbrace \in D^{(n)}
\end{align*}
$$

Let $d : \kappa^{(n)} \to \kappa^{(n)}$ be the diagonal function in $\Ult_{D_n}$. It follows that in $\Ult^{(n+1)}$, $[\tilde{d}_{n+1}]_{D^{(n)}} = [d]_{U^{(n)}}$. But since $\Ult^{(n)} \models D^{(n)}$ is a normal measure, we have that $\Ult^{(n+1)} \models [d]_{U^{(n)}} = \kappa^{(n+1)}$. Thus $[d_{n+1}]_{D^{n+1}} = [\tilde{d}_{n+1}]_{D^{(n)}} = \kappa^{(n+1)}$, as desired. 
$\square$

<a name="ex19.5"></a>
## Exercise 19.5.
<i>Solution.</i> For $n \geq 0$, define the symbol $\forall^{*(n)}\alpha$ by such that for all formulas $\varphi(\alpha)$, we have:

$$
\begin{align*}
\forall^{*(n)}\alpha \, \varphi(\alpha) \iff \lbrace \alpha < \kappa^{(n)} : \varphi(\alpha)\rbrace \in U^{(n)}
\end{align*}
$$

Note that $\forall^\ast $ and $\forall^{*(0)}$ have the same meaning. Now definition of $D_n$ and Lemma 17.5, we have:

$$
\begin{align*}
&\iffbreak A \in D_n \\
&\iff \forall^{*(0)} \alpha_0 \, \forall^{*(0)} \alpha_1 \, \ldots \, \forall^{*(0)} \alpha_{n-1} \, (\alpha_0,\dots,\alpha_{n-1}) \in A \\
&\iff \lbrace \alpha_0 < \kappa : \forall^{*(0)} \alpha_1 \, \ldots \, \forall^{*(0)} \alpha_{n-1} \, (\alpha_0,\dots,\alpha_{n-1}) \in A\rbrace \in D \\
&\iff \kappa \in j\bb{\lbrace \alpha_0 < \kappa : \forall^{*(0)} \alpha_1 \, \ldots \, \forall^{*(0)} \alpha_{n-1} \, (\alpha_0,\dots,\alpha_{n-1}) \in A\rbrace} \\
&\iff \kappa \in \lbrace \alpha_0 < \kappa^{(1)} : \forall^{*(1)} \alpha_1 \, \ldots \, \forall^{*(1)} \alpha_{n-1} \, (\alpha_0,\dots,\alpha_{n-1}) \in i_{0,1}(A)\rbrace \\
&\iff \forall^{*(1)} \alpha_1 \, \ldots \, \forall^{*(1)} \alpha_{n-1} \, (\kappa,\alpha_1,\dots,\alpha_{n-1}) \in i_{0,1}(A) \\
&\iff \lbrace \alpha_1 < \kappa^{(1)} : \forall^{*(1)} \alpha_2 \, \ldots \, \forall^{*(1)} \alpha_{n-1} \, (\kappa,\alpha_1,\dots,\alpha_{n-1}) \in i_{0,1}(A)\rbrace \in D^{(1)}  \\
&\iff \kappa^{(1)} \in j\bb{\lbrace \alpha_1 < \kappa^{(1)} : \forall^{*(1)} \alpha_2 \, \ldots \, \forall^{*(1)} \alpha_{n-1} \, (\kappa,\alpha_1,\dots,\alpha_{n-1}) \in i_{0,1}(A)\rbrace} \\
&\iff \kappa^{(1)} \in \lbrace \alpha_1 < \kappa^{(2)} : \forall^{*(2)} \alpha_2 \, \ldots \, \forall^{*(2)} \alpha_{n-1} \, (\kappa,\alpha_1,\alpha_2,\dots,\alpha_{n-1}) \in i_{0,2}(A)\rbrace \\
&\iff \forall^{*(2)} \alpha_2 \, \ldots \, \forall^{*(2)} \alpha_{n-1} \, (\kappa,\kappa^{(1)},\alpha_2,\dots,\alpha_{n-1}) \in i_{0,2}(A) \\
&\iff \ldots
\end{align*}
$$

We may repeat this for all $i < n$, and ultimately conclude that:

$$
\begin{align*}
A \in D_n \iff (\kappa,\kappa^{(1)},\dots,\kappa^{(n-1)}) \in i_{0,n}(A)
\end{align*}
$$

Since $i_{0,n} = j_{D_n}$, the result follows. 
$\square$

<a name="ex19.6"></a>
## Exercise 19.6.
<i>Solution.</i> Note that by "$[B]^n$", the author was referring to unordered tuples, i.e. the set of all $(\alpha_1,\dots,\alpha_n)$ such that $\alpha_i \in B$ for all $1 \leq i \leq n$, and $\alpha_1 < \ldots < \alpha_n$, as it was noted (preceding Lemma 19.11) that $D_n$ concentrates on increasing sequences.

If $n = 1$, then $D_1 = D$ and so let $B = A$. Otherwise, suppose $A \in D_{n+1}$ where $n \geq 1$. By <a href="#ex19.5">Exercise 19.5</a>, we have that:

$$
\begin{align*}
A \in D_{n+1} &\iff (\kappa,\kappa^{(1)},\dots,\kappa^{(n)}) \in i_{0,n+1}(A) \\
&\iff \kappa \in \lbrace \alpha_1 < \kappa^{(1)} : (\alpha_1,\kappa^{(1)},\dots,\kappa^{(n)}) \in i_{0,n+1}(A)\rbrace \\
&\iff \kappa \in j\bb{\lbrace \alpha_1 < \kappa : (\alpha_1,\kappa,\dots,\kappa^{(n-1)}) \in i_{0,n}(A)\rbrace} \\
&\iff \lbrace \alpha_1 < \kappa : (\alpha_1,\kappa,\dots,\kappa^{(n-1)}) \in i_{0,n}(A)\rbrace \in D
\end{align*}
$$

Thus, we let $B_1 := \lbrace \alpha_1 < \kappa : (\alpha_1,\kappa,\dots,\kappa^{(n-1)}) \in i_{0,n}(A)\rbrace$, which is in $D$. Now for each $\alpha_1 \in B_1$, we have:

$$
\begin{align*}
&\iffbreak (\alpha_1,\kappa,\dots,\kappa^{(n-1)}) \in i_{0,n}(A) \\
&\iff \kappa \in \lbrace \alpha_2 < \kappa^{(1)} : (\alpha_1,\alpha_2,\kappa^{(1)},\dots,\kappa^{(n-1)}) \in i_{0,n}(A)\rbrace \\
&\iff \kappa \in j\bb{\lbrace \alpha_2 < \kappa : (\alpha_1,\alpha_2,\kappa,\dots,\kappa^{(n-2)}) \in i_{0,n-1}(A)\rbrace} \\
&\iff \lbrace \alpha_2 < \kappa : (\alpha_1,\alpha_2,\kappa,\dots,\kappa^{(n-2)}) \in i_{0,n-1}(A)\rbrace \in D
\end{align*}
$$

Thus, we let $B_1^{(\alpha_1)} := \lbrace \alpha_2 < \kappa : (\alpha_1,\alpha_2,\kappa,\dots,\kappa^{(n-2)}) \in i_{0,n-1}(A)\rbrace$, which is also in $D$. If $\alpha_1 \notin B_1$, let $B_1^{(\alpha_1)} := \kappa$. Since $D$ is normal, we may let:

$$
\begin{align*}
B_2 &:= B_1 \cap \bigtriangle_{\alpha_1 < \kappa} B_1^{(\alpha_1)} \\
&= \ss{\alpha_2 \in B_1 : \alpha_2 \in \bigcap_{\alpha_1 < \alpha_2} B_1^{(\alpha_1)}} \\
&= \ss{\alpha_2 \in B_1 : (\forall \alpha_1 \in B_1 \cap \alpha_2) \, (\alpha_1,\alpha_2,\kappa,\dots,\kappa^{(n-2)}) \in i_{0,n-1}(A)}
\end{align*}
$$

So $B_2 \in D$. If $n = 1$, then $B_2 = \lbrace \alpha_2 \in B_1 : (\forall \alpha_1 \in B_1 \cap \alpha_2) \, (\alpha_1,\alpha_2) \in A\rbrace$. Thus, if $(\alpha_1,\alpha_2) \in [B_2]^2$ and $\alpha_1 < \alpha_2$, then since $B_2 \subseteq B_1$ by definition we have that $(\alpha_1,\alpha_2) \in A$. If $n > 1$, then we may repeat the working - for each $\alpha_1,\alpha_2 \in B_2$,we have:

$$
\begin{align*}
&\iffbreak (\alpha_1,\alpha_2,\kappa,\dots,\kappa^{(n-2)}) \in i_{0,n-1}(A) \\
&\iff \lbrace \alpha_3 < \kappa : (\alpha_1,\alpha_2,\alpha_3,\kappa,\dots,\kappa^{(n-3)}) \in i_{0,n-2}(A)\rbrace \in D
\end{align*}
$$

So we let $B_2^{(\alpha_2)} := \lbrace \alpha_3 < \kappa : (\alpha_1,\alpha_2,\alpha_3,\kappa,\dots,\kappa^{(n-3)}) \in i_{0,n-2}(A)\rbrace$, which is also in $D$. Let $B_3 := B_2 \cap \bigtriangle_{\alpha_2<\kappa} B_2^{(\alpha_2)}$, and we have that:

$$
\begin{align*}
B_3 := \lbrace \alpha_3 \in B_2 : (\forall \alpha_2 \in B_2 \cap \alpha_3)(\forall \alpha_1 \in B_2 \cap \alpha_2) \, (\alpha_1,\alpha_2,\alpha_3,\kappa,\dots,\kappa^{(n-3)}) \in A\rbrace
\end{align*}
$$

Again, if $n = 2$ then $[B_3]^3 \subseteq A$ by definition. This can be repeated for any $n$. 
$\square$

<b>Remark.</b>. Compare with Theorem 10.22.

<a name="ex19.7"></a>
## Exercise 19.7.
<i>Solution.</i> By Lemma 19.21, there exists a $\delta < \kappa^{(\omega)}$ such that $U = \lbrace X \subseteq \kappa : \delta \in i_{0,\omega}(X)\rbrace$, and there exists an $N$ such that for all $X \subseteq \kappa$, $j_U(X) = i_{0,N}(X)$. As in the hint, we consider two cases.

<b>Case 1 - $\delta = \kappa^{(n)}$ for some $n$:</b> Then $N = n$, Observe that:

$$
\begin{align*}
\kappa^{(n)} \in i_{0,\omega}(X) &\iff i_{n+1,\omega}(\kappa^{(n)}) \in i_{0,\omega}(X) \\
&\iff i_{n+1,\omega}(\kappa^{(n)}) \in i_{n+1,\omega}(i_{0,n+1}(X)) \\
&\iff \kappa^{(n)} \in i_{0,n+1}(X) \\
\end{align*}
$$

Let $\phi(\kappa,D,X)$ be a formula asserting that $\kappa \in j^{(0)}(X)$. We see that $j^{(0)}$ is the elementary embedding given by the ultrapower from $D$, and similarly $\Ult^{(n)}$ thinks that $j^{(n)}$ is the elementary embedding given by the ultrapower from $i_{0,n}(D)$. Thus, in $\Ult^{(n)}$, the sentence $\phi(i_{0,n}(\kappa),i_{0,n}(D),i_{0,n}(X))$ must mean that $i_{0,n}(\kappa) \in j^{(n)}(i_{0,n}(X))$. Thus by elementarity, $\kappa \in j^{(0)}(X)$ holds iff $\Ult^{(n)} \models i_{0,n}(\kappa) \in j^{(n)}(i_{0,n}(X))$, which is true when $N = n$. Hence $U = D$, so this case is excluded.

<b>Case 2 - $\delta \neq \kappa^{(n)}$ for all $n$:</b> In this case we have that $\kappa^{(n-1)} < \delta < \kappa^{(n)}$ for some $n$ (as $\delta < \kappa^{(\omega)} = \sup_{n < \omega} \kappa^{(n)}$). Note that since $\kappa^{(n-1)} < \delta < j_U(\kappa)$, $N \geq n$. We have $\delta \in \Ult_{D_n}$, so $\delta = [g]_{D_n}$ for some $g : \kappa^n \to \kappa$. Let $f : \kappa \to \kappa$ be as defined in the hint. We shall show that $[f]_U < [d]_U$.

Since $\kappa^{(n-1)} < \delta$ and $\kappa^{(n-1)} = [d_n]_{D_n}$ (see <a href="#ex19.4">Exercise 19.4</a>), there exists an $A \in D_n$ such that for all $(\alpha_1,\dots,\alpha_n) \in A$, $g(\alpha_1,\dots,\alpha_n) > d(\alpha_1,\dots,\alpha_n) = \alpha_n$. On the other hand, we have $f(g(\alpha_1,\dots,\alpha_n)) =$ the least $\alpha$ such that for some $\beta_1 < \dots < \beta_{n-1} < \alpha$, $g(\beta_1,\dots,\beta_{n-1},\alpha) \geq g(\alpha_1,\dots,\alpha_{n-1},\alpha_n)$. Then clearly such $\alpha$ is at most $\alpha_n$, so for all $(\alpha_1,\dots,\alpha_n) \in A$:

$$
\begin{align*}
f(g(\alpha_1,\dots,\alpha_n)) \leq \alpha_n < g(\alpha_1,\dots,\alpha_n)
\end{align*}
$$

In other words, we have that $(j_{D_n}(f))(\delta) < \delta$. Since $\delta < \kappa^{(n)}$, $N \geq n$ and $j_{D_n} = i_{0,n}$, we have that $(j_U(f))(\delta) = (i_{0,N}(f))(\delta) < \delta$, so $f(\xi) < \xi$ for almost all $\xi$ (mod $U$). Hence $[f]_U < [d]_U$.

<b>$U$ does not extend the closed unbounded filter:</b> We shall find a closed unbounded subset $C \subseteq \kappa$ that does not lie in $U$. Define a function $h : \kappa \to \kappa$ by stipulating that:

$$
\begin{align*}
h(\alpha) := \sup\lbrace g(\alpha_1,\dots,\alpha_n) + 1 : \alpha_1 < \ldots < \alpha_n < \alpha\rbrace
\end{align*}
$$

Clearly $h$ is a normal function, so the set $C$ of fixed points of $h$ is closed unbounded. Then we see that for any $\alpha \in C$ and $(\alpha_1,\dots,\alpha_n) \in \kappa^n$, either $\alpha_n \geq \alpha$ (which gives $g(\alpha_1,\dots,\alpha_n) > \alpha_n \geq \alpha$), or $\alpha_n < \alpha$ (which gives $g(\alpha_1,\dots,\alpha_n) < h(\alpha) = \alpha$. In other words, $g(\alpha_1,\dots,\alpha_n) \neq \alpha$ for all $\alpha_1 < \dots < \alpha_n$ in $\kappa^n$.

Now if $U$ extends the closed unbounded filter, then we have that on $C \in U$ so $C$ witnesses that $[f]_U \notin i_{0,N}(C)$. However by above, we have that $C \in U$ iff $\delta = [f]_U \in i_{0,N}(C)$, a contradiction. 
$\square$

<a name="ex19.8"></a>
## Exercise 19.8.
<i>Solution.</i> Let $U := \lbrace X \in P^M(\kappa) : \kappa \in j(X)\rbrace$. The proof that $U$ is a nonprincipal $\kappa$-complete $M$-ultrafilter is verbatim to the proof in Lemma 17.3, and that $U$ is normal follows from the remark preceding Lemma 17.5. Thus, it remains to show that it is iterable, i.e. it satisfies (19.17).

Let $\mathcal{X} := \c{X_\alpha : \alpha < \kappa} \in M$. Then $j(\mathcal{X}) = \c{j(X_\alpha) : \alpha < j(\kappa)} \in N$, where $j(X_\alpha)$ is some subset of $j(\kappa)$ for $\alpha \geq \kappa$. Note that this implies that $\c{j(X_\alpha) : \alpha < \kappa} \in N$ (by restriction of the sequence to domain $\kappa$, as $\kappa \in N$). Thus, $Y := \lbrace \alpha < \kappa : \kappa \in j(X_\alpha)\rbrace \in N$, so $Y \in P^N(\kappa)$. Since $P^N(\kappa) = P^M(\kappa)$, $Y \in M$, as desired. 
$\square$

<a name="ex19.9"></a>
## Exercise 19.9.
<i>Solution.</i> Let $\c{f_n : n < \omega}$, where $f_n : \kappa^\alpha \to M$ are functions in $M$ of finite support $E_n \subseteq \alpha$, such that $\lbrace t \in \kappa^\alpha : f_{n+1}(t) \in f_n(t)\rbrace \in U_\alpha$ for all $n$. Let $\beta$ be the order-type of $\bigcup_{n=0}^\infty E_n$, and let $\sigma : \beta \to \bigcup_{n=0}^\infty E_n$ be an order-preserving one-to-one correspondence. Let $F_n := \sigma_{-1}(E_n)$.

For each $n$, we define $g_n : \kappa^\beta \to M$ by stipulating that for all $t \in \kappa^\beta$:

$$
\begin{align*}
g_n(t) = f_n(t'), \; \text{where $t' \in \kappa^\alpha$ and $t'\restrictedto E_n = t\restrictedto F_n$}
\end{align*}
$$

Then by the remarks preceding Lemma 19.13, we have that:

$$
\begin{align*}
\lbrace t \in \kappa^\beta : g_{n+1}(t) \in g_n(t)\rbrace \in U_\beta \iff \lbrace t \in \kappa^\alpha : f_{n+1}(t) \in f_n(t)\rbrace \in U_\alpha
\end{align*}
$$

so $g_0,g_1,\dots$ yields a counterexample in $\Ult_{U_\beta}$. 
$\square$

<a name="ex19.10"></a>
## Exercise 19.10.
<i>Solution.</i> There are probably some typos in the hint, such as the mixing up of $n$ and $\eta$. We will thus ignore the hint. By <a href="#ex19.9">Exercise 19.9</a>, it suffices to show that $\Ult_{U_\alpha}(M)$ is well-founded for all $\alpha < \omega_1$. We induct on $\alpha$ to show that arbitrary countable intersections of elements of $U_\alpha$ is non-empty. Then, as in the proof of Lemma 17.2, taking $t \in \bigcap_{n=0}^\infty X_n$ would yield us the desired contradiction.

Since $\alpha$ is countable, we enumerate $\alpha = \lbrace \alpha_n : n < \omega\rbrace$. By induction on $k \geq 0$, suppose we have shown that there exists some $\gamma_0,\dots,\gamma_{k-1} < \omega$ such that:

$$
\begin{align*}
\forall n \, (\exists Y_n \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_{k-1}\rbrace})(\forall s \in Y_n) \, s \cup \lbrace (\alpha_0,\gamma_0),\dots,(\alpha_{k-1},\dots,\gamma_{k-1})\rbrace
\end{align*}
$$

Note that for $k = 0$, we may let $Y_n = X_n$. For each $n$, since $Y_n \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_{k-1}\rbrace}$ we have that:

$$
\begin{align*}
&\iffbreak Y_n \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_{k-1}\rbrace} \\
&\iff (\exists A_n \in U)(\forall \gamma \in A_n)(\exists Z_{n,\gamma} \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_k\rbrace})(\forall s \in Z_{n,\gamma}) \, s \cup \lbrace (\alpha_k,\gamma)\rbrace \in Y_n
\end{align*}
$$

Since arbitrary countable intersections of elements of $U$ are non-empty, $A := \bigcap_{n=0}^\infty \neq \emptyset$. Let $\gamma_k \in A_k$. Then we have:

$$
\begin{align*}
\forall n \, (\exists Z_n \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_k\rbrace})(\forall s \in Z_n) \, s \cup \lbrace (\alpha_k,\gamma_k)\rbrace \in Y_n
\end{align*}
$$

Combined with the induction hypothesis, this gives:

$$
\begin{align*}
\forall n \, (\exists Z_n \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_k\rbrace})(\forall s \in Z_n) \, s \cup \lbrace (\alpha_0,\gamma_0),\dots,(\alpha_k,\gamma_k)\rbrace \in X_n
\end{align*}
$$

which completes the induction. Now let:

$$
\begin{align*}
t := \lbrace (\alpha_k,\gamma_k) : k < \omega\rbrace
\end{align*}
$$

We shall show that $t \in \bigcap_{n=0}^\infty X_n$, which completes the proof. Fix $n < \omega$. Recall that we have $X_n = i_{E,\alpha}(X_n\restrictedto E)$ for some finite $E \subseteq \alpha$, where $X_n\restrictedto E := \lbrace s\restrictedto E : s \in X_n\rbrace$ and $X_n\restrictedto E \in U_E$. By the finiteness of $E$, $E \subseteq \lbrace \alpha_k : k < m\rbrace$ for some $m$. As we proved above, we have that:

$$
\begin{align*}
\forall n \, (\exists Y_n \in U_{\alpha - \lbrace \alpha_0,\dots,\alpha_{m-1}\rbrace})(\forall s \in Y_n) \, s \cup \lbrace (\alpha_0,\gamma_0),\dots,(\alpha_{m-1},\gamma_{m-1})\rbrace \in X_n
\end{align*}
$$

Take any $s \in Y_n$. Since the support of $X_n$ lies in $\lbrace \alpha_k : k < m\rbrace$, we have that:

$$
\begin{align*}
&\iffbreak s \cup \lbrace (\alpha_0,\gamma_0),\dots,(\alpha_{m-1},\gamma_{m-1})\rbrace \in X_n \\
&\iff \lbrace (\alpha_0,\gamma_0),\dots,(\alpha_{m-1},\gamma_{m-1})\rbrace \in X_n\restrictedto\lbrace \alpha_k : k < m\rbrace \\
&\iff t \in X_n
\end{align*}
$$

as $t\restrictedto\lbrace \alpha_k : k < m\rbrace = \lbrace (\alpha_0,\gamma_0),\dots,(\alpha_{m-1},\gamma_{m-1})\rbrace$. Thus $t \in X_n$ for all $n$, completing the proof. 
$\square$

<a name="ex19.11"></a>
## Exercise 19.11.
<i>Solution.</i> The definition of $L[\W]$ appears to be circular, so we first clarify the construction: Let $\W^\ast  := \c{U_\alpha,U^0,U^1}_{\alpha \in B}$, and consider the inner model $L[\W^\ast ]$. Let $W_\alpha = U_\alpha \cap L[\W^\ast ]$, $W^\varepsilon = U^\varepsilon \cap L[\W^\ast ]$, and let $\W = \c{W_\alpha,W^0,W^1}_{\alpha \in B}$. By a proof similar to Lemma 13.23, we can prove that $L[\W] = L[\W^\ast ]$ (so we indeed have $W_\alpha = U_\alpha \cap L[\W]$ and $W^\varepsilon = U^\varepsilon \cap L[\W]$), and $\W \in L[\W]$. This also implies that $W_\alpha,W^0,W^1 \in L[\W]$ for $\alpha \in B$.

We now check that $L[\W]$ satisfies (i)-(iii) of (19.24). For (i) and (ii), we first note that since $U^0,U^1$ are normal measures on $\kappa$ in $L[\U]$, it's easy to verify by definition that $W^\varepsilon = U^\varepsilon \cap L[\W]$ are normal measures on $\kappa$ in $L[\W]$. By Theorem 19.38, $W_\alpha,W^0,W^1$ are the only normal measures in $L[\W]$, which implies that each $W_\alpha$ is of order $0$. It remains to show that:
<ol>
<li> $W^0 < W^1$ in $L[\W]$..</li>
<li> $\c{W_\alpha : \alpha \in B}$ represents $W^0$ in $\Ult_{W^1}(L[\W])$.</li>
</ol>
We first note that:

$$
\begin{align*}
U^0 < U^1 \iff U^0 \in \Ult_{U^1}(L[\U]) \iff U^0 \in L[j_{U_1}(\U)]
\end{align*}
$$

Thus, 
$\square$

<a name="ex19.13"></a>
## Exercise 19.13.
<i>Solution.</i> Let $(U')^1,(W')^1$ be two different normal measures of order $1$ on $\kappa$, along with $(U')^0 < (U')^1$ and $(W')^0 < (W')^1$. Let $A' \in (U')^1$ and $B' \in (W')^1$ such that $\c{U_\alpha' : \alpha \in A'}$ represents $(U')^0$ in $\Ult_{(U')^1}(L[\U'])$ (where $\U' = \c{U_\alpha',(U')^0,(U')^1}_{\alpha\in A'}$, and $\c{W_\alpha' : \alpha \in B'}$ represents $(W')^0$ in $\Ult_{(W')^1}(L[\W'])$ ($\W'$ is similarly defined). Since $(U')^1 \neq (W')^1$ are normal measures, there exist some $X \subseteq \kappa$ such that $X \in (U')^1$ and $\kappa - X \in (W')^1$. Consequently, there exists $A \subseteq A'$ in $(U')^1$, and $B \subseteq B'$ in $(W')^1$, such that $A$ and $B$ are disjoint. Now let $\U = \c{U_\alpha,U^0,U^1}_{\alpha \in A}$, where $U_\alpha = U_\alpha' \cap L[\U]$, $U^0 = (U')^0 \cap L[\U]$ and $U^1 = (U')^1 \cap L[\U]$. Define $W_\alpha,W^0,W^1$ similarly. By <a href="#ex19.12">Exercise 19.12</a>, $L[\U]$ and $L[\W]$ are the desired inner models with $A$ and $B$ disjoint. 
$\square$