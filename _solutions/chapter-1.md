---
title: "1) Axioms of Set Theory"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-1
excerpt: ""
---

<a name="ex1.1">## Exercise 1.1.</a>
$\impliedby$ is clear. For $\implies$, suppose $(a,b) = \{\{a\},\{a,b\}\} = \{\{c\},\{c,d\}\} = (c,d)$. Then $\{a\} \in \{\{c\},\{c,d\}\}$, so $\{a\} = \{c\}$ or $\{a\} = \{c,d\}$. We consider two cases.
<ol>
  <li>If $c = d$, then either way we have $\{a\} = \{c\}$, so we have $a = c$. We see that in this case, $\{\{a\},\{a,b\}\} = \{\{c\}\}$. Then $\{a,b\} = \{c\} = \{a\}$, so $\{a,b\} \subseteq \{a\} \implies b = a$. Hence $a = b = c = d$.</li>
        
  <li>\item If $c \neq d$, then we must have $\{a\} = \{c\}$ and $\{c\} \neq \{c,d\}$. This also implies that $\{a,b\} = \{c,d\}$. Since $a = c$, ($b = c$ or $b = d$) and $c \neq d$, we must have $b = d$.</li>
</ol>

## Exercise 1.2.
If such an $X$ exists, then $X \in P(X) \subseteq X$, contradicting Axiom of Regularity (see Page 63 of the textbook).
<a href="ex1.1">jump</a>