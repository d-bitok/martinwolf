---
title: IE-friendly mobile-first CSS with Sass 3.2
author: Martin Wolf
layout: post
permalink: /2013/07/02/ie-friendly-mobile-first-css-with-sass-3-2/
linked_list_url:
  - http://jakearchibald.github.io/sass-ie/
categories:
  - Linked List
tags:
  - ie
  - sass
---
<p class="linked-list-quote-author">
  Jake Archibald:
</p>

> Building CSS mobile-first is the way forward, because blah blah blah progressive enhancement blah. Problem is, Internet Explorer prior to 9 ignores anything within media query blocks, leaving those browsers with mobile styles.
> 
> Not all of us can get away with that, but thankfully, as Chris Eppstein points out, Sass 3.2 can generate a separate stylesheet with everything it needs to create a "desktop" look.

If you&#8217;re in the bad spot and have to support IE7 or IE8 and are using Sass, the upcoming new version of it will help you maintain separate CSS files for these legacy browsers.