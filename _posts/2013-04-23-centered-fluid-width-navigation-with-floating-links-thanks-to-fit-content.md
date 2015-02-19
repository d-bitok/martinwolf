---
title: Centered fluid width navigation with floating links thanks to fit-content
author: Martin Wolf
layout: post
permalink: /2013/04/23/centered-fluid-width-navigation-with-floating-links-thanks-to-fit-content/
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:237:"a:1:{i:0;a:8:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";}}";'
snapTW:
  - 's:154:"a:1:{i:0;a:5:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";}}";'
categories:
  - Articles
tags:
  - codepen
  - css
  - fit-content
  - float
  - fluid
  - navigation
---
We all know the problem that an element, that contains floating elements can&#8217;t be centered with `margin: 0 auto;` because it has no real width. But there is something coming our way that will change this situation for the better: `fit-content`

Just apply `fit-content` to the container of floating elements and oh see, you can use `margin: 0 auto;`

<pre class="lang-markup"><code>&lt;div class="container"&gt;
    &lt;ul class="list-centered"&gt;
        &lt;li&gt;Lorem ipsum&lt;/li&gt;
        &lt;li&gt;li&gt;Dolor sit amet&lt;/li&gt;
        &lt;li&gt;li&gt;Constetetur&lt;/li&gt;
    &lt;/ul&gt;
&lt;/div&gt;</code></pre>

<pre class="lang-css"><code>.container {
    width: 600px;
}

.list-centered {
    margin: 0 auto;
    width: -webkit-fit-content;
       width: -moz-fit-content;
            width: fit-content;
}

.list-centered li {
    float: left;
}</code></pre>

Browser support is, as one could expect, poor at the moment but the cool things always start out like that. So if you know you&#8217;re only building for Chrome and Firefox you can go ahead and use it right now.

I made a [CodePen][1] to show it in action:

<pre class="codepen" data-height="300" data-type="result" data-href="ysiwa" data-user="martinwolf" data-safe="true"><code></code><a href="http://codepen.io/martinwolf/pen/ysiwa">Check out this Pen!</a></pre>

 [1]: http://codepen.io/martinwolf/pen/ysiwa