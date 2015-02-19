---
title: 'Blink: The new rendering engine for the Chromium project'
author: Martin Wolf
layout: post
permalink: /2013/04/04/blink-the-new-rendering-engine-for-the-chromium-project/
linked_list_url:
  - http://blog.chromium.org/2013/04/blink-rendering-engine-for-chromium.html
categories:
  - Linked List
tags:
  - blink
  - browsers
  - chrome
  - google
  - opera
  - rendering engine
  - webkit
---
<p class="linked-list-quote-author">
  So just as a lot of people feared a Webkit monoculture Google decides to fork WebKit and go on with their own, new rendering engine called &#8216;<a href="http://www.chromium.org/blink">Blink</a>&#8216;:
</p>

> This was not an easy decision. We know that the introduction of a new rendering engine can have significant implications for the web. Nevertheless, we believe that having multiple rendering engines—similar to having multiple browsers—will spur innovation and over time improve the health of the entire open web ecosystem.

Interesting is that [Opera][1] is going with them and will also use Blink in the future. So that leaves WebKit more or less alone for Safari and iOS in general, which might slow down the development on this side. I hope Apple will allow different rendering engines on iOS in the future.

What&#8217;s really cool is, that Blink will [drop vendor prefixes][2] in the future.

Overall I think that diversity like that is good for the open and standards based web and will help pushing things forward. But I also thought that it&#8217;d be nice to have one browser engine less to test.

 [1]: http://www.brucelawson.co.uk/2013/hello-blink/
 [2]: http://www.chromium.org/blink#vendor-prefixes