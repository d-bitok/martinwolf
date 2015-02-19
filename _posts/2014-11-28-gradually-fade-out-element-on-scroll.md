---
title: Gradually fade out element on scroll
author: Martin Wolf
layout: post
permalink: /2014/11/28/gradually-fade-out-element-on-scroll/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"538344223091986432";s:5:"pDate";s:19:"2014-11-28 14:50:39";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_803424929720791";s:5:"pDate";s:19:"2014-11-28 14:50:51";}}";'
categories:
  - Articles
tags:
  - code
  - fade out
  - jquery
  - scrolling
---
A popular effect is to fade out an element when you start to scroll. You can do that by checking how far the user has scrolled and then perform a fade out animation and do the reverse if the users scrolls back up. But the effect gets even a little bit nicer if you gradually fade out the element according to how far the user has scrolled.  
You can achieve this effect with just a few lines of jQuery.

First we store the element we want to animate in a variable we don&#8217;t have to look for it on every scroll event.

<pre><code class="lang-javascript">var myElement = $('.js_my-element');</code></pre>

If the user scrolls we grab the scroll position and store it in variable.

<pre><code class="lang-javascript">$(window).on('scroll', function() {
    var st = $(this).scrollTop();</code></pre>

Then we update the opacity value on our element. For that we divide the scroll position by a value of our choice. A higher value means the user has to scroll a longer distance before the element has completely faded out. Then we subtract the result from 1 and apply the result as the new opacity value.

<pre><code class="lang-javascript">myElement.css({
    'opacity' : 1 - st/600
});</code></pre>

**This is the complete code:**

<pre><code class="lang-javascript">var myElement = $('.js_my-element');

$(window).on('scroll', function() {
    var st = $(this).scrollTop();
    myElement.css({
        'opacity' : 1 - st/600
    });
});</code></pre>