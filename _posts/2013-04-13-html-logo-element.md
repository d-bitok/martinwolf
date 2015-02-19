---
title: Why is there no HTML5 logo element?
author: Martin Wolf
layout: post
permalink: /2013/04/13/html-logo-element/
categories:
  - Articles
tags:
  - element
  - html
  - html5
  - logo
  - proposal
---
With HTML5 we got new HTML elements like `header`, `footer`, `article` to only name a few. These are elements for commonly used content types. So recently I asked myself why isn&#8217;t there a logo element? It&#8217;s pretty much save to say that every website has a logo in some form or shape so wouldn&#8217;t a logo element in combination with `header`, `article`, etc make total sense?

<pre class="language-markup"><code>&lt;header&gt;
    &lt;logo&gt;
        &lt;h1&gt;The Amazing Web&lt;/h1&gt;
    &lt;/logo&gt;
    &lt;nav&gt;
        ...
    &lt;/nav&gt;
&lt;/header&gt;

&lt;main&gt;
    ...
&lt;/main&gt;</code></pre>

Inside the logo element tags there could be everything you want. It could be a simple `h1` or an image or you could simply use the logo tag and apply a background image to it. Every screen reader and search engine could perfectly detect it and everybody wins.

So I wonder, is there something I overlooked or don&#8217;t know of? Hit me up on [Twitter][1], [Facebook][2] or simply via [mail][3]. Thanks!

 [1]: http://twitter.com/_martinwolf
 [2]: https://www.facebook.com/TheAmazingWeb
 [3]: mailto:martin@theamazingweb.net