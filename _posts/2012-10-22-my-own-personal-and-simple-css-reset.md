---
title: My own personal and simple CSS reset
author: Martin Wolf
layout: post
permalink: /2012/10/22/my-own-personal-and-simple-css-reset/
categories:
  - Articles
tags:
  - boilerplate
  - css
  - normalize
  - reset
  - scss
---
**While I never was a fan of using a framework to help getting me started with a project I also never was a fan of CSS resets. I see the value in both of them, but they just aren&#8217;t for me. Let me tell you why.**

When not using a fancy CSS reset one could use [Normalize][1] to start with — probably smart — values which should let browsers display everything the same way if you&#8217;d just write HTML.  
But that isn&#8217;t for me either. I think all these clever frameworks or how you&#8217;d call them blow up my project with things I don&#8217;t know whether I need them or not before I even started.  
In almost no scenario I rely on the default behavior of the browser and just define my own values. And testing in all the different browsers I want to support is also part of my workflow.

You don&#8217;t have to agree with me, that&#8217;s just the way I see it because I write all the CSS I need anyway.

So for years I just started with this simple reset on the top of my CSS file:

<pre class="lang-css"><code class="lang-css">* {
	margin: 0;
	padding: 0;
}</code></pre>

Removing every `margin` and `padding` values from all elements was all I did and it worked great for me.  
Lately I added a few more things to my star selector. Let&#8217;s have a look:

<pre class="lang-css"><code class="lang-css">* {
	position: relative;
	margin: 0;
	padding: 0;
	list-style-type: none;
	@include box-sizing(border-box);
}</code></pre>

While coding away I realised that I was setting `position: relative;` all over the place. I often work with pseudo elements and position them absolute in context of their parent element so I need `position: relative;` every time. After thinking about it, I came to the conclusion that setting it on every element doesn&#8217;t do any harm, so why not just give it a try?  
So I just went with it and never looked back. There is rarely the case that I need to revert an element to `position: static;` and even if I need to, so what? It&#8217;s definitely less writing than the other way round.

The other thing I realised is that the only places I really want a `list-style` is in text blocks. So every time I create a list for a navigation or something like that I have to remove the `list-style-type`. Removing it for all elements turns out to be a smart thing, at least for me. I only have to set the wanted `list-style-type` in a few places.

Last but not least I set everything to `box-sizing: border-box;`. I use a SCSS include so that the generated CSS has all the needed vendor prefixes in it. At the moment `-webkit` and `-moz` are needed.  
In case you don&#8217;t know what this does, it changes how the box-model works. If you have a `div` with `width: 200px;` and apply `padding: 20px;` to it, the `div` stays at 200 pixels width and the `padding` lets the content inside the `div` shrink instead of adding the pixels to the width and making the element bigger.  
I always thought the default behavior was strange but I didn&#8217;t know there was another way or if I had known, I couldn&#8217;t have used it because of lacking browser support. `border-box` doesn&#8217;t only make more sense to me, it&#8217;s also very cool if you work with fluid layouts. For example it allows you to define `width: 100%;` and also add `padding: 40px;` and the elements stays at exactly 100%. In the old days that wasn&#8217;t possible.  
There are some rare cases where you want to use `box-sizing: content-box;`, but then it&#8217;s no problem to just do it.

So that&#8217;s my simple CSS reset and my thoughts that went into it. How about you, are you using a fancy blown-up CSS reset or is yours similar to mine?

 [1]: http://necolas.github.com/normalize.css/