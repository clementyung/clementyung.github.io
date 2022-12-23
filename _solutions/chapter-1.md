---
title: "1) Axioms of Set Theory"
collection: solutions
type: "Type"
permalink: /jech-solutions/chapter-1
---


<div id="accordion">
  <div class="panel">
    <a data-toggle="collapse" data-parent="#accordion" href="#ex1.1">
      Exercise 1.1.
    </a>
  <div id="ex1.1" class="collapse">
    <div class="panel-body">
      $\impliedby$ is clear. For $\implies$, suppose $(a,b) = \{\{a\},\{a,b\}\} = \{\{c\},\{c,d\}\} = (c,d)$. Then $\{a\} \in \{\{c\},\{c,d\}\}$, so $\{a\} = \{c\}$ or $\{a\} = \{c,d\}$. We consider two cases.
      <ol>
        <li>If $c = d$, then either way we have $\{a\} = \{c\}$, so we have $a = c$. We see that in this case, $\{\{a\},\{a,b\}\} = \{\{c\}\}$. Then $\{a,b\} = \{c\} = \{a\}$, so $\{a,b\} \subseteq \{a\} \implies b = a$. Hence $a = b = c = d$.</li>
        
        <li>If $c \neq d$, then we must have $\{a\} = \{c\}$ and $\{c\} \neq \{c,d\}$. This also implies that $\{a,b\} = \{c,d\}$. Since $a = c$, ($b = c$ or $b = d$) and $c \neq d$, we must have $b = d$.</li>
      </ol>
    </div>
  </div>

  <div class="panel">
    <a data-toggle="collapse" data-parent="#accordion" href="#ex1.2">
      Exercise 1.2.
    </a>
  <div id="ex1.2" class="collapse">
    <div class="panel-body">
      <a data-toggle="collapse" data-parent="#accordion" href="#ex1.1">
        Testing.
      </a>
      If such an $X$ exists, then $X \in P(X) \subseteq X$, contradicting the Axiom of Regularity (see Page 63 of the textbook).
    </div>
  </div>
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