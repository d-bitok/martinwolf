---
title: WordPress is_home() fixed
author: Martin Wolf
layout: post
permalink: /2014/05/02/wordpress-is_home-fixed/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:261:"a:1:{i:0;a:9:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:38:"New post on TheAmazingWeb.net: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";}}";'
snapTW:
  - 's:267:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:14:"%TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"462140369745219584";s:5:"pDate";s:19:"2014-05-02 08:03:45";}}";'
categories:
  - Articles
tags:
  - conditional tags
  - is_home
  - is_paged
  - theme building
  - wordpress
---
**WordPress has a whole lot of conditional tags build in that help you build themes. Recently I stumbled about a behaviour of `is_home()` that I didn&#8217;t expect.**

I thought there is only one time this would return `true`, namely on the homepage. But that&#8217;s not the case. `is_home()` returns `true` for the homepage and every single paginated page of a blog that is not the first one.

In my case I wanted the logo of the theme to be a link back to the homepage but not on the homepage itself, because it&#8217;s pointless.

Luckily there is another conditional tag called `is_paged()` which returns `true` if you are on a paginated page.

If we combine these two we can only display the normal link if it&#8217;s the homepage and not a paginated page and on all other pages we can use a link:

<pre><code  class="lang-php">&lt;?php if ( is_home() && !is_paged() ) { ?&gt;

    &lt;h1 class="site-header__title"&gt;
        &lt;?php bloginfo('name'); ?&gt;
    &lt;/h1&gt;

&lt;?php } else { ?&gt;

    &lt;a href="&lt;?php echo esc_url( home_url( '/' ) ); ?&gt;"&gt;
        &lt;?php bloginfo('name'); ?&gt;
    &lt;/a&gt;

&lt;?php } ?&gt;</code></pre>