---
layout: page
title: Articles
permalink: /articles/
---

<ul class="post-list">
{% for article in site.articles %}

<h3 class="post-list-heading">
<a class="post-link" href="{{ article.url | relative_url }}">
{{ article.title | escape }}
</a>
</h3>

{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
<span class="post-meta">{{ article.date | date: date_format }}</span>

{% endfor %}