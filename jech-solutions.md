---
layout: default
title: "Suggested Solutions to Jech's <em>Set Theory</em>"
permalink: /jech-solutions/
---

I spent most of my summer break before the start of my PhD doing exercises in Jech's book. Here are my suggested solutions. See the readme and credits <a href="/jech-solutions/readme">here</a>.

<table>
  <thead>
    <tr>
      <th style="text-align: left; padding: 8px;">Chapter</th>
      <th style="text-align: left; padding: 8px;">Title</th>
      <th style="text-align: left; padding: 8px;">Missing Questions</th>
    </tr>
  </thead>
  <tbody>
    {% for post in site.posts reversed %}
      {% if post.category == "solution" %}
        {% comment %}
          Split the "#) Title" string by ") " to separate the chapter number and title
        {% endcomment %}
        {% assign chapter_parts = post.chapter | split: ") " %}
        {% assign ch_number = chapter_parts[0] | strip %}
        {% assign ch_title = chapter_parts[1] %}

        {% comment %}
          Map out the missing questions based on the readme file
        {% endcomment %}
        {% assign missing = "" %}
        {% if ch_number == "7" %}
          {% assign missing = "7.31" %}
        {% elsif ch_number == "15" %}
          {% assign missing = "15.11, 15.27" %}
        {% elsif ch_number == "16" %}
          {% assign missing = "16.4, 16.18" %}
        {% elsif ch_number == "19" %}
          {% assign missing = "19.12" %}
        {% elsif ch_number == "20" %}
          {% assign missing = "20.9, 20.20" %}
        {% elsif ch_number == "24" %}
          {% assign missing = "24.10" %}
        {% else %}
          {% assign missing = "" %}
        {% endif %}

        <tr>
          <td style="padding: 8px; font-weight: bold;">{{ ch_number }}</td>
          <td style="padding: 8px;"><a href="{{ post.url }}">{{ ch_title }}</a></td>
          <td style="padding: 8px; color: #666;">{{ missing }}</td>
        </tr>
      {% endif %}
    {% endfor %}
  </tbody>
</table>