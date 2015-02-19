---
title: Open files in Atom Editor from the command line
author: Martin Wolf
layout: post
permalink: /2014/04/29/open-files-in-atom-editor-from-the-command-line/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:261:"a:1:{i:0;a:9:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:38:"New post on TheAmazingWeb.net: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";}}";'
snapTW:
  - 's:281:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:28:"New blog post: %TITLE% %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"461059855504375809";s:5:"pDate";s:19:"2014-04-29 08:30:10";}}";'
categories:
  - Articles
tags:
  - Atom Editor
  - command line
  - Quicktip
---
If you are like me and spent quite some time on the command line, navigating directories, using git, grunt and all the other fancy things, you might want to open files and folders in your favourite editor right from where you are.

When using [Atom Editor][1], this is very easy. Atom automatically creates a sym link in your /usr/local/bin when it&#8217;s installed. That means you can use these commands:

#### Open current folder:

<pre class="lang-markup"><code>$ atom .</code></pre>

#### Open a file

<pre class="lang-markup"><code>$ atom style.scss</code></pre>

#### Just open Atom

<pre class="lang-markup"><code>$ atom</code></pre>

 [1]: http://atom.io/