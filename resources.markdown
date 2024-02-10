---
layout: default
title: "Resources"
permalink: /resources/
---

{% for page in site.resources %}
   test<a href="{{ page.url }}">{{ page.title }}</a>
{% endfor %}