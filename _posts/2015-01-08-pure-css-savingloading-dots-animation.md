---
title: Pure CSS saving/loading dots animation
author: Martin Wolf
layout: post
permalink: /2015/01/08/pure-css-savingloading-dots-animation/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_830327117030572";s:5:"pDate";s:19:"2015-01-08 11:03:49";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"553145003342843904";s:5:"pDate";s:19:"2015-01-08 11:03:40";}}";'
categories:
  - Articles
tags:
  - animation
  - css
  - CSS animation
  - dots
  - keyframes
  - loading
  - saving
---
Inspired by the Instapaper iOS Saving Overlay I opened CodePen and built the saving dots animation with CSS and tweaked the animation a little bit. The result looks like that:

<p data-height="163" data-theme-id="1276" data-slug-hash="PwbEZo" data-default-tab="result" data-user="martinwolf" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/PwbEZo/'>Saving dots animation</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
</p>



<!--more-->

Let me explain how it works. First the HTML:

<pre><code class="lang-markup" >&lt;p class="saving"&gt;Saving&lt;span&gt;.&lt;/span&gt;&lt;span&gt;.&lt;/span&gt;&lt;span&gt;.&lt;/span&gt;&lt;/p&gt;</code></pre>

Each dot is wrapped in a `span` element and the whole thing will be controller by the `.saving` class.

To make the magic happen we need some CSS:

<pre><code class="lang-css">@keyframes blink {
    /**
     * At the start of the animation the dot
     * has an opacity of .2
     */
    0% {
      opacity: .2;
    }
    /**
     * At 20% the dot is fully visible and
     * then fades out slowly
     */
    20% {
      opacity: 1;
    }
    /**
     * Until it reaches an opacity of .2 and
     * the animation can start again
     */
    100% {
      opacity: .2;
    }
}

.saving span {
    /**
     * Use the blink animation, which is defined above
     */
    animation-name: blink;
    /**
     * The animation should take 1.4 seconds
     */
    animation-duration: 1.4s;
    /**
     * It will repeat itself forever
     */
    animation-iteration-count: infinite;
    /**
     * This makes sure that the starting style (opacity: .2)
     * of the animation is applied before the animation starts.
     * Otherwise we would see a short flash or would have
     * to set the default styling of the dots to the same
     * as the animation. Same applies for the ending styles.
     */
    animation-fill-mode: both;
}

.saving span:nth-child(2) {
    /**
     * Starts the animation of the third dot
     * with a delay of .2s, otherwise all dots
     * would animate at the same time
     */
    animation-delay: .2s;
}

.saving span:nth-child(3) {
    /**
     * Starts the animation of the third dot
     * with a delay of .4s, otherwise all dots
     * would animate at the same time
     */
    animation-delay: .4s;
}</code></pre>

This is only the minimal required code for making the animation work, no visual styles for formatting the text. In the CodePen example above I increased the `font-size` of the dots to make it look better.