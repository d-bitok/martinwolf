---
title: Position the border-bottom of text
author: Martin Wolf
layout: post
permalink: /2012/09/24/positioning-the-border-bottom-of-inline-elements/
categories:
  - Articles
tags:
  - border
  - border-bottom
  - css
  - line-height
  - trick
---
The problem with `text-decoration: underline` is that the border always has the same color as the text and that you can&#8217;t define the space between text and the underline itself. To get around these problems you can simply use `border-bottom`. The problem you are often faced with is how to get the border further away or nearer to it&#8217;s text without affecting the line-height of the whole paragraph. The simple solution is to apply `inline-block` and then adjusting the `line-height`.

<pre class="language-markup"><code  class="language-markup">&lt;p&gt;Lorem ipsum dolor &lt;a href="#"&gt;sit amet&lt;/a&gt;, consectetuer adipiscing elit.&lt;/p&gt;</code></pre>

<pre class="language-css"><code class="language-css">p {
    color: #000;
    font-size: 16px;
    line-height: 20px;
}

a {
    display: inline-block;
    color: #000;
    line-height: 18px;
    text-decoration: none;
    border-bottom: 1px solid #bbb;
}</code></pre>

Once again I made a small [Pen][1] on CodePen so you can play around with it.

 [1]: http://codepen.io/martinwolf/pen/vgpAd