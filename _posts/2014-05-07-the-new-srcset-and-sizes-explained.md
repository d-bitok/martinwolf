---
title: The new srcset and sizes explained
author: Martin Wolf
layout: post
permalink: /2014/05/07/the-new-srcset-and-sizes-explained/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:261:"a:1:{i:0;a:9:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:38:"New post on TheAmazingWeb.net: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";}}";'
snapTW:
  - 's:267:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:14:"%TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"463949172433903618";s:5:"pDate";s:19:"2014-05-07 07:51:17";}}";'
categories:
  - Articles
tags:
  - codepen
  - explained
  - github
  - help
  - howto
  - picture
  - responsive images
  - rwd
  - sizes
  - srcset
  - tutorial
---
**Last sunday I sat down on my couch, got comfy and started reading up on the new `srcset` and `sizes` syntax. I wanted to understand it and then starting to use it now with the awesome picture/srcset/sizes polyfill [picturefill 2][1].  
**

## Personal struggle

But after some time of reading I had to face it — I just wasn&#8217;t able to grasp it, to understand the thought behind it and the overall system. I felt paralysed, sitting in this comfy spot not knowing what to do or who to ask. I felt that it wasn&#8217;t all that complicated but I didn&#8217;t understand it anyway. It made me anxious. Am I not good enough? This is the future of images on the web, I have to understand it. If I&#8217;m not even understanding this simple code, how will I ever be able to help others?

I took a deep breath and started reading again. I read the important parts again and again and then I started to build a simple test case. I experimented with different values, always resizing the browser and analysing what was happening. And finally it made click and I understood it.

It was a relief and I was very happy that I stuck it out and didn&#8217;t give in to me feeling bad about myself. So now here I am, hoping to explain to you in simple words the new `srcset` and `sizes` syntax for responsive images.

## How `srcset` and `sizes` work

**It&#8217;s important to note that this new `srcset` has nothing to do with the [old draft from 2012][2].**

There are now two responsive images solutions which can be combined or used on their own. This article focuses on the simpler one, which will do for almost all responsive content images, which aren&#8217;t art directed and should just stretch and squish with `max-width: 100%;`.

Until now we used media queries to determine which size the viewport is and which pixel density the screen has and load a specific source according to that. With `srcset` we don&#8217;t need that anymore.

We don&#8217;t tell the browser which source it should display at which screen size and pixel density, because that is inflexible and lead to dozens of lines of code and definitions just for one single image. Even worse, it&#8217;s not really future proof and we only support pixel densities that we defined. What if a 4x screens comes along tomorrow? Did you write media queries to support that? I haven&#8217;t. But with `srcset` we are covered.

What we do with `srcset` and `sizes` is, we tell the browser which sources, aka files, it has at its disposal and which width they have. Then we also tell the browser how wide the image should be displayed at any given viewport width. The browser now knows everything it needs to know to decide which image is appropriate to use. I like to imagine the img tag as a container. We as developers only define how big the container should be at any given point and the browser decides which source to load to get the best output for the user.

So while at first this might not seem like a big win, the browser is much smarter than we are and is now able to use the right source at the right time. For example, it could load the medium sized image in your mobile breakpoint as the source because the screen has 2x resolution or if a 3x screen comes along it can automatically choose to load the large sized source. To achieve this with media queries you had to write dozens of them covering every possible case. That&#8217;s tedious and prone to errors.  
The browser is/will also be capable of loading a lower resolution source when it detects that bandwidth is slow. How awesome is that?

## The syntax

<pre><code class="lang-markup">&lt;article&gt;
    &lt;img srcset="large.jpg 1400w, medium.jpg 700w, small.jpg 400w"
         sizes="(min-width: 700px) 700px, 100vw"
         alt="A woman reading"&gt;
&lt;/article&gt;</code></pre>

<pre><code class="lang-css">* {
    margin: 0;
    padding: 0;
}

article {
    margin: 0 auto;
    max-width: 700px;
}

img {
    max-width: 100%;
}</code></pre>

In the `srcset` attribute we define the image sources and tell the browser the width of each one. In the `sizes` attribute we then use media query expressions to define the width of the image at any given point. These breakpoints should mirror your page’s breakpoints. The length after each media query specifies the width of the image if the media query is true. The last value is the default value. Remember that these length values are all relative to the viewport. 100vw is the full with of the viewport as is 100%. So 80% is 80% of the viewport width not of the container div the image is in or something like that. Here you can find a list of possible lengths: <http://www.w3.org/TR/css3-values/#lengths>

The sample code above describes a simple one column blog that has a max-width of 700px. In this case that means the column is always 100% wide until it the viewport&#8217;s width is larger than 700px. The image is always as wide as the encircling article tag. This means the default `sizes` values is 100vw and as soon as the the viewport is 700px or wider, the image just stays at these 700px.

Here you can see it in action: [srcset and `sizes` demonstration on CodePen][3].

It looks as we could just use 100% as the size for the image if the media query evaluates to true, but that&#8217;s wrong. Remember, the length it relative to the viewport and not to the article element. So if the viewport is 1400px wide, the browser would load the larger image source even though we don&#8217;t need it to. We don&#8217;t want that.

I made a test case so you can have a look at the code and try it yourself. I hope this introduction to `srcset` and `sizes` helped you getting started. I still recommend that you grab a copy of picturefill, fire up your favourite editor and try it yourself. There is nothing better to learn and really understand new things than doint them yourself.

**Here you can find the CodePen, fork it and discover how awesome `srcset` and `sizes` are: [srcset and sizes Testcase code on CodePen][4]  
Or if you want to fork and download the code to try it locally, I also put it up on GitHub: [srcset and sizes Testcase on GitHub][5]**

Still having trouble with `srcset` and `sizes`? Tweet me [@_martinwolf][6], send me an email at martin@martinwolf.org or have a look at this long form [article on picture and srcset/sizes][7] by Eric Portis.

 [1]: http://scottjehl.github.io/picturefill/
 [2]: http://lists.whatwg.org/htdig.cgi/whatwg-whatwg.org/2012-May/035855.html
 [3]: http://codepen.io/martinwolf/full/0fad73c3ab0275ebe69c7db17eb250fb/
 [4]: http://codepen.io/martinwolf/pen/hFxyj/
 [5]: https://github.com/martinwolf/srcset-sizes-testcase
 [6]: http://twitter.com/_martinwolf
 [7]: http://ericportis.com/posts/2014/srcset-sizes