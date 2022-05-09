---
layout: home
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

## Maven

If you're here from a tutorial on how to use some of my [GitHub](https://github.com/RedGrapefruit09) JVM libraries,
you may be looking for a Maven repository with all the artifacts hosted on it.

Just paste this little piece of Groovy code into your `build.gradle` to include the Maven:
```groovy
repositories {
    maven {
        url = "https://redgrapefruit09.github.io/maven/"
    }
}
```

If you encounter any Gradle installation problems, create an issue in the project's repository, and I'll get in
touch as soon as possible.
