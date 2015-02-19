---
title: Force repaint of an element with Javascript
author: Martin Wolf
layout: post
permalink: /2014/06/10/force-repaint-of-an-element-with-javascript/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Snippet] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"476345548635930624";s:5:"pDate";s:19:"2014-06-10 12:50:03";}}";'
snapFB:
  - 's:380:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:38:"New snippet on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_716182415111710";s:5:"pDate";s:19:"2014-06-10 12:50:09";}}";'
categories:
  - Snippets
tags:
  - code
  - fixed
  - javascript
  - performance
  - rendering
  - repaint
  - safari
  - snippet
---
Today I had a pretty nasty situation in which Safari on OSX would render an element in a place where it doesn&#8217;t belong. It was clearly a rendering bug/issue because when highlighting the element in the web inspector the place where the element should have been rendered was highlighted.

I tried adding `transform: translate3d(0,0,0);` to push the element on it&#8217;s own layer to increase rendering performance, but that didn&#8217;t help. I thought that if I could bring the browser to repaint the element, I&#8217;d be fine, even though it&#8217;s probably not the nicest solution. I dug around the internet and [found a solution][1] to force the repaint of an element with Javascript:

<pre><code class="lang-javascript">/**
 * Force Repaint of Header because of
   OSX Safari Rendering Bug
 */
var siteHeader = document.getElementById('header');

siteHeader.style.display='none';
siteHeader.offsetHeight; // no need to store this anywhere, the reference is enough
siteHeader.style.display='block';</code></pre>

But be careful when you execute this code. You don&#8217;t want to repaint an element more often than you absolutely have to.

 [1]: http://stackoverflow.com/questions/3485365/how-can-i-force-webkit-to-redraw-repaint-to-propagate-style-changes/3485654#3485654