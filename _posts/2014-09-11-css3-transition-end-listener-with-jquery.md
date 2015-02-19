---
title: CSS3 transition end listener with jQuery
author: Martin Wolf
layout: post
permalink: /2014/09/11/css3-transition-end-listener-with-jquery/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Snippet] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"509993700798509056";s:5:"pDate";s:19:"2014-09-11 09:15:48";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_762913347105283";s:5:"pDate";s:19:"2014-09-11 09:15:52";}}";'
categories:
  - Snippets
tags:
  - css3
  - javascript
  - jquery
  - snippet
  - transition
  - transitionend
---
As you hopefully know CSS3 transitions are a lot more performant than good old Javascript transitions. But what if you want to kick off some Javascript/jQuery when a CSS3 transition has ended?

Here is a code snippet that has done a great service for me in the past:

<pre><code class="lang-javascript">$('#my-div-with-css3-transition').one("webkitTransitionEnd otransitionend oTransitionEnd msTransitionEnd transitionend", function() {
    // Do your jQuery magic here
});</code></pre>

All those different `transionend`&#8216;s are need for best browser support.