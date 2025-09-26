---
layout: default
title: Computer Science
---

# Computer Science (KS4/KS5)

<ul class="card-grid">
{% assign pages = site.pages | where_exp: "p","p.path contains 'cs/'" | sort: "title" %}
{% for p in pages %}
  {% if p.url != '/cs/' %}
    <li class="card"><a href="{{ p.url }}">{{ p.title }}</a></li>
  {% endif %}
{% endfor %}
</ul>

{% assign pdfs = site.static_files | where_exp: "f","f.path contains '/cs/' and f.extname == '.pdf'" %}
{% if pdfs.size > 0 %}
<h2>Downloads</h2>
<ul>
  {% for f in pdfs %}
    <li><a href="{{ f.path }}">{{ f.name }}</a></li>
  {% endfor %}
</ul>
{% endif %}
