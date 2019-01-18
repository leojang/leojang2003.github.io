---
layout: post
title:  "HTML5 Notes"
date:   2019-01-18 14:04:13 +0800
categories: Front-End
tags: html
---

## main

HTML5 introduces more descriptive HTML tags. These include header, footer, nav, video, article, section and others.
These tags make your HTML easier to read, and also help with Search Engine Optimization (SEO) and accessibility.

{% highlight html %}
<h2>CatPhotoApp</h2>
<main>
<p>Something</p>

<p>Something
</main>
{% endhighlight html %}

## img
{% highlight html %}
<img src="https://bit.ly/fcc-relaxing-cat" alt="A cute orange cat lying on its back.">
{% endhighlight html %}

## anchor
{% highlight html %}
<a href="http://freecatphotoapp.com">cat photos</a>
{% endhighlight html %}
  
 ## internal anchor
 {% highlight html %}
 <a href="#contacts-header">Contacts</a>
 ...
 <h2 id="contacts-header">Contacts</h2>
 {% endhighlight html %}
