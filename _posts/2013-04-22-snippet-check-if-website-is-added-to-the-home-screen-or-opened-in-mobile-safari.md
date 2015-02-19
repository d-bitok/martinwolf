---
title: 'Snippet: Check if website is added to the home screen or opened in mobile safari'
author: Martin Wolf
layout: post
permalink: /2013/04/22/snippet-check-if-website-is-added-to-the-home-screen-or-opened-in-mobile-safari/
categories:
  - Snippets
tags:
  - homescreen
  - iOS
  - javascript
  - js
  - snippet
  - web app
---
<pre class="lang-javascript"><code>if(navigator.standalone === undefined || !!navigator.standalone) {
    // if added to home screen do this
} else {
    // if opened in mobile safari do this
}</code></pre>