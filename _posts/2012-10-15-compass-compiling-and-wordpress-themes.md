---
title: Compass Compiling and WordPress Themes
author: Martin Wolf
layout: post
permalink: /2012/10/15/compass-compiling-and-wordpress-themes/
linked_list_url:
  - http://css-tricks.com/compass-compiling-and-wordpress-themes/
categories:
  - Linked List
tags:
  - chris coyier
  - compass
  - css-tricks
  - style.css
  - wordpress
---
<p class="linked-list-quote-author">
  Chris Coyier:
</p>

> If you&#8217;re a WordPress theme builder and a Sass/Compass user, first, yay you are awesome! Second, there is this little issue that will probably crop up for you regarding compile locations, so let&#8217;s solve it now.

I know the problem that Chris is describing, but why not just use the `style.css` in the css folder instead of the one on the root level of your theme. The latter one can just hold the WordPress comments which are used for defining your Theme name, etc.  
The only thing you have to do is put the following in your `header.php`

<pre class="lang-markup"><code class="lang-markup">&lt;link href="&lt;?php bloginfo('template_url'); ?&gt;/css/style.css" type="text/css" rel="stylesheet"&gt;</code></pre>

Or am I missing something?