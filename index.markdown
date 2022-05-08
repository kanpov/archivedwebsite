---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
---

## [Newsletter]({% link newsletter.markdown %})

A weekly newsletter for documenting my life.\
Comes out every Sunday at 6 PM GMT.

{% for post in site.posts limit:1 %}
<b>Latest post:</b> 
<a href="{{ post.url | relative_url }}">
{{ post.title | escape }}
</a>
{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
(<i>{{ post.date | date: date_format }}</i>)
{% endfor %}

## [Articles]({% link articles.markdown %})

A series of articles on various topics that come to mind.

{% for article in site.articles limit:1 %}
<b>Latest article:</b>
<a href="{{ article.url | relative_url }}">
{{ article.title | escape }}
</a>
{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
(<i>{{ article.date | date: date_format }}</i>)
{% endfor %}

## [About]({% link about.markdown %})
