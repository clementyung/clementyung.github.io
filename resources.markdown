---
layout: default
title: "Resources"
permalink: /resources/
---

{% include base_path %}

{% for post in site.resources %}
  <li>
      <a>{{ post.title }}</a>
  </li>
{% endfor %}