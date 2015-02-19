---
title: Fading out of text at the end of line
author: Martin Wolf
layout: post
permalink: /2012/10/28/fading-out-of-text/
categories:
  - Articles
tags:
  - fading
  - nowrap
  - pseudo element
  - text
---
**Sometimes you just don&#8217;t want a certain headline or just some line of text to wrap even if it doesn&#8217;t fit in it&#8217;s container. That&#8217;s easy, you just set `white-space: nowrap;` for the text and the surrounding box gets `overflow: hidden;`.**

But then the text just abruptly disappears on the edge of the box. That doesn&#8217;t look good. So while dealing with this problem at [QUOTE.fm][1] for an upcoming new feature I thought it&#8217;d be cool if the text just fades out at the end.

Thanks to a pseudo-element and a little bit of CSS3 this is very easy and doesn&#8217;t need any additional markup. And if a browser doesn&#8217;t support it, nothing breaks. It just doesn&#8217;t look so cool anymore.

<img src="http://theamazingweb.net/wp-content/uploads/2012/10/faded-out.png" alt="" title="faded-out" width="588" height="49" class="alignnone size-full wp-image-652" /> 

<pre class="lang-markup"><code class="lang-markup">&lt;div class="box"&gt;
    &lt;h1&gt;This is a very long headline, maybe even too long for this box.&lt;/h1&gt;
&lt;/div&gt;</code></pre>

<pre class="lang-css"><code class="lang-css">@import "compass/css3";

body {
  padding: 50px;
}

.box {
  max-width: 600px;
  overflow: hidden;
}

h1 {
  position: relative;
  white-space: nowrap;
  &:after {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    width: 30%;
    height: 100%;
    @include background-image(linear-gradient(left, rgba(255,255,255,0) 0%, white 80%, white 100%));
    pointer-events: none;
  }
}</code></pre>

So let&#8217;s see what we&#8217;ve got. There is a `div` with `overflow: hidden;` that has an `h1` in it that doesn&#8217;t wrap. So far nothing special. Then we use `:after` to make a box that is 20% wide and 100% tall. The percentage values are in relation to the dimensions of the `h1` because that has `position: relative;`. We position this box at the far right and top of the headline and give it a `linear-gradient`, which fades from transparent on the left to white on the right. We put a color stop in it so that it actually is completely white at 80%.

At last we set `pointer-events: none;` so that you can select the text under the fade.

That&#8217;s it. Pretty easy. And because we use percentage values and `max-width` for the container that thing is fully responsive.

If you wonder what the `@import`, `@include` and weird nesting is, you need to look at [SASS/SCSS][2] and [Compass][3] right now and come back if you understand and use it. Really, go. And if you have any questions feel free to ask. :)

*I made a little [CodePen][4] out of this so you can play around with it.*

 [1]: http://quote.fm
 [2]: http://sass-lang.com/
 [3]: http://compass-style.org/
 [4]: http://codepen.io/martinwolf/pen/DkKgJ