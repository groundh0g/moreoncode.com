---
---

{% comment %}
{% assign books = "" %}
{% for file in site.pages %}
    {% if file.path contains "books/" and file.path contains "/summary.md" %}
        {% assign book = file.path | replace: "/summary.md", "/" %}
        {% assign books = books | append: book | append: "," %}
    {% endif %}
{% endfor %}

{{ books | split: "," | size }}
{% endcomment %}

Needs content.