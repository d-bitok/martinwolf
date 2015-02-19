---
title: Say hello to marcel.io
author: Martin Wolf
layout: post
permalink: /2014/07/22/say-hello-to-marcel-io/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_737878756275409";s:5:"pDate";s:19:"2014-07-22 07:41:36";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"491488183272898560";s:5:"pDate";s:19:"2014-07-22 07:41:29";}}";'
categories:
  - Articles
tags:
  - marcel.io
  - one-pager
  - picturefill
  - portfolio site
  - release
  - responsive
  - rwd
  - scss
  - srcset
  - website
---
**A few weeks back my good friend [Marcel][1] decided that he needs a new portfolio site to show off some of his best work to kickstart his freelance business. If you already follow me along for quite a while you know that we worked together a lot so it was a natural fit that I would develop the site.**

[<img src="http://martinwolf.org/wp-content/uploads/2014/07/marcel-io-1.jpg" alt="marcel-io-1" width="600" height="641" class="alignnone size-full wp-image-2810" />][2]  
<!--more-->

Marcel made a clean one-pager layout that focuses on the different app designs. Since the site is very simple and won&#8217;t change that often we decided to omit a CMS and build a static site. It&#8217;s probably also faster.

For me it was a nice project to try a few things and most of all get to know Vim without the pressure of a big client projects deadline. The site is fully responsive, retina ready and makes use of SVGs where possible. I also tried to build modular Scss and added some custom jQuery Javascript. The sliders are based on the amazing [bxSlider][3].

[<img src="http://martinwolf.org/wp-content/uploads/2014/07/marcel-io-2.jpg" alt="marcel-io-2" width="600" height="641" class="alignnone size-full wp-image-2809" />][2] 

We tried to keep the size of the page small, but due to the sheer amount of screens it&#8217;s not the slimmest site ever although we made use of [`srcset`][4] and [picturefill][5].

[**Visit marcel.io**][2]&nbsp;

That&#8217;s basically it. If you want to know more you can have a look at the [code on GitHub][6], send me a tweet [@_martinwolf][7] or write an email to martin@martinwolf.org

 [1]: http://uarrr.org
 [2]: http://marcel.io
 [3]: http://bxslider.com
 [4]: http://martinwolf.org/2014/05/07/the-new-srcset-and-sizes-explained/
 [5]: http://scottjehl.github.io/picturefill/
 [6]: https://github.com/martinwolf/marcel-io
 [7]: http://twitter.com/_martinwolf