---
title: Vertically Written Text
author: Martin Wolf
layout: post
permalink: /2014/11/03/vertically-written-text/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"529280250262597632";s:5:"pDate";s:19:"2014-11-03 14:33:39";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_790881957641755";s:5:"pDate";s:19:"2014-11-03 14:33:46";}}";'
categories:
  - Articles
tags:
  - break-word
  - css
  - pure CSS vertical text
  - word-wrap
---
Ever wanted to create vertically written text? I mean the kind where the letters aren&#8217;t rotated, but just aligned one below the other.

You could easily achieve this effect by inserting a bunch of `<br>` tags, but that would be bad for Accessibility. Screenreaders for example might read letter after letter and don&#8217;t recognise that it&#8217;s one word. Furthermore it&#8217;s semantically bad.

<!--more-->

Luckily we can achieve this effect with the CSS property `word-wrap`. If you set `word-wrap` to `break-word`, it allows text to not only break after a complete word but to break a word apart. It&#8217;s ofter used to prevent a responsive design to break on long words or links.

Combine that with a `width` of 0 and your word breaks after every letter:

<p data-height="460" data-theme-id="1276" data-slug-hash="jfoIA" data-default-tab="result" data-user="martinwolf" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/jfoIA/'>Vertically Written Text</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
</p>