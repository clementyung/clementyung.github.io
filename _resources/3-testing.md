---
title: "1) Axioms of Set Theory</i>"
collection: resources
type: "Type"
permalink: /resources/jech-solutions/1
---

<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
.accordion {
  background-color: #eee;
  color: #444;
  cursor: pointer;
  padding: 18px;
  width: 100%;
  border: none;
  text-align: left;
  outline: none;
  font-size: 15px;
  transition: 0.4s;
}

.active, .accordion:hover {
  background-color: #ccc; 
}

.panel {
  padding: 0 18px;
  display: none;
  background-color: white;
  overflow: hidden;
}
</style>
</head>
<body>

<h2>Accordion</h2>

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