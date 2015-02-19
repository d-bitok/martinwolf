---
title: Play iFrame embedded YouTube video on click of a button
author: Martin Wolf
layout: post
permalink: /2013/12/17/play-iframe-embedded-youtube-video-on-click-of-a-button/
nxs_snap_sh_FB0_1387290251:
  - 'a:24:{s:4:"doFB";i:1;s:5:"nName";s:8:"Facebook";s:7:"fbAppID";s:15:"547424155328706";s:8:"fbAppSec";s:32:"7cb4de34e0ff8039f7c03541f99c8105";s:8:"catSelEd";s:0:"";s:10:"fbPostType";s:1:"A";s:7:"fbAttch";s:1:"2";s:12:"fbAttchAsVid";i:0;s:6:"imgUpl";s:1:"1";s:11:"fbMsgFormat";s:44:"New post on TheAmazingWeb.net: %TITLE% %URL%";s:10:"fbMsgAFrmt";s:0:"";s:10:"riComments";i:0;s:12:"riCommentsAA";i:0;s:5:"fbURL";s:41:"https://www.facebook.com/visuellegedanken";s:6:"fbPgID";s:16:"visuellegedanken";s:6:"catSel";s:1:"0";s:14:"fbAppAuthToken";s:183:"CAAHx4R5R4MIBAN5RO4N873D8mKgRvoi8q7mqc9djALiq5tkKfAbmI84x09uohZAzhxGmW8e9vHWKp3ezhz9WnIywE5yi4kyZA4UyZAMFgJZAhTimmRtcgZC6jqvZCtj5BEFPbq76oKuIKxrxPJR9K1KR7bBupOnGFlzYXF61AXITbDcshKaXN2";s:18:"fbAppPageAuthToken";s:183:"CAAHx4R5R4MIBAN5RO4N873D8mKgRvoi8q7mqc9djALiq5tkKfAbmI84x09uohZAzhxGmW8e9vHWKp3ezhz9WnIywE5yi4kyZA4UyZAMFgJZAhTimmRtcgZC6jqvZCtj5BEFPbq76oKuIKxrxPJR9K1KR7bBupOnGFlzYXF61AXITbDcshKaXN2";s:13:"fbAppAuthUser";s:10:"1607117196";s:8:"isPosted";s:0:"";s:8:"imgToUse";b:0;s:8:"urlToUse";b:0;s:2:"ii";i:0;s:9:"timeToRun";i:1387290251;}'
snap_isAutoPosted:
  - 1
nxs_snap_sh_TW0_1387290253:
  - 'a:19:{s:4:"doTW";i:1;s:5:"nName";s:11:"_martinwolf";s:5:"twURL";s:30:"http://twitter.com/_martinwolf";s:9:"twConsKey";s:22:"43f4ucgXHmQ656M02ZBUxw";s:9:"twConsSec";s:42:"DrRkkZBFd0cClZD7dkNzUgimG9yud45yXIaXPUXn3c";s:10:"twAccToken";s:50:"15392033-DNYwP7PucUC9UGuba81ugP89CLdCf7MBB0zy3G9js";s:8:"catSelEd";s:0:"";s:10:"riComments";i:0;s:11:"riCommentsM";i:0;s:12:"riCommentsAA";i:0;s:13:"twAccTokenSec";s:42:"dnlfWj0ZBmBlrSpOVL7wJkFMfOc7Hfgexj7ykUKsXM";s:11:"twMsgFormat";s:14:"%TITLE%: %URL%";s:8:"attchImg";i:0;s:4:"twOK";i:1;s:6:"catSel";s:1:"0";s:8:"isPosted";s:0:"";s:8:"imgToUse";b:0;s:2:"ii";i:0;s:9:"timeToRun";i:1387290253;}'
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"PostType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:44:"New post on TheAmazingWeb.net: %TITLE% %URL%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:28:"1607117196_10201169333987915";s:5:"pDate";s:19:"2013-12-17 14:24:16";}}";'
snapTW:
  - 's:267:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:14:"%TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"412951394623426560";s:5:"pDate";s:19:"2013-12-17 14:24:19";}}";'
categories:
  - Articles
tags:
  - iframe
  - jquery
  - youtube
---
In a recent project I had to show and autoplay an embedded YouTube video on click of a button. My first reaction was to use the YouTube API, create the video on the fly with Javascript and have some functions at my finger tips to start the video and so on. But then I started to look around if it might be possible to do the same with the normal embedded iframe code and I did find something that is much easier than to do all this YouTube API stuff.

So if you just need to play the video on click and don&#8217;t need to know when it&#8217;s ended or do other things with it, that the YouTube API allows you to do, this is the solution you are looking for:

First we need a simple link and the iframe Embed Code.

<pre><code class="lang-markup">&lt;a id="play-video" href="#"&gt;Play Video&lt;/a&gt;
 
&lt;iframe id="video" width="420" height="315" src="//www.youtube.com/embed/9B7te184ZpQ?rel=0" frameborder="0" allowfullscreen&gt;&lt;/iframe&gt;</code></pre>

And then we write some simple jQuery, which on click just extends the YouTube video source with the autoplay parameter thus plays the video. I also prevent the link from behaving like it normally would. Simple as that.

<pre><code class="lang-javascript">$(document).ready(function() {
    $('#play-video').on('click', function(ev) {

        $("#video")[0].src += "&autoplay=1";
        ev.preventDefault();
 
    });
});</code></pre>

Maybe this is useful for some of you in the future. :) I also made a CodePen so you can see [the code in action][1].

 [1]: http://codepen.io/martinwolf/pen/dyLAC