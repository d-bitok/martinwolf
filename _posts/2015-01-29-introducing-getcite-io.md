---
title: 'Introducing: getcite.io'
author: Martin Wolf
layout: post
permalink: /2015/01/29/introducing-getcite-io/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"560816789228376064";s:5:"pDate";s:19:"2015-01-29 15:08:36";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_841924285870855";s:5:"pDate";s:19:"2015-01-29 15:08:56";}}";'
categories:
  - Articles
tags:
  - Case Study
  - cite
  - css
  - gulp
  - scss
  - website
---
<img class="alignnone size-full wp-image-3425" srcset="http://martinwolf.org/wp-content/uploads/2015/01/cite-acd-710x542.jpg 710w, http://martinwolf.org/wp-content/uploads/2015/01/cite-acd.jpg 1420w, http://martinwolf.org/wp-content/uploads/2015/01/cite-acd-360x275.jpg 360w, http://martinwolf.org/wp-content/uploads/2015/01/cite-acd-720x550.jpg 720w, http://martinwolf.org/wp-content/uploads/2015/01/cite-acd-280x214.jpg 280w, http://martinwolf.org/wp-content/uploads/2015/01/cite-acd-560x428.jpg 560w" sizes="(max-width: 640px) calc(100vw - 4rem), (max-width: 900px) calc(((100vw - 2rem) * 0.666) - 2rem), 710px" /> 

**A few weeks ago [Marcel][1] had an idea for a simple iOS app that acts as a sharing service for beautiful Textshots. Never heard the term?  
Over the past month more and more people take screenshots of articles with a marked text passage and share the image with a short commentary and the link on Twitter. These screenshots are called Textshots by a group of people. So why not go with it?**

As you know I&#8217;m not an iOS developer, but [Florian][2] is. So Flo and Marcel are in the process of building the iOS app: **[cite][3]**  
The app is currently in private beta status and a couple of people will get invited very soon. In the meantime I built the [website][3] to promote the app and explain the concept.

It&#8217;s a relatively simple one-pager product page and I tried to make it as fast as possible.  
The site was developed with vim in iTerm. My CSS preprocessor of choice is [SCSS][4] and the build system to put everything together and run a simple dev server is [gulp.js][5].  
It&#8217;s a static, minified HTML page. I used svg images for easy retina support where possible and [picturefill.js][6] for the responsive pixel image.  
The sliders are build with [Owl Carousel 2][7], which I used for the first time and I&#8217;m very pleased with.  
We use Mailchimp to send out news about cite and I implemented a form as simple as possible. All the validation happens after you hit the &#8220;Send&#8221; button and Mailchimp does everything for us. At first we hid the submit button and only send the form when the user hit enter, but it turns out mobile Safari didn&#8217;t like that.

If you want to dig deeper into the codebase, you can do that on [GitHub][8]. If you find a bug, please open an [issue][9]. Thank you!

 [1]: http://uarrr.org
 [2]: http://florianalbrecht.net
 [3]: http://getcite.io
 [4]: http://sass-lang.com/
 [5]: http://gulpjs.com/
 [6]: https://github.com/scottjehl/picturefill
 [7]: http://owlcarousel.owlgraphic.com/
 [8]: https://github.com/martinwolf/getcite.io
 [9]: https://github.com/martinwolf/getcite.io/issues