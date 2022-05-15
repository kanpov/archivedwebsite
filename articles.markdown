---
layout: page
title: Articles
permalink: /articles/
---

{% for article in site.articles %}
{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
<span class="post-meta">{{ article.date | date: date_format }}</span>
<a class="post-link" href="{{ article.url | relative_url }}">
{{ article.title | escape }}
</a>
{% endfor %}
