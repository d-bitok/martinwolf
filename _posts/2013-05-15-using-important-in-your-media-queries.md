---
title: Using !important in your media queries?
author: Martin Wolf
layout: post
permalink: /2013/05/15/using-important-in-your-media-queries/
linked_list_url:
  - http://www.iandevlin.com/blog/2013/05/css/using-important-in-your-media-queries
categories:
  - Linked List
tags:
  - '!important'
  - coding
  - css
  - media queries
---
<p class="linked-list-quote-author">
  Ian Devlin:
</p>

> Since the styling that you will place within your media queries is intended to override previous styling when certain conditions are met, depending on the complexity of the previous styles, overriding with !important can be an ideal and neater solution.

What Ian is proposing makes sense in a way, but I think a CSS stylesheet without or with very little `!important` rules will always be better maintainable easier to extend.