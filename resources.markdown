---
layout: default
title: "Resources"
permalink: /resources/
---

{% for post in site.posts %}
   {% if post.category == "resource" %}
       <a href="{{ post.url }}">{{ post.title }} {{ post.excerpt }}</a>
   {% endif %}
{% endfor %}