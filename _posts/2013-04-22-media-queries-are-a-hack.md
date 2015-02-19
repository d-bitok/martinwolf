---
title: Media Queries are a Hack
author: Martin Wolf
layout: post
permalink: /2013/04/22/media-queries-are-a-hack/
linked_list_url:
  - http://ianstormtaylor.com/media-queries-are-a-hack/
categories:
  - Linked List
tags:
  - element queries
  - media queries
  - rwd
---
<p class="linked-list-quote-author">
  Ian Storm Taylor:
</p>

> I want write-once, use-anywhere—that’s what modular code is.
> 
> Media queries are not that. They’re write-everywhere. They’re relative to your screen, so every time you write a media query for max-width or min-width, you’re connecting the appearance of your module to the width of the entire canvas—exactly what you were trying to avoid.

This post fits in line with the one from [Tab Atkins][1] I posted earlier today. Ian explains what the problem with media queries is and why we need element queries. But he doesn&#8217;t talk about the problem of circularity like Tab does. Nevertheless, go ahead and read it.

 [1]: http://theamazingweb.net/2013/04/22/element-queries/