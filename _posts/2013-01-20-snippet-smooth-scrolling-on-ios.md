---
title: 'Snippet: Smooth scrolling on iOS'
author: Martin Wolf
layout: post
permalink: /2013/01/20/snippet-smooth-scrolling-on-ios/
categories:
  - Snippets
tags:
  - bounce
  - iOS
  - overflow-scrolling
  - scrolling
  - smooth
  - snippet
  - touch
  - webkit
---
Let&#8217;s assume you have a container in which you need to scroll. You just set a specific height and width and set it to `overflow-y: scroll;` No big deal, eh? But if you try to scroll within this container on your iOS device you&#8217;ll notice that it doesn&#8217;t scroll very smoothly and it doesn&#8217;t bounce at the top and end. But you can change this very simply:

<pre class="language-css"><code class="language-css">.my-container {
  overflow-y: scroll;
  -webkit-overflow-scrolling: touch;
}</code></pre>