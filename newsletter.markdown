---
layout: page
title: Newsletter
permalink: /newsletter/
---

<h2>Subscribe</h2>


<ul>
  <li>Follow <a href="https://feedrabbit.com/signup?return_url=%2Fsubscriptions%2Fnew%3Furl%3Dhttps%253A%252F%252Fkanpov.github.io%252Ffeed.xml">this link</a> to go to FeedRabbit, which is a service that will deliver the new posts to your inbox</li>
  <li>Enter your email address and sign up to the service</li>
  <li>Click on the green subscribe button</li>
  <li>Click on the save button, edit the settings if necessary</li>
  <li>Lastly, check your email address to verify it</li>
</ul>

<h2>Past Posts</h2>

{%- if site.posts.size > 0 -%}
<ul class="post-list">
{%- for post in site.posts -%}

<h3 class="post-list-heading">
<a href="{{ post.url | relative_url }}" class="post-link">
{{ post.title | escape }}
</a>
</h3>

{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
<span class="post-meta">{{ post.date | date: date_format }}</span>

{%- endfor -%}
</ul>
{%- endif -%}
