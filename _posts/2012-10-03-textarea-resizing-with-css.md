---
title: Textarea resizing with CSS
author: Martin Wolf
layout: post
permalink: /2012/10/03/textarea-resizing-with-css/
categories:
  - Articles
tags:
  - css
  - property
  - resize
  - textarea
---
**In modern browsers you can resize a standard textarea while dragging the lower right corner. That&#8217;s a nice feature of the browser but you can be a little bit more specific about that if you need to.**

All you need is the CSS property `resize`. There are four possibilities: `none`, `vertical`, `horizontal` and `both`. You don&#8217;t need to be extremely clever to understand what they are doing. What&#8217;s cool is, that you can combine these with `max-width` and `max-height`:

<pre class="language-css"><code class="language-css">textarea {
    display: block;
    resize: none;
    width: 100px;
    height: 100px;
    max-width: 200px;
    max-height: 200px;
}

.resize-both {
    resize: both;
}

.resize-vertical {
    resize: vertical;
}

.resize-horizontal {
    resize: horizontal;
}</code></pre>

Want to try it yourself? Have a look at my simple [CodePen][1].

 [1]: http://codepen.io/martinwolf/pen/knCez