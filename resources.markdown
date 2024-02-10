---
layout: default
title: "Resources"
permalink: /resources/
---

{% for page in site.resources %}
  <li>
      <a href="{{ page.url }}">{{ page.title }}</a>
  </li>
{% endfor %}