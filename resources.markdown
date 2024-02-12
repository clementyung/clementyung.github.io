---
layout: default
title: "Resources"
permalink: /resources/
---

<body>
{% for post in site.posts %}
   {% if post.category == "resource" %}
       ## <a href="{{ post.url }}">{{ post.title }}</a>

       {{ post.excerpt }}
   {% endif %}
{% endfor %}
</body>