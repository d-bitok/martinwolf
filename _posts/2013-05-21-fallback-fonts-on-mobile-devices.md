---
title: Fallback Fonts on Mobile Devices
author: Martin Wolf
layout: post
permalink: /2013/05/21/fallback-fonts-on-mobile-devices/
linked_list_url:
  - http://blog.typekit.com/2013/04/17/fallback-fonts-on-mobile-devices/
categories:
  - Linked List
tags:
  - performance
  - typekit
  - webfonts
---
<p class="linked-list-quote-author">
  Jordan Moore:
</p>

> I learned through my own experience that a font stack based on system fonts is no longer as safe as it was before the mobile device boom. Where system fonts in the major mobile operating systems are concerned, there is barely any consistency at all. For example, the Android operating system only comes packaged with 4 system fonts — none of which appear on iOS or Windows Phone, and those two platforms only share a handful of fonts between themselves. In the process of creating a compatibility table of shared default fonts across these systems for my own reference, what I ended up with was actually more like an [incompatibility table][1]. There is no safe native typographic foundation on today’s web.

Jordan Moore explores the possibilities of fallback fonts for mobile devices in a guest post on the Typekit blog.

Sadly I see a lot of websites loading massive amounts of webfont data when they don&#8217;t even need all of it. So make sure to only add fonts to your Typekit kits or Google webfonts that you really need.

Over and out, Performance-Martin.

 [1]: http://www.jordanm.co.uk/tinytype