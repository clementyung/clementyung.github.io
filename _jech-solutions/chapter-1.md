---
title: "1) Axioms of Set Theory"
collection: jech-solutions
type: "Type"
permalink: /jech-solutions/chapter-1
---

Solutions to Chapter 1, Axioms of Set Theory.

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
.accordion {
  background-color: white;
  color: #444;
  cursor: pointer;
  padding: 18px;
  width: 100%;
  border: none;
  text-align: left;
  outline: none;
  font-size: 20px;
  transition: 0.4s;
  font-weight: bold;
}

.active, .accordion:hover {
  background-color: #ccc; 
}

.accordion:after {
  content: '\002B';
  color: #777;
  font-weight: bold;
  float: right;
  margin-left: 5px;
}

.active:after {
  content: "\2212";
}

.panel {
  padding: 0 18px;
  display: none;
  background-color: #eee;
  overflow: hidden;
}
</style>
</head>
<body>

<button class="accordion">Exercise 1.1.</button>
<div class="panel">
  <p>
    $\impliedby$ is clear. For $\implies$, suppose $(a,b) = \{\{a\},\{a,b\}\} = \{\{c\},\{c,d\}\} = (c,d)$. Then $\{a\} \in \{\{c\},\{c,d\}\}$, so $\{a\} = \{c\}$ or $\{a\} = \{c,d\}$. We consider two cases.
    <ol>
     <li>If $c = d$, then either way we have $\{a\} = \{c\}$, so we have $a = c$. We see that in this case, $\{\{a\},\{a,b\}\} = \{\{c\}\}$. Then $\{a,b\} = \{c\} = \{a\}$, so $\{a,b\} \subseteq \{a\} \implies b = a$. Hence $a = b = c d$.</li>
        
     <li>If $c \neq d$, then we must have $\{a\} = \{c\}$ and $\{c\} \neq \{c,d\}$. This also implies that $\{a,b\} = \{c,d\}$. Since $a = c$, ($b = c$ or $b = d$) and $c \neq d$, we must have $b = d$.</li>
    </ol>
  </p>
</div>

<button class="accordion">Exercise 1.2.</button>
<div class="panel">
  <p>
    If such an $X$ exists, then $X \in P(X) \subseteq X$, contradicting Axiom of Regularity (see Page 63 of the textbook).
  </p>
</div>

<script>
var acc = document.getElementsByClassName("accordion");
var i;

for (i = 0; i < acc.length; i++) {
  acc[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var panel = this.nextElementSibling;
    if (panel.style.display === "block") {
      panel.style.display = "none";
    } else {
      panel.style.display = "block";
    }
  });	
}
</script>

</body>
</html>