---
layout: default
title: Year 7
description: Year 7 Computer Science — web dev starter unit.
---

# Year 7

<p>Pick a lesson below. Each page includes objectives, code snippets, and simple tasks.</p>

<ul class="card-grid">
{% assign pages = site.pages | where_exp:"p","p.path contains 'ks3/year7/'" | sort:"title" %}
{% for p in pages %}
  {% if p.url != '/ks3/year7/' %}
    <li class="card"><a href="{{ p.url }}">{{ p.title }}</a></li>
  {% endif %}
{% endfor %}
</ul>
