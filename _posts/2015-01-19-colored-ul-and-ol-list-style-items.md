---
title: Colored ul and ol list style items
author: Martin Wolf
layout: post
permalink: /2015/01/19/colored-ul-and-ol-list-style-items/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"557093676359643136";s:5:"pDate";s:19:"2015-01-19 08:34:17";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_836428299753787";s:5:"pDate";s:19:"2015-01-19 08:34:24";}}";'
categories:
  - Articles
tags:
  - color list style item
  - css
  - list-style
  - ol
  - ul
---
**Have you ever tried to set a different color for `ul` and `ol` list style items in contrast to the list item text? Sadly there&#8217;s no such thing as `list-style-color`.**

Luckily there&#8217;s a really easy way around that. If you set the color of the `li` the text as well as the list item will be affected. You use that definition to color the list style items and then wrap the text inside the `li` in another element and set the color of that one, too.

<!--more-->

<pre><code class="lang-scss">ul {
  li {
    color: blue;
  }

  li &gt; span {
    color: black;
  }
}</code></pre>

If you just have a simple list you can wrap the text inside a `span` element. This has no semantic meaning and will most likely not effect the layout. Often a list consists of links, so you can style the `a` element and even make cool things happen on hover.

I put together a CodePen to demonstrate how it works:

<p data-height="266" data-theme-id="3560" data-slug-hash="KwWdEK" data-default-tab="result" data-user="martinwolf" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/KwWdEK/'>Colored ul and ol list style items</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
</p>