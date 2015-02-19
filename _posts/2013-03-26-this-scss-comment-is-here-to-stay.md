---
title: This (S)CSS comment is here to stay!
author: Martin Wolf
layout: post
permalink: /2013/03/26/this-scss-comment-is-here-to-stay/
categories:
  - Articles
tags:
  - comment
  - compass
  - css
  - scss
  - tip
---
Apparently compass doesn&#8217;t remove comments which are formatted like the following example when you compile your SCSS; no matter which `output_style` you define in your `config.rb`.

<pre><code class="language-css">/*! This comment will stay here forever */</code></pre>

This took me a while to figure out. Hope this saves you some precious time.