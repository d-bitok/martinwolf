---
title: Trigger Download with HTML5 download attribute
layout: post
permalink: /2015/04/13/trigger-download-with-html5-download-attribute/
categories:
  - Articles
tags:
  - html5
  - download
format: article
---
HTML5 brought a lot of big new things to the world, but there are also a couple of nice small things like the `download` attribute for example. It allows you to force a download of the linked file instead of opening it in a new tab or window. It's really useful if you want to offer images for download for example - like in a press section. Add it like that:

{% highlight html %}
<a href="http://mysite.com/downloads/team.jpg" download>Download</a>
{% endhighlight %}

If the linked file has a auto generated name - form a CMS for example - you can define a new name with which the file will be downloaded:

{% highlight html %}
<a href="http://mysite.com/downloads/3cHj983bn.jpg" download="team.jpg">Download</a>
{% endhighlight %}

Hope you can use it to improve the user experience of the sites you work on.
