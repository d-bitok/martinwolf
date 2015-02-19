---
title: Custom WordPress Template Includes
author: Martin Wolf
layout: post
permalink: /2014/11/26/custom-wordpress-template-includes/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_802351443161473";s:5:"pDate";s:19:"2014-11-26 12:26:20";}}";'
snapTW:
  - 's:308:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:52:"[Snippet] Custom @WordPress Template Includes: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"537583133160640512";s:5:"pDate";s:19:"2014-11-26 12:26:21";}}";'
categories:
  - Snippets
tags:
  - Includes
  - Learn WordPress
  - php
  - Templates
  - wordpress
---
**What if `<?php get_header(); ?>`, `<?php get_footer(); ?>` and the other few WordPress includes aren&#8217;t enough and you would like to split your template files into smaller parts?**

There is a quite nice and easy way to import PHP template parts into your usual WordPress templates:

<pre><code class="lang-php" >&lt;?php include (TEMPLATEPATH . '/includes/my-template-part.php'); ?&gt;</code></pre>

`TEMPLATEPATH` points into the folder of your theme. There I usually create a folder for includes. Hope that helps!

### Update

Or you could use `get_template_part`.

<pre><code class="lang-php" >&lt;?php get_template_part( 'includes/my-template-part' ); ?&gt;</code></pre>