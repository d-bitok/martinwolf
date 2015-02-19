---
title: 'Introducing: gif.martinwolf.org'
author: Martin Wolf
layout: post
permalink: /2015/01/15/introducing-gif-martinwolf-org/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_834165666646717";s:5:"pDate";s:19:"2015-01-15 10:57:40";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"555680212034539520";s:5:"pDate";s:19:"2015-01-15 10:57:41";}}";'
categories:
  - Articles
tags:
  - Casestudy
  - code
  - css
  - fun
  - gifs
  - php
  - sideproject
---
**Being a freelancer and doing a lot of serious work for clients had me wondering where the fun in just developing simple, little and maybe stupid things has gone.**

So last weekend I sat down in the living room in a comfy chair and just started to build this [collection of gifs][1] which had been sitting in a folder for quite a while. This simple one-pager automatically loads all the gifs from a folder and shows them in grid with the according url. I used opportunity and learned a few simple things about PHP and tried laying out a grid with [Flexbox][2].

<!--more-->

<pre><code class="lang-php" >&lt;?php
    $images = glob("img/*.gif");
?&gt;</code></pre>

This snippet grabs all gif files from the `img` folder.

<pre><code class="lang-php" >&lt;ul class="list"&gt;
    &lt;?php foreach($images as $image) { ?&gt;
        &lt;?php $image_dimensions = getimagesize($image)[3]; ?&gt;
        &lt;li class="list__item"&gt;
            &lt;img
                src="&lt;?php echo $image ?&gt;"
                &lt;?php echo $image_dimensions ?&gt;
                alt="&lt;?php echo $image ?&gt;"&gt;

            &lt;input
                onFocus="this.select()"
                class="path"
                readonly
                type="text"
                value="http://&lt;?php echo $_SERVER['HTTP_HOST'].'/'.$image ?&gt;"&gt;
        &lt;/li&gt;
    &lt;?php } ?&gt;
&lt;/ul&gt;</code></pre>

Next I loop through all images and show them as a list. I get the dimensions with `getimagesize($image)[3];` which returns an array which 4th (you need to use 3 in the code because the array starts at 0) key value consists of the HTML for width and height (width=&#8221;400&#8243; height=&#8221;200&#8243; for example). Displaying the images would also work without these HTML attributes but the rendering is faster with them.

If you click inside the input below the image the text automatically gets selected which is a nice thing to have. This is achieved with `onFocus="this.select()"`. The input field is also set to `readonly` because there&#8217;s no reason to edit it and would just be confusing if you could.

The value of the input field is the url to the according gif which I put together with the PHP variable `$_SERVER['HTTP_HOST']` (in this case gif.martinwolf.org) and the image path we get from grabbing the image from the `img` folder.

Because the CSS is very small I inlined it in the head to save a request. I also use a Webfont from Google which is loaded asynchronously via their Javascript snippet. Thinking about how little text is actually on the page this is probably wasted bandwidth but I felt like using a custom font.

That&#8217;s it. If I find a new gif I like, I just drop it into the `img` folder and that&#8217;s it. If you want to have a look at the complete code you can do so on [GitHub][3] and if you want to link to the gifs, [go for it][1].

 [1]: http://gif.martinwolf.org
 [2]: http://css-tricks.com/snippets/css/a-guide-to-flexbox/
 [3]: https://github.com/martinwolf/gif.martinwolf.org