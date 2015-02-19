---
title: Chrome Canary Network Tab Improvement
author: Martin Wolf
layout: post
permalink: /2015/01/12/chrome-canary-network-tab-improvement/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_832446166818667";s:5:"pDate";s:19:"2015-01-12 07:47:50";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"554545242016600064";s:5:"pDate";s:19:"2015-01-12 07:47:43";}}";'
categories:
  - Articles
tags:
  - chrome canary
  - dev tools
  - Network Tab
  - performance
  - Timeline
  - TTFB
  - update
---
**Being a web developer these days is incredible. The built-in Developer Tools of browsers like Firefox and Chrome are awesome and even the one from Safari isn&#8217;t that bad anymore. And what&#8217;s even cooler, they get better every couple of weeks.**

A recent update to Chrome Canary (Version 41) made the Network Tab Timeline easier to use more useful. You can now see at a glance where the time was spent loading resources!

<!--more-->

In the settings of the Developer Tools you can now find a section called &#8220;Network&#8221; with an option called &#8220;Color-code resource types&#8221;.

<img class="alignnone size-full wp-image-3352" srcset="http://martinwolf.org/wp-content/uploads/2015/01/settings.png 710w, http://martinwolf.org/wp-content/uploads/2015/01/settings.png 1420w, http://martinwolf.org/wp-content/uploads/2015/01/settings.png 360w, http://martinwolf.org/wp-content/uploads/2015/01/settings.png 720w, http://martinwolf.org/wp-content/uploads/2015/01/settings.png 280w, http://martinwolf.org/wp-content/uploads/2015/01/settings.png 560w" sizes="(max-width: 640px) calc(100vw - 4rem), (max-width: 900px) calc(((100vw - 2rem) * 0.666) - 2rem), 710px" /> 

This option was the previous default. If it&#8217;s checked the Network Timeline looks like this:

<img class="alignnone size-full wp-image-3353" srcset="http://martinwolf.org/wp-content/uploads/2015/01/before-710x765.png 710w, http://martinwolf.org/wp-content/uploads/2015/01/before.png 1420w, http://martinwolf.org/wp-content/uploads/2015/01/before-360x388.png 360w, http://martinwolf.org/wp-content/uploads/2015/01/before-720x776.png 720w, http://martinwolf.org/wp-content/uploads/2015/01/before-280x302.png 280w, http://martinwolf.org/wp-content/uploads/2015/01/before-560x603.png 560w" sizes="(max-width: 640px) calc(100vw - 4rem), (max-width: 900px) calc(((100vw - 2rem) * 0.666) - 2rem), 710px" /> 

Each resource type has a different color, which is nice, but the various stages of the loading process aren&#8217;t easily recognizable. **Deactiving the color-coding instead shows different colors for the various stages and you can easily spot where you are losing precious milliseconds** as soon as you&#8217;ve learned which color represents what. But that shouldn&#8217;t be a problem. In addition you can always hover over the bars to get even more detailed information.

<img class="alignnone size-full wp-image-3354" srcset="http://martinwolf.org/wp-content/uploads/2015/01/after-710x765.png 710w, http://martinwolf.org/wp-content/uploads/2015/01/after.png 1420w, http://martinwolf.org/wp-content/uploads/2015/01/after-360x388.png 360w, http://martinwolf.org/wp-content/uploads/2015/01/after-720x776.png 720w, http://martinwolf.org/wp-content/uploads/2015/01/after-280x302.png 280w, http://martinwolf.org/wp-content/uploads/2015/01/after-560x603.png 560w" sizes="(max-width: 640px) calc(100vw - 4rem), (max-width: 900px) calc(((100vw - 2rem) * 0.666) - 2rem), 710px" /> 

In this screenshot you can see that the time to first byte/TTFB (green) for ei.js as well as the initial connection (orange) is very slow.

I think that&#8217;s a great option to have in Chrome Dev Tools. Every update to either Chrome Canary or Firefox Developer Edition makes me want to switch to the other one. Although in this case the Firefox Developer Edition Dev Tools already have this feature. Anyway, it&#8217;s really nice to see both teams doing so well at the moment.