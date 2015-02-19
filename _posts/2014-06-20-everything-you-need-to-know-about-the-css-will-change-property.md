---
title: Everything You Need to Know About the CSS will-change Property
author: Martin Wolf
layout: post
permalink: /2014/06/20/everything-you-need-to-know-about-the-css-will-change-property/
linked_list_url:
  - 'http://dev.opera.com/articles/css-will-change-property/?utm_source=CSS-Weekly&utm_campaign=Issue-115&utm_medium=email'
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_721754221221196";s:5:"pDate";s:19:"2014-06-20 13:52:23";}}";'
snapTW:
  - 's:301:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:45:"[Linked] %TITLE%: %URL% //feat. @SaraSoueidan";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"479985092254003201";s:5:"pDate";s:19:"2014-06-20 13:52:18";}}";'
categories:
  - Linked List
tags:
  - browser
  - css
  - performance
  - rendering
  - will-change
---
<p class="linked-list-quote-author">
  Sara Soueidan:
</p>

> The will-change property allows you to inform the browser ahead of time of what kinds of changes you are likely to make to an element, so that it can set up the appropriate optimizations before they’re needed, therefore avoiding a non-trivial start-up cost which can have a negative effect on the responsiveness of a page. The elements can be changed and rendered faster, and the page will be able to update snappily, resulting in a smoother experience.

This is a highly recommended article because it is very important that you fully understand the upcoming `will-change` property before you use it. My biggest fear with this property is that it&#8217;ll get used with the intent of improving the performance of a site, but actually degrading it. So please take some time and read this article in full. It&#8217;ll be worth it.