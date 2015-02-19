---
title: How to load a part of a page via ajax
author: Martin Wolf
layout: post
permalink: /2014/12/09/how-to-load-a-part-of-a-page-via-ajax/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_809206222475995";s:5:"pDate";s:19:"2014-12-09 16:07:14";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"542349774499086336";s:5:"pDate";s:19:"2014-12-09 16:07:17";}}";'
categories:
  - Articles
tags:
  - ajax
  - howto
  - javascript
  - jquery
  - learn coding
  - load
  - tutorial
---
**I’m currently working on a small portfolio project where we want to have cool page transitions when the users goes from the homepage to a project single page without the classic reload which you normally get if you click on a link.**

I tried to use [smoothState.js][1] which loads the content of the target page via ajax, keeps your sites urls intact and you don’t have much to do except load the script and add a few lines of Javascript.

It works fine but it’s not flexible enough for what we want to do so I set out to write the whole thing myself. I’m not especially experienced with Ajax but there’s always something you don’t know even if you work on stuff you know a lot about, so I just gave it a try.

<pre><code class="lang-javascript">var projectContainer = $('#js_project-container');

$('.js_load-project').on('click', function(ev) {
    var href = $(this).attr('href');

    /**
     * Prevent default link behaviour
     */
    ev.preventDefault();

    /**
     * Load the project, then initiate the slides
     */
    projectContainer.load(href, doTheSlides);
});</code></pre>

If the user clicks a link on the homepage I load the content of the target url with jQuery’s [`.load()`][2] method. I prevent the browser from following the link and atfer the load event has finished I call the `doTheSlides` function, which handles the animations.  
After a few tests I was happy with the result besides that I loaded in the whole DOM including the complete `<head>` section.

After a few Google searches I found out that you can target a specific id on the target page you want to load and only grab the content of that specific element. Perfect.

**The updated code:**

<pre><code class="lang-javascript">var projectContainer = $('#js_project-container');

$('.js_load-project').on('click', function(ev) {
    var href = $(this).attr('href')+' #project';

    /**
     * Prevent default link behaviour
     */
    ev.preventDefault();

    /**
     * Load the project, then initiate the slides
     */
    projectContainer.load(href, doTheSlides);
});</code></pre>

This will only load the contents from `<div id="project"></div>` from the project single page and inject them into the `<div id="js_project-container"></div>` on the homepage.

**Make sure to add a space between the url you want to load and the target id. Otherwise it won&#8217;t work.  
And remember, the `.load` method only works with requests to the same domain, not cross-domain.**

Of course this is only a small portion of the complete solution I need for the project I&#8217;m working on but I thought it&#8217;s worth sharing. I hope somebody can make use of it.

 [1]: http://weblinc.github.io/jquery.smoothState.js/
 [2]: http://api.jquery.com/load/