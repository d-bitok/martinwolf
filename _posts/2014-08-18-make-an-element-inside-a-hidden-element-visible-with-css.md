---
title: Make an element inside a hidden element visible with CSS
author: Martin Wolf
layout: post
permalink: /2014/08/18/make-an-element-inside-a-hidden-element-visible-with-css/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"501415672241750016";s:5:"pDate";s:19:"2014-08-18 17:09:46";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_751448578251760";s:5:"pDate";s:19:"2014-08-18 17:09:51";}}";'
categories:
  - Articles
tags:
  - codepen
  - css
  - did you know
  - hidden
  - opacity
  - visibility
---
**Let&#8217;s imagine the following scenario: You have an element that should be hidden but one of the elements inside it should be visible. I&#8217;m sure everyone has had this problem before and tried to force it with `opacity`. At least I did.**

But that&#8217;s not possible. As soon as you set an element to `opacity: 0;` all of it&#8217;s children will forever be invisible.

<!--more-->

<div data-height="150" data-theme-id="1276" data-slug-hash="uLJEx" data-default-tab="html" class='codepen'>
  <pre><code>&lt;div class=&quot;opacity-0&quot;&gt;
  &lt;span&gt;I&#x27;m not visible&lt;/span&gt;
  &lt;span class=&quot;opacity-1&quot;&gt;I&#x27;m not visible&lt;/span&gt;
&lt;/div&gt;</code></pre>
  
  <p>
    See the Pen <a href='http://codepen.io/martinwolf/pen/uLJEx/'>uLJEx</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
  </p>
</div>



Same with `display: none;`. You can&#8217;t set a children back to `display: block;`.

<div data-height="150" data-theme-id="1276" data-slug-hash="rnFam" data-default-tab="html" class='codepen'>
  <pre><code>&lt;div class=&quot;display-none&quot;&gt;
  &lt;span&gt;I&#x27;m not visible&lt;/span&gt;
  &lt;span class=&quot;display-block&quot;&gt;I&#x27;m not visible&lt;/span&gt;
&lt;/div&gt;</code></pre>
  
  <p>
    See the Pen <a href='http://codepen.io/martinwolf/pen/rnFam/'>rnFam</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
  </p>
</div>



But a while back I learned that `visibility` actually behaves differently. You can set `visibility: hidden;` for a parent element and show a children element with `visibility: visible`.

<div data-height="150" data-theme-id="1276" data-slug-hash="IyEeb" data-default-tab="html" class='codepen'>
  <pre><code>&lt;div class=&quot;visibility-hidden&quot;&gt;
  &lt;span&gt;I&#x27;m not visible&lt;/span&gt;
  &lt;span class=&quot;visibility-visible&quot;&gt;I&#x27;m visible&lt;/span&gt;
&lt;/div&gt;</code></pre>
  
  <p>
    See the Pen <a href='http://codepen.io/martinwolf/pen/IyEeb/'>IyEeb</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
  </p>
</div>



Hope this helps!