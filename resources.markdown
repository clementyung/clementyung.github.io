---
layout: default
title: "Resources"
permalink: /resources/
---

{% for post in site.posts %}
   <ul>
   {% if post.categories == "resource" %}
       <li><a href="{{ post.url }}">{{ post.title }}</a></li>
   {% endif %}
   </ul>
{% endfor %}