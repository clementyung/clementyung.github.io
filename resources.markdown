---
layout: default
title: "Resources"
permalink: /resources/
---

{% for post in site.posts %}
   <ul>
   {% if post.categories == "resource" %}
       <a href="{{ post.url }}">{{ post.title }} {{ post.excerpt }}</a>
   {% endif %}
   </ul>
{% endfor %}