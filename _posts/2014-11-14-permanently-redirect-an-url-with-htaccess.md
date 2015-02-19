---
title: Permanently Redirect an url with .htaccess
author: Martin Wolf
layout: post
permalink: /2014/11/14/permanently-redirect-an-url-with-htaccess/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_796450597084891";s:5:"pDate";s:19:"2014-11-14 11:36:15";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"533222041370234880";s:5:"pDate";s:19:"2014-11-14 11:36:56";}}";'
categories:
  - Articles
  - Snippets
tags:
  - 301
  - htaccess
  - redirect
  - server
  - snippet
---
This blog once was called TheAmazingWeb.net and as I changed it to MartinWolf.org I didn&#8217;t want to loose all the backlinks which came in via the old domain. To achieve this I just checked a setting on the website of my webhoster.

Recently I moved off this simple managed hosting package because I wanted to be able to install things like the IRC Client Shout, weechat, cGit and more. Just to try things out and broaden my horizon. With that I lost the simple just working out of the box redirect.

I almost forgot about the old links. But I&#8217;ve now fixed it and all the old theamazingweb.net links are working properly again. That&#8217;s very comforting.

I&#8217;ve accomplished that with only four lines in the .htaccess of the old domain:

<pre><code class="lang-markup" >RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} !newdomain.org$ [NC]
RewriteRule ^(.*)$ http://newdomain.org/$1 [L,R=301]</code></pre>

This permanently redirects (301) the old domain (theamazingweb.net) to the new one (martinwolf.org). It even detects all the deeplinks. Magic in my eyes!