---
layout: default
title: "Resources"
permalink: /resources/
---

<body>
{% for post in site.posts %}
   <ul>
   {% if post.category == "resource" %}
       <li><a href="{{ post.url }}">{{ post.title }} {{ post.excerpt }}</a></li>
   {% endif %}
   </ul>
{% endfor %}
</body>