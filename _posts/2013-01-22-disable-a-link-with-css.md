---
title: Disabling a link with CSS
author: Martin Wolf
layout: post
permalink: /2013/01/22/disable-a-link-with-css/
categories:
  - Articles
tags:
  - active
  - button
  - css
  - cursor
  - disable
  - pointer-events
---
Let&#8217;s imagine you have a navigation with a bunch of links. If you click a link you switch to that page and the link gets some sort of active class to style it so that the user sees on which page he is. In my world this link should also be disabled because there is no need to click it. You are already on this page. What I did until today is, I would apply `cursor: default;` to the active link so that you don&#8217;t get the pointer mouse cursor.

But an even better solution is to just disable the active link with `pointer-events: none;`. Not only is the link not clickable, but it also ignores all other pointer events like `:hover` or `:active`. That&#8217;s so much better than having to override all the pseudo-classes of the normal link.

Here is a simple example:

<pre class="language-markup"><code  class="language-markup">&lt;nav class="page-nav"&gt;
  &lt;a class="btn btn-is-active" href="index.php"&gt;Home&lt;/a&gt;
  &lt;a class="btn" href="about.php"&gt;About&lt;/a&gt;
  &lt;a class="btn" href="projects.php"&gt;Projects&lt;/a&gt;
&lt;/nav&gt;</code></pre>

<pre class="language-css"><code class="language-css">$btncolour: #307a16;

.btn {
  display: inline-block;
  padding: 10px 12px;
  color: #fff;
  text-decoration: none;
  background: $btncolour;
  border-radius: 3px;
}

.btn:hover,
.btn:focus {
  background: lighten($btncolour, 5%);
}

.btn:active {
  position: relative;
  top: 1px;
}

.btn-is-active {
  pointer-events: none; /* Disables the button completely. Better than just cursor: default; */
  @include opacity(0.7);
}</code></pre>

You can also try it out yourself on [CodePen][1].

 [1]: http://codepen.io/martinwolf/pen/yxboB