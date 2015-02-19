---
title: How to make a transparent border with CSS
author: Martin Wolf
layout: post
permalink: /2012/10/17/how-to-make-a-transparent-border-in-css/
categories:
  - Articles
tags:
  - border
  - box-shadow
  - css
  - css3
  - opacity
  - snippet
  - transparent
---
Sadly there is no such thing as `border-opacity` in CSS. Yet. Luckily `box-shadow` is a very mighty CSS property and can help us make a transparent border.  
The only thing we have to do is take the blur out of the equation and use `rgba` for the color definition.

Let&#8217;s say we have two divs. One should have a transparent border on the outside and the other one on the inside.

<pre class="lang-markup"><code class="lang-markup">&lt;div class="box outside-border"&gt;&lt;/div&gt;

&lt;div class="box inside-border"&gt;&lt;/div&gt;</code></pre>

<pre class="lang-css"><code class="lang-css">.box {
    margin: 0 auto 40px auto;
    width: 300px;
    height: 120px;
    background: #529db5;
}

.outer {
    box-shadow: 0 0 0 10px rgba(0,0,0,0.3);
}

.inner {
    box-shadow: inset 0 0 0 10px rgba(0,0,0,0.3);   
}</code></pre>

It&#8217;s as simple as that. You just define how much bigger the &#8220;shadow&#8221; should be as the box and then define your color. In this case it&#8217;s black with an opacity of 0.3.  
And this is how it looks like:

<img src="http://theamazingweb.net/wp-content/uploads/2012/10/transparent-border-with-css.gif" alt="" title="transparent-border-with-css" width="540" height="377" class="alignnone size-full wp-image-563" /> 

Yeah, you&#8217;re right, you could have done this with a solid color but what if the background changes? Or the background is an image? You get my point.  
As always I made a [Pen on CodePen][1] to play around with it.

 [1]: http://codepen.io/martinwolf/pen/Jkhdm