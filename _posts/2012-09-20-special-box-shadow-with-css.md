---
title: Cool box-shadow with CSS
author: Martin Wolf
layout: post
permalink: /2012/09/20/special-box-shadow-with-css/
categories:
  - Articles
tags:
  - box-shadow
  - css
  - css3
  - effect
  - tutorial
---
Below the header of The Amazing Web you can see a subtle box shadow that is smaller on both sides and thus the header looks like it&#8217;s standing out a little bit. It just looks nicer than a standard box shadow which I used in the early stages of the design process. Then Nico pointed me to his german [tutorial][1] on creating a cooler box shadow with CSS. It&#8217;s a clever solution which I then changed just a little bit. This is my solution:

<pre class="language-markup"><code class="language-markup">&lt;div class="box"&gt;
    &lt;p&gt;Put as much HTML in here as you like.&lt;/p&gt;
&lt;/div&gt;</code></pre>

<pre class="language-css"><code class="language-css">.box {
    position: relative;
    margin: 0 auto 80px;
    padding: 70px 0 40px;
    max-width: 840px;
    text-align: center;
    background: #fff;
}

.box:after {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 4px;
    -webkit-border-radius: 50%;
            border-radius: 50%;
    -webkit-box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
       -moz-box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
    z-index: -1;
}</code></pre>

By using an pseudo element (I love pseudo elements) you don&#8217;t need an additional element for creating the shadow. This pseudo element basically creates an oval shaped element with a box shadow. By positioning it at the bottom of and behind your `.box` element we create the illusion that the box shadow gets smaller on both sides. Don&#8217;t forget to define a background color for `.box` to mask the upper half of the box shadow.

You can see the code in action and play with it on <a href="http://codepen.io/martinwolf/pen/aylso" target="_blank">CodePen</a>.

 [1]: http://www.stadtpirat.net/post/25852112426/gebogener-schlagschatten-mit-css