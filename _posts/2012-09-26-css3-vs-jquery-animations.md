---
title: CSS3 vs jQuery Animations
author: Martin Wolf
layout: post
permalink: /2012/09/26/css3-vs-jquery-animations/
linked_list_url:
  - http://dev.opera.com/articles/view/css3-vs-jquery-animations/
categories:
  - Linked List
tags:
  - animations
  - css3
  - jquery
  - performance
---
<p class="linked-list-quote-author">
  Siddharth Rao:
</p>

> Clearly, CSS3 wins the race by lengths. The huge difference in performance is because the browser&#8217;s CSS processor is written in C++ and native codes executes very fast whereas jQuery (JavaScript) is an interpreted language and the browser can&#8217;t predict JavaScript ahead in time, in terms of what event will occur next.

Nice performance comparison of jQuery and CSS3 animations. Even though CSS3&#8217;s performance is much better, keep in mind that all IE&#8217;s below Version 10 don&#8217;t support CSS animations.