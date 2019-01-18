---
layout: post
title:  "FreeCodeCamp HTML5 Notes"
date:   2019-01-18 14:04:13 +0800
categories: front-end
tags: html
---

HTML5 introduces more descriptive HTML tags. These include header, footer, nav, video, article, section and others.
These tags make your HTML easier to read, and also help with Search Engine Optimization (SEO) and accessibility.

{% highlight html linenos %}
<h2>CatPhotoApp</h2>
<main>
<p>Something</p>

<p>Something
</main>
{% endhighlight html %}

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
