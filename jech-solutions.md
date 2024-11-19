---
layout: default
title: "Suggested Solutions to Jech's <i>Set Theory</i>"
permalink: /jech-solutions/
---

I spent most of my summer break before the start of my PhD doing exercises in Jech's book. Here are my suggested solutions. See the readme and credits here<a href="/jech-solutions/readme">here</a>.

{% for post in site.posts reversed %}
   <ul>
   {% if post.category == "solution" %}
       <li><a href="{{ post.url }}">{{ post.title }}</a></li>
   {% endif %}
   </ul>
{% endfor %}