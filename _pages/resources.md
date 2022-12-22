---
layout: archive
title: "Resources"
permalink: /resources/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}


{% for post in site.resources %}
  {% include archive-single.html %}
{% endfor %}