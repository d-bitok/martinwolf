---
title: What happens to :hover on touch devices?
author: Martin Wolf
layout: post
permalink: /2013/05/09/what-happens-to-hover-on-touch-devices/
categories:
  - Articles
tags:
  - hover
  - iOS
  - test
  - touch
---
**We all know the problem: There is no hover event on touch devices. So what happens on those devices with dropdown menus and other content that gets revealed only by an hover event?**

Over the past few days I heard different people say different things so I put together a simple CodePen to check what happens. This is what I found out:

If you take an `a` element which has an `href` attribute and tap it, the hover event gets triggered. A second tap will then take you to the `href` location. If you just want to reveal some content or something like that, you can simply use `href="javascript:;"` and the second tap will do nothing.

Using a `button` tag will do the same thing. But with all the other elements I tested nothing will happen if you tap on them, although it has an hover effect applied.

But that leaves us with an open dropdown or whatever your hover did. And as far as I can tell there is no way to hide the hover effect other than using Javascript.

Another interesting behaviour is that if you apply an hover effect to a simple link you will see the effect for a split second when you tap the link but you don&#8217;t need a second tap. But if you position another element in the `a` and actually select it on hover, you&#8217;ll need the second tap to actually go to the `href` location. This is what happens in my &#8220;reveal a box example&#8221; below.

I only tested it with my iPhone because I don&#8217;t have an Android device. But the CodePen is openly accessible and I&#8217;d love to hear how Android behaves. Feel free to @reply my on [Twitter][1] or write a [mail][2].

<pre class="codepen" data-height="300" data-type="result" data-href="FCznv" data-user="martinwolf" data-safe="true"><code></code><a href="http://codepen.io/martinwolf/pen/FCznv">Check out this Pen!</a></pre>

 [1]: http://twitter.com/_martinwolf
 [2]: mailto:martin@theamazingweb.net