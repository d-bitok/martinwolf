---
title: The main issue
author: Martin Wolf
layout: post
permalink: /2013/01/31/the-main-issue/
linked_list_url:
  - http://adactio.com/journal/6014/
categories:
  - Linked List
tags:
  - element
  - footer
  - header
  - html5
  - main
  - spec
---
<p class="linked-list-quote-author">
  Jeremy Keith:
</p>

> So what I don’t understand is why we can’t have the main element work the same way i.e. scope it to its sectioning content ancestor so that only the main element that is scoped to the body element will correspond to role="main":

Jeremy makes a good point regarding the currently planned implementation of the `main` element. At the moment the plan is to allow the element only once in an document but Jeremy proposes that it should behave the same way as the `header` and `footer` elements. I&#8217;m with him on this one.