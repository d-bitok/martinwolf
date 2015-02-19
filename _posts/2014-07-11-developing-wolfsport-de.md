---
title: Developing wolfsport.de
author: Martin Wolf
layout: post
permalink: /2014/07/11/developing-wolfsport-de/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"487492395219828736";s:5:"pDate";s:19:"2014-07-11 07:03:38";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_732481480148470";s:5:"pDate";s:19:"2014-07-11 07:03:44";}}";'
categories:
  - Articles
tags:
  - Case Study
  - github
  - Theme
  - wolfsport
  - wordpress
---
**Somewhen last week Henning, my brother, decided he wanted to start blogging. The topic should be sports in general, but mainly soccer. We decided to use WordPress and naturally I wanted to build a custom theme for him.  
**  
So on the weekend we had a Skype session with screen sharing and build him a relatively simple theme. The name was clear pretty early on: [wolfsport.de][1]

<img src="http://martinwolf.org/wp-content/uploads/2014/07/b9wVcTyFX.png" alt="b9wVcTyFX" width="836" height="1027" class="alignnone size-full wp-image-2763" /> 

The focus should be the text, so we went for a single small column and the nice typeface [Fira Sans][2].  
He had a pretty specific idea for a logo, which we put together with my little bit rusty Photoshop skills. It would be nice to have the logo as an SVG, but I only had raster graphics to work with. Maybe I can rework the logo in Illustrator in the future.

I didn&#8217;t use any frameworks or the like for the frontend, only some styles from my own, incomplete boilerplate like my slim `<a href="https://github.com/martinwolf/boilerplate">_normalize.scss</a>`. The site is complete responsive, but because of the simplicity of the theme, there wasn&#8217;t much to do to accomplish that.

On the WordPress side of things we use [Cachify][3] to cache and deliver static, minified HTML which speeds up the site tremendously. I also installed [Statify][4] so Henning can get a sense of how popular his blog gets. That&#8217;s about it.

It took us about four hours from idea to finished WordPress site. If you want to have a look at the code, it&#8217;s on GitHub: <https://github.com/martinwolf/wolfsport>

 [1]: http://wolfsport.de
 [2]: https://www.mozilla.org/en-US/styleguide/products/firefox-os/typeface/
 [3]: http://cachify.de/
 [4]: http://statify.de/