---
title: Show content on top of YouTube video
author: Martin Wolf
layout: post
permalink: /2013/04/03/show-content-on-top-of-youtube-video/
categories:
  - Snippets
tags:
  - flash
  - iframe
  - opaque
  - snippet
  - wmode
  - youtube
---
I just ran into the problem that I needed a YouTube video to play in the background and have some other content covering it. Worked fine in all major browsers out of the box but for IE (all versions) you need to add `wmode=opaque` at the end of the `src` attribute like that:

<pre><code class="language-markup">&lt;iframe width="640" height="480" src="http://www.youtube.com/embed/9B7te184ZpQ&wmode=opaque" frameborder="0" allowfullscreen&gt;&lt;/iframe&gt;</code></pre>