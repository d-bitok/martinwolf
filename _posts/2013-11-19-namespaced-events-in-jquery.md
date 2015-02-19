---
title: Namespaced Events in jQuery
author: Martin Wolf
layout: post
permalink: /2013/11/19/namespaced-events-in-jquery/
snapFB:
  - 's:152:"a:1:{i:0;a:4:{s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:28:"1607117196_10200993072461487";s:5:"pDate";s:19:"2013-11-19 08:42:46";}}";'
snap_isAutoPosted:
  - 1
snapTW:
  - 's:142:"a:1:{i:0;a:4:{s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"402718581680775168";s:5:"pDate";s:19:"2013-11-19 08:42:46";}}";'
linked_list_url:
  - http://css-tricks.com/namespaced-events-jquery/
categories:
  - Linked List
tags:
  - jquery
---
<p class="linked-list-quote-author">
  Chris Coyier:
</p>

> Its really easy to add an event listener in jQuery. Its equally easy to remove an event listener. You might want to remove a listener because you dont care to perform any actions on that event anymore, to reduce memory usage, or both. But lets say youve attached several listeners to the same event. How do you remove just one of them? Namespacing can help.

Some nice little jQuery tip that sooner or later will come in handy.