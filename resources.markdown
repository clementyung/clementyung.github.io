---
layout: default
title: "Resources"
permalink: /resources/
---

{% include base_path %}

{% for page in site.resources %}
  <li>
      <a href="{{ page.permalink }}">{{ page.title }}</a>
  </li>
{% endfor %}