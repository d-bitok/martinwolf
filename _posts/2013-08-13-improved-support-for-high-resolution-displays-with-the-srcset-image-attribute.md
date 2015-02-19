---
title: Improved support for high-resolution displays with the srcset image attribute
author: Martin Wolf
layout: post
permalink: /2013/08/13/improved-support-for-high-resolution-displays-with-the-srcset-image-attribute/
linked_list_url:
  - https://www.webkit.org/blog/2910/improved-support-for-high-resolution-displays-with-the-srcset-image-attribute/
categories:
  - Linked List
tags:
  - srcset
  - webkit
---
<p class="linked-list-quote-author">
  Dean Jackson:
</p>

> WebKit now supports the srcset attribute on image (img) elements (official specification from the W3C). This allows you, the developer, to specify higher-quality images for your users who have high-resolution displays, without penalizing the users who don’t. Importantly, it also provides a graceful fallback for browsers that don’t yet support the feature.

I&#8217;m not sure if I like what I read. I don&#8217;t think `srcset` is the right way to go about our responsive image problem. I&#8217;d rather see more use and implementations of the `picture` element.