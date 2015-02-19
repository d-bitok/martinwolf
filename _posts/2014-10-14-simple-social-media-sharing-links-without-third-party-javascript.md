---
title: Simple Social Media Sharing Links without Third Party Javascript
author: Martin Wolf
layout: post
permalink: /2014/10/14/simple-social-media-sharing-links-without-third-party-javascript/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_779952638734687";s:5:"pDate";s:19:"2014-10-14 08:37:16";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"521942772228829184";s:5:"pDate";s:19:"2014-10-14 08:37:08";}}";'
categories:
  - Articles
  - Snippets
tags:
  - facebook
  - Sharing Links
  - Social Media Sharing
  - twitter
  - wordpress
---
Recently I needed to implement social media sharing buttons into a project. We wanted to use custom icons and omit all the third party javascript. Luckily there are simple links you can use with some parameters for the big players like Twitter or Facebook.

<!--more-->

### Twitter Share Link

<pre><code class="lang-markup" >&lt;a href="https://twitter.com/home?status=Your%20custom%20tweet%20with%20blanks."&gt;Share on Twitter&lt;/a&gt;</code></pre>

### Twitter Share Link with WordPress Template Tags:

<pre><code class="lang-markup" >&lt;a href="https://twitter.com/home?status=Check%20out%20this%20article%20by%20@_martinwolf:%20&lt;?php the_title(); ?&gt; &lt;?php the_permalink(); ?&gt;"&gt;Share on Twitter&lt;/a&gt;</code></pre>

### Facebook Share Link

<pre><code class="lang-markup" >&lt;a href="https://www.facebook.com/sharer/sharer.php?u=http://mydomain.com/articletitle"&gt;Share on Facebook&lt;/a&gt;</code></pre>

### Facebook Share Link with WordPress Template Tags:

<pre><code class="lang-markup" >&lt;a href="https://www.facebook.com/sharer/sharer.php?u=&lt;?php the_permalink(); ?&gt;"&gt;Share on Facebook&lt;/a&gt;</code></pre>

### Google+ Share Link

<pre><code class="lang-markup" >&lt;a href="https://plus.google.com/share?url=http://mydomain.com/articletitle"&gt;Share on Google+&lt;/a&gt;</code></pre>

### Google+ Share Link with WordPress Template Tags:

<pre><code class="lang-markup" >&lt;a href="https://plus.google.com/share?url=&lt;?php the_permalink(); ?&gt;"&gt;Share on Google+&lt;/a&gt;</code></pre>

### Share via Mail Link

<pre><code class="lang-markup" >&lt;a href="mailto:?subject=Reading Recommendation&amp;body=Check out this article: Article Title http://mydomain.com/articletitle."&gt;Share via Mail&lt;/a&gt;</code></pre>

### Share via Mail Link with WordPress Template Tags:

<pre><code class="lang-markup" >&lt;a href="mailto:?subject=Reading Recommendation&amp;body=Check out this article: &lt;?php the_title(); ?&gt; &lt;?php the_permalink() ?&gt;."&gt;Share via Mail&lt;/a&gt;</code></pre>