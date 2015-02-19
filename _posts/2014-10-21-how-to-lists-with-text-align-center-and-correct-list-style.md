---
title: 'How-To: Lists with text-align: center and correct list-style'
author: Martin Wolf
layout: post
permalink: /2014/10/21/how-to-lists-with-text-align-center-and-correct-list-style/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"524494713861447681";s:5:"pDate";s:19:"2014-10-21 09:37:39";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_783964138333537";s:5:"pDate";s:19:"2014-10-21 09:37:47";}}";'
categories:
  - Articles
tags:
  - list-style-position
  - lists
  - ol
  - text-align center
  - ul
---
Let&#8217;s say you have a standard `ul` or `ol` and set it to `text-align: center;`. Then you get this:

<img class="alignnone size-full wp-image-3040" srcset="http://martinwolf.org/wp-content/uploads/2014/10/ps75zUHS9.png 710w, http://martinwolf.org/wp-content/uploads/2014/10/ps75zUHS9.png 1420w, http://martinwolf.org/wp-content/uploads/2014/10/ps75zUHS9-360x71.png 360w, http://martinwolf.org/wp-content/uploads/2014/10/ps75zUHS9.png 720w, http://martinwolf.org/wp-content/uploads/2014/10/ps75zUHS9-280x55.png 280w, http://martinwolf.org/wp-content/uploads/2014/10/ps75zUHS9.png 560w" sizes="(max-width: 640px) calc(100vw - 4rem), (max-width: 900px) calc(((100vw - 2rem) * 0.666) - 2rem), 710px" /> 

I think we can agree that that&#8217;s not looking good. You could just hide the list style with `list-style: none;` but that might not be acceptable. Another possible way would be to hide the list styles and create your own list style with a `::before` pseudo element and it&#8217;s `content` property.

**But there is a much easier way: `list-style-position: inside;`**

<p data-height="337" data-theme-id="1276" data-slug-hash="xsvKc" data-default-tab="result" data-user="martinwolf" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/xsvKc/'>List with text-align center and bullets</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
</p>