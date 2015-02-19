---
title: Zooming Squishes
author: Martin Wolf
layout: post
permalink: /2013/01/17/zooming-squishes/
linked_list_url:
  - http://css-tricks.com/zooming-squishes/
categories:
  - Linked List
tags:
  - accessibility
  - em
  - media query
  - pixel
  - responsive
  - rwd
---
<p class="linked-list-quote-author">
  Chris Coyier:
</p>

> My media queries were in pixels. If changed them into EMs, then as you zoom in, the EM size changes, and the media queries should take effect where the pixel ones would not. So that&#8217;s what I did and it works great!

Chris converted all of his CSS-Tricks media queries from pixel to `em` based values so that they take effect not only when the viewport is resized but also when the visitor zooms in or out. That makes for better accessibility.

Just yesterday afternoon I experimented with `em` and how changes of the body `font-size` affect the rest of the document. You can see my <a href="http://codepen.io/martinwolf/pen/BgGxy" title="Experiments with em based values" target="_blank">CodePen here</a>.  
In the past I always avoided `em` but now I think it&#8217;s great and we should all use it more often. I definitely will.