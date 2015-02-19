---
title: Adding and removing classes from svg elements with jQuery
author: Martin Wolf
layout: post
permalink: /2014/12/11/adding-and-removing-classes-from-svg-elements-with-jquery/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_810113729051911";s:5:"pDate";s:19:"2014-12-11 10:03:13";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"542982932504514560";s:5:"pDate";s:19:"2014-12-11 10:03:14";}}";'
categories:
  - Articles
tags:
  - .attr
  - addClass
  - classList
  - howto
  - javascript
  - jquery
  - removeClass
  - Snippets
  - svg
  - Web API
---
A few days ago I wanted to toggle a class on an svg element. Not sure anymore, but I think I wanted to show/hide it. jQuery was already loaded and used in the project so I added the class with `$('#js_svg-element').addClass('my-class');`

Nothing happened.

I inspected my code over and over again and couldn&#8217;t find anything that&#8217;s wrong, so I asked my dear friend Google and found out that you can&#8217;t add/remove classes to/from svg elements with jQuery. Bummer.

Luckily, there are two solutions:

<!--more-->

### jQuery .attr()

One solution is to fall back to the .attr() method of jQuery, like that:

<pre><code class="lang-javascript">/**
 * Instead of .addClass('my-class')
 */
$('#js_svg-element').attr('class', 'my-class');

/**
 * Instead of .removeClass('newclass')
 */
$('#js_svg-element').attr('class', '');</code></pre>

The `.attr()` method replaces the complete attribute, so if you want to add a class to existing ones you have to list them too, which can make this workaround a little tedious:

<pre><code class="lang-javascript">/**
 * If #js_svg-element already has the classes a-class and another-class
 */
$('#js_svg-element').attr('class', 'a-class another-class my-class');</code></pre>

### classList

The other solution is to use the Web API Interface `Element.classList`.  
`classList` has three different write possibilities: `.add`, `.remove` or `.toggle`. Sadly IE9 and Opera Mini [don&#8217;t support][1] `classList`.

<pre><code class="lang-javascript">$('#js_svg-element').classList.add('my-class');
$('#js_svg-element').classList.remove('my-class');

/**
 * If my-class is set, remove it, otherwise add it
 */
$('#js_svg-element').classList.toggle('my-class');

/**
 * You can also add multiple classes
 */
$('#js_svg-element').classList.add('my-class','my-other-class');</code></pre>

If you want to know more about the classList Web API Interface, the [MDN][2] has tons of information and a Javascript Shim which should make it work in IE9 and Opera Mini.  
But in my case I&#8217;m not a fan of throwing so much JS on the table just to make this work for adding/removing a class from a single svg element.

 [1]: http://caniuse.com/#search=classList
 [2]: https://developer.mozilla.org/en-US/docs/Web/API/element.classList