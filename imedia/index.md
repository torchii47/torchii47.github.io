---
layout: default
title: Creative iMedia
---

# Creative iMedia

<ul class="card-grid">
{% assign pages = site.pages | where_exp: "p", "p.path contains 'imedia/'" | sort: "title" %}
{% for p in pages %}
  {% if p.url != '/imedia/' %}
    <li class="card"><a href="{{ p.url }}">{{ p.title }}</a></li>
  {% endif %}
{% endfor %}
</ul>

{% comment %} Optional: auto-list PDFs in /imedia/ {% endcomment %}
{% assign pdfs = site.static_files | where_exp: "f", "f.path contains '/imedia/' and f.extname == '.pdf'" %}
{% if pdfs.size > 0 %}
<h2>Downloads</h2>
<ul>
  {% for f in pdfs %}
    <li><a href="{{ f.path }}">{{ f.name }}</a></li>
  {% endfor %}
</ul>
{% endif %}
