---
layout: default
title: "Resources"
permalink: /resources/
---

<body>
{% for post in site.posts %}
   {% if post.category == "resource" %}
       <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>

       {{ post.excerpt }}
   {% endif %}
{% endfor %}
</body>