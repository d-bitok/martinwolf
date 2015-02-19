---
title: Remove HTML Comments with PHP
author: Martin Wolf
layout: post
permalink: /2013/02/21/remove-html-comments-with-php/
linked_list_url:
  - http://davidwalsh.name/remove-html-comments-php
categories:
  - Linked List
tags:
  - functions.php
  - html comments
  - php
  - wordpress
---
<p class="linked-list-quote-author">
  David Walsh:
</p>

> There&#8217;s no reason for HTML comments to be sent down to the user &#8212; they simply bloat the payload.

That&#8217;s why I switched to marking up comments with PHP, they won&#8217;t be send over the wire to the user. But nevertheless, David has a nice small function for your WordPress `functions.php` which will remove all of your HTML comments.