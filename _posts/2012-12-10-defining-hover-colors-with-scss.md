---
title: Defining hover colors for consistency
author: Martin Wolf
layout: post
permalink: /2012/12/10/defining-hover-colors-with-scss/
categories:
  - Articles
tags:
  - colors
  - css
  - hover
  - scss
  - variables
---
While working with SCSS and therefore the ability to use variables in my CSS I&#8217;m constantly defining colors in my `_vars.scss`.

When defining hover states I over and over again saw me writing things like

<pre class="lang-css"><code class="lang-css">.class {
	background: $keycolor;
	&:hover, &:focus {
		background: darken($keycolor, 5%);
	}
}</code></pre>

or simply don&#8217;t remembering how I made the hover state of this color look or if I already defined a hover with this color at all. So I ended up with slightly different hover colors all over the place. That&#8217;s not good.

So I had the idea to define a second hover color as soon as I define a color variable, which looks like this:

<pre class="lang-css"><code class="lang-css">$keycolor: #0073a3;
$keycolorHover: darken($keycolor, 5%);</code></pre>

This brings some consitency into my hover states, saves me some work while writing my CSS and is especially convenient if I want to change a base color later. My CSS will then automatically create an appropriate hover color or if not I can easily adjust it. The CSS looks like this then:

<pre class="lang-css"><code class="lang-css">.class {
	background: $keycolor;
	&:hover, &:focus {
		background: $keycolorHover;
	}
}</code></pre>