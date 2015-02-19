---
title: 'Polylang Snippet: Automatically get id of translated page'
author: Martin Wolf
layout: post
permalink: /2014/07/30/polylang-snippet-automatically-get-id-of-translated-page/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_742022365861048";s:5:"pDate";s:19:"2014-07-30 17:58:27";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"494542554633748480";s:5:"pDate";s:19:"2014-07-30 17:58:27";}}";'
categories:
  - Snippets
tags:
  - Multi Language
  - php
  - Polylang
  - snippet
  - wordpress
---
**I&#8217;m currently working on a multi-language WordPress site project and while I&#8217;m trying to build everything without having to rely on specific page id&#8217;s, it happens from time to time.**

I&#8217;m using [Polylang][1] to achieve the multi-lang capability and this plugin is great. Thanks for the recommendation goes out to [Nils][2].

Let&#8217;s say our default language is german and you need the title of a specific page and this page has the id of 52. This is how you would normally do it:

<!--more-->

<pre><code class="lang-php" >&lt;?php echo get_the_title(52); ?&gt;</code></pre>

But this will always return the german title of this page no matter the current language. That&#8217;s because with Polylang a translation is just a new page which is internally linked to the other. This means the translation of page id 52 might actually be page id 106.

So while I need the title of page id 52 in the default language I want to output the title of page id 106 when english is active.

Luckily there&#8217;s an easy way to do that with Polylang:

<pre><code class="lang-php" >&lt;?php echo get_the_title(pll_get_post(52)); ?&gt;</code></pre>

This will recognise the link between page id 52 and 106, check the current language and use the right id. Happy end!

 [1]: http://polylang.wordpress.com/
 [2]: http://noxoc.de