---
title: "2) Ordinal Numbers"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-2
excerpt: ""
---

<head> 
  <script src="jquery.js"></script> 
  <script> 
  $(function(){
    $("#includedContent").load("https://clementyung.github.io/files/commands.html"); 
  });
  </script> 
</head> 

<div id="includedContent"></div>

## Exercise 2.1.
Suppose $f : P \to Q$ and $g : Q \to R$ are two isomorphisms.
    
<b>Reflexive:</b> The identity $\id : P \to P$ is clearly an isomorphism.
    
<b>Symmetry:</b> By definition of an isomorphism, it's easy to see if $f : P \to Q$ is an isomorphism then so is $f^{-1} : Q \to P$.
    
<b>Transitive:</b> Composition of isomorphisms are isomorphisms, as they remain bijective and:
$$
  x < y \implies f(x) < f(y) \implies g(f(x)) < g(f(y))
$$

## Exercise 2.2.
Note that $\beta < \alpha$ iff $\beta + 1 \leq \alpha$.

<u>$\implies$:</u> Suppose $\beta \in \alpha$. Since $\alpha = \bigcup \alpha$, $\beta \in \gamma$ for some $\gamma \in \alpha$. Then $\beta + 1 \subseteq \gamma$. Since $\gamma \in \alpha$, $\beta + 1 \in \alpha$.
    
<u>$\impliedby$:</u> If $\beta \in \bigcup \alpha$, then $\beta \in \gamma$ for some $\gamma \in \alpha$. By transitivity of ordinals, $\gamma \subseteq \alpha$, so $\beta \in \alpha$. Thus, $\bigcup \alpha \subseteq \alpha$ (we have not used the hypothesis).
    
On the other hand, let $\beta \in \alpha$. By hypothesis, $\beta + 1 \in \alpha$, so $\beta + 1 \subseteq \bigcup\alpha$. Hence $\beta \in \bigcup\alpha$.

$$
x = y
$$