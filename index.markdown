---
title: Home
layout: page
---

## [Newsletter]({% link newsletter.markdown %})

A newsletter that comes out every Sunday/Monday at 6PM GMT with:

- Detailed dev-logs and updates on my current projects
- In-depth coverage of the internal architecture and design principles I use in my projects
- Updates on this website and my journaling method
- A bit of self-reflection on my language learning journey (I'm learning advanced English and recently started learning
  German)

<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-10_7_dtp.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{clear:left; font:14px Helvetica,Arial,sans-serif;  width:600px;}
	/* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="https://github.us17.list-manage.com/subscribe/post?u=c615ef4665a3ec494fca28dc0&amp;id=03ae13b6f2" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
<div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
<div class="mc-field-group">
	<label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
</label>
	<input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL">
</div>
	<div id="mce-responses" class="clear foot">
		<div class="response" id="mce-error-response" style="display:none"></div>
		<div class="response" id="mce-success-response" style="display:none"></div>
	</div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_c615ef4665a3ec494fca28dc0_03ae13b6f2" tabindex="-1" value=""></div>
        <div class="optionalParent">
            <div class="clear foot">
                <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
                <p class="brandingLogo"><a href="http://eepurl.com/h4LzR1" title="Mailchimp - email marketing made easy and fun"><img src="https://eep.io/mc-cdn-images/template_images/branding_logo_text_dark_dtp.svg"></a></p>
            </div>
        </div>
    </div>
</form>
</div>
<script type='text/javascript' src='//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js'></script><script type='text/javascript'>(function($) {window.fnames = new Array(); window.ftypes = new Array();fnames[0]='EMAIL';ftypes[0]='email';fnames[1]='FNAME';ftypes[1]='text';fnames[2]='LNAME';ftypes[2]='text';fnames[3]='ADDRESS';ftypes[3]='address';fnames[4]='PHONE';ftypes[4]='phone';fnames[5]='BIRTHDAY';ftypes[5]='birthday';}(jQuery));var $mcj = jQuery.noConflict(true);</script>
<!--End mc_embed_signup-->

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
