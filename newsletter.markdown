---
layout: page
title: Newsletter
permalink: /newsletter/
---

You can subscribe to the newsletter via RSS to receive updates into your mail:

- Download an RSS extension, for example, [this one](https://chrome.google.com/webstore/detail/rss-feed-reader/pnjaodmkngahhkoihejjehlcdlnohgmp?hl=en)
- Click on [this link]({% link feed.xml %}) to go to the feed
- Subscribe by entering your email address

<p></p>

{%- if site.posts.size > 0 -%}
{%- for post in site.posts -%}

<h3>
<a href="{{ post.url | relative_url }}">
{{ post.title | escape }}
</a>
</h3>

<p>
{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
<span>{{ post.date | date: date_format }}</span>
</p>

{%- endfor -%}
{%- endif -%}
