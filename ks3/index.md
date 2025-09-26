---
layout: default
title: KS3 Resources
---

# KS3 Resources

<ul class="card-grid">
{% assign pages = site.pages | where_exp: "p","p.path contains 'ks3/'" | sort: "title" %}
{% for p in pages %}
  {% if p.url != '/ks3/' %}
    <li class="card"><a href="{{ p.url }}">{{ p.title }}</a></li>
  {% endif %}
{% endfor %}
</ul>

{% comment %} Optional: auto-list PDFs in /ks3/ {% endcomment %}
{% assign pdfs = site.static_files | where_exp: "f","f.path contains '/ks3/' and f.extname == '.pdf'" %}
{% if pdfs.size > 0 %}
<h2>Downloads</h2>
<ul>
  {% for f in pdfs %}
    <li><a href="{{ f.path }}">{{ f.name }}</a></li>
  {% endfor %}
</ul>
{% endif %}
