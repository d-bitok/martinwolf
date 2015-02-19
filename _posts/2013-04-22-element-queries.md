---
title: Element Queries
author: Martin Wolf
layout: post
permalink: /2013/04/22/element-queries/
linked_list_url:
  - 'http://www.xanthir.com/b4PR0?utm_source=Responsive+Design+Weekly&utm_campaign=4d85e189fc-Responsive_Design_Weekly_53&utm_medium=email'
categories:
  - Linked List
tags:
  - element queries
  - media queries
  - responsive
  - rwd
---
<p class="linked-list-quote-author">
  Tab Atkins:
</p>

> The idea of Element Queries is pretty simple &#8211; it&#8217;s like a Media Query (specifically, the min-width/etc queries), but for a parent or ancestor element, rather than the viewport.
> 
> This way, you could create a "component" that is styled one way when it&#8217;s in a narrow container (like a sidebar), but another way when it&#8217;s got some breathing room (like in the main content of the page), without having to manually specify what kinds of containers are each type &#8211; it just naturally happens due to the width of the respective containers.

This is what we all long for, isn&#8217;t it? But as it turns out this isn&#8217;t so easy as we think it should be due to the concept of circularity. Read on to see what it actually means.