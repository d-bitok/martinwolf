---
title: Pure CSS multiline text with ellipsis
author: Martin Wolf
layout: post
permalink: /2013/01/29/pure-css-multiline-text-with-ellipsis/
categories:
  - Articles
tags:
  - codepen
  - css
  - ellipsis
  - pen
  - text-overflow
---
I just crafted a new Pen which demonstares the use of `text-overflow: ellipsis` for multiline text. It only works in webkit browsers but has a fallback for the other ones.  
I used SCSS variables to easily adjust text size, line height and line count.

For example this can be useful if you need to make sure that a certain headline can&#8217;t be longer/taller than a certain size and also don&#8217;t want to just cut it without any indicator.

<pre class="codepen" data-height="300" data-type="result" data-href="qlFdp" data-user="martinwolf" data-safe="true"><code></code><a href="http://codepen.io/martinwolf/pen/qlFdp">Check out this Pen!</a></pre>