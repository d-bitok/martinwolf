---
title: Eliminating the 300ms delay on mobile devices when tapping a link with FastClick.js
author: Martin Wolf
layout: post
permalink: /2013/04/24/eliminating-the-300ms-delay-on-mobile-devices-when-tapping-a-link-with-fastclick-js/
categories:
  - Articles
tags:
  - click
  - delay
  - fastclick
  - iOS
  - mobile
---
**We all know this delay when tapping a link on a mobile device and it can be annoying.**

Okay, to be fair it&#8217;s really just 300ms. But nevertheless you can feel it and especially when crafting a mobile web app you need everything as fast and smooth as possible. The delay basically exists because the browser is waiting to check if the user is performing a double tap.

If you&#8217;re building a web app you rarely need that functionality on a link, so it would be nice to get rid of the delay. And that&#8217;s what [fastClick.js][1] is here for. It&#8217;s a simple JavaScript plugin that was developed by [FT Labs][2].

The question if this functionality is worth loading 20kb of JavaScript is yours to answer and may depend on the project you&#8217;re working on.

To show you how it works I made a [CodePen][3]. It goes without saying that you need to open this url on you mobile device, right?

<pre class="codepen" data-height="300" data-type="js" data-href="yFmpG" data-user="martinwolf" data-safe="true"><code>// Loading fastclick.js as external js file

window.addEventListener('load', function() {
  new FastClick(document.body);
}, false);</code><a href="http://codepen.io/martinwolf/pen/yFmpG">Check out this Pen!</a></pre>

 [1]: https://github.com/ftlabs/fastclick
 [2]: http://labs.ft.com/
 [3]: http://cdpn.io/yFmpG