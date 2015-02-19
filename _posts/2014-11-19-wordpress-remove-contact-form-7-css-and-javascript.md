---
title: 'WordPress: Remove Contact Form 7 CSS and Javascript'
author: Martin Wolf
layout: post
permalink: /2014/11/19/wordpress-remove-contact-form-7-css-and-javascript/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_798931530170131";s:5:"pDate";s:19:"2014-11-19 13:43:38";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"535065877310623744";s:5:"pDate";s:19:"2014-11-19 13:43:40";}}";'
categories:
  - Articles
tags:
  - Contact Form 7
  - css
  - js
  - plugins
  - wordpress
---
**One of my biggest problems with WordPress plugins is that they often just throw a bunch of CSS and JS at your page which you often either don&#8217;t need or just don&#8217;t want to use an extra request.**

Contact Form 7 does the same and I really don&#8217;t want an extra request for that CSS which I will override anyway. And I can also gladly do without the Javascript. If the Javascript is not included Contact Form 7 will just reload the page after submitting the form. This is fine for me in most cases.

To achieve that you add the following to your wp-config.php:

<pre><code class="lang-php" >/**
 * Remove Contact Form 7 Stuff
 */
define('WPCF7_LOAD_JS', false);
define('WPCF7_LOAD_CSS', false);</code></pre>

This will remove all of the Contact Form 7 Javascript and CSS.