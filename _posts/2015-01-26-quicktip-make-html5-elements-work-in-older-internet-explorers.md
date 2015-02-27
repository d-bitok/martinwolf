---
title: 'QuickTip: Make HTML5 elements work in older Internet Explorers'
author: Martin Wolf
layout: post
permalink: /2015/01/26/quicktip-make-html5-elements-work-in-older-internet-explorers/
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_839962796067004";s:5:"pDate";s:19:"2015-01-26 08:34:52";}}";'
snap_isAutoPosted:
  - 1
snapTW:
  - 's:279:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:23:"[Article] %TITLE% %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"559630540496982016";s:5:"pDate";s:19:"2015-01-26 08:34:53";}}";'
categories:
  - Articles
tags:
  - html5
  - HTML5shiv
  - internet explorer
  - Quicktip
---
[While we are talking][1] about older versions of Internet Explorer, there is a small Javascript called html5shiv.js which enables the use of HTML5 elements like `<article>` or `<section>` in IE6-9. You can download it here from GitHub: <https://github.com/aFarkas/html5shiv>.

Include the script in the head of your page, so IE knows the new elements before rendering them. You should do that with [Conditional Comments][2] to make sure that the file is only loaded for the browsers that need it, in this case IE9 and below.


{% highlight html %}
<!--[if lt IE 9]>
    <script src="js/html5shiv.js"></script>
<![endif]-->
{% endhighlight %}

 [1]: http://martinwolf.org/2015/01/22/ie78-friendly-nth-child/
 [2]: https://msdn.microsoft.com/en-us/library/ms537512%28v=vs.85%29.aspx
