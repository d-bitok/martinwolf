---
title: 'Snippet: Styling HTML5 Placeholder'
author: Martin Wolf
layout: post
permalink: /2012/10/24/snippet-styling-html5-placeholder/
categories:
  - Snippets
tags:
  - css
  - html5
  - placeholder
  - snippet
---
You are using the HTML5 `placeholder="Your name"` attribute but don&#8217;t know how to style it? Here is how you do it:

<pre class="lang-css"><code class="lang-css">.my-input::-webkit-input-placeholder {
    color: #555;
}

.my-input:-moz-placeholder {
    color: #555;
}

.my-input:-ms-input-placeholder {
    color: #555;
}</code></pre>

Make sure you don&#8217;t comma separate the selectors because browsers stop interpreting the whole list if they don&#8217;t understand one selector in it.