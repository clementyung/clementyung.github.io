---
layout: default
title: "Resources"
permalink: /resources/
---

{% for post in site.resources %}
  <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endfor %}