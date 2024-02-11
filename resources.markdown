---
layout: default
title: "Resources"
permalink: /resources/
---

{% for post in site.resources %}
    <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}

{% for post in site.posts %}
    <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}