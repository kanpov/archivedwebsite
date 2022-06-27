---
title: Home
layout: page
---

## [Newsletter]({% link newsletter.markdown %})

A newsletter that comes out every Sunday/Monday at 6PM GMT where I give updates on my life
and projects.

<b>How to subscribe to the newsletter:</b>

<ul>
  <li>Follow <a href="https://feedrabbit.com/signup?return_url=%2Fsubscriptions%2Fnew%3Furl%3Dhttps%253A%252F%252Fkanpov.github.io%252Ffeed.xml">this link</a> to go to FeedRabbit, which is a service that will deliver the new posts to your inbox</li>
  <li>Enter your email address and sign up to the service</li>
  <li>Click on the green subscribe button</li>
  <li>Click on the save button, edit the settings if necessary</li>
  <li>Lastly, check your email address to verify it</li>
</ul>

{% if site.posts.size > 0 %}
**Recent highlights:**
<ul>
{% for post in site.posts limit:3 %}
<li>
<a href="{{ post.url | relative_url }}">
{{ post.title | escape }}
</a>
{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
(<i>{{ post.date | date: date_format }}</i>)
</li>
{% endfor %}
</ul>
{% endif %}

## [Articles]({% link articles.markdown %})

My questionable pieces of writing.\
Come out non-consistently, usually about once a month.

{% if site.articles.size > 0 %}
<ul>
{% for article in site.articles limit:3 %}
<li>
<a href="{{ article.url | relative_url }}">
{{ article.title | escape }}
</a>
{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
(<i>{{ article.date | date: date_format }}</i>)
</li>
{% endfor %}
</ul>
{% endif %}

## [Projects]({% link projects.markdown %})

A repository of all of my projects.\
These currently include:

- Minecraft mods
- Minecraft modding libraries
- Games

## Maven

If you're here from a tutorial on how to use some of my [GitHub](https://github.com/kanpov) JVM libraries,
you may be looking for a Maven repository with all the artifacts hosted on it.

Just paste this little piece of Groovy code into your `build.gradle` to include the Maven:

```groovy
repositories {
    maven {
        url = "https://kanpov.github.io/maven/"
    }
}
```

If you encounter any Gradle installation problems, create an issue in the project's repository, and I'll get in
touch as soon as possible.
