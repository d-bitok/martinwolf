---
title: Making use of the BEM naming system
author: Martin Wolf
layout: post
permalink: /2014/05/15/making-use-of-the-bem-naming-system/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:277:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"466849307224997888";s:5:"pDate";s:19:"2014-05-15 07:55:23";}}";'
snapFB:
  - 's:258:"a:1:{i:0;a:9:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";}}";'
categories:
  - Articles
tags:
  - bem
  - css
  - naming
  - structure
---
**I&#8217;m a big fan of the BEM way of writing CSS classes. I think besides from sometimes having a somewhat long class name it only has benefits. The biggest is it&#8217;s simplicity and clear structure.**

If you&#8217;ve never heard of BEM, here is a short introduction. BEM is short for Block Element Modifier and this is a simple example:

<pre><code class="lang-markup" >&lt;nav class="site-nav"&gt;
  &lt;a class="site-nav__item" href="#"&gt;Home&lt;/a&gt;
  &lt;a class="site-nav__item site-nav__item--active" href="#"&gt;About&lt;/a&gt;
  &lt;a class="site-nav__item" href="#"&gt;Contact&lt;/a&gt;
&lt;/nav&gt;</code></pre>

In this example `site-nav` is the Block, `site-nav__item` is the Element and `site-nav__item--active` is the modifier. Styling with these class selectors brings great flexibility because you could easily change the HTML elements, keep the classes and the CSS would keep working.  
A developer not familiar with the project will also be easily able to understand the system and can get an impression of the HTML structure from simply looking at the CSS.  
Furthermore it helps and encourages to write portable modules, which is what brings great flexibility.

<pre><code class="lang-css">.site-nav {
  margin-bottom: 20px;
  max-width: 300px;
}

.site-nav__item {
  display: inline-block;
  color: #000;
}

.site-nav__item--active {
  border-bottom: 1px solid;
}</code></pre>

There is more to it, but that&#8217;s enough to get the idea of the system. If you want to read more on the topic, [Harry Roberts][1] has a great detailed write-up.

Because the BEM naming system worked so well for me for CSS classes and I&#8217;m a big fan of structuring things in a simple, yet powerful way, I started using it elsewhere, too. I think SCSS variables are a great example for that. I transitioned into naming them this way:

<pre><code class="lang-scss">$grey: #a2a2a2;
$grey__dark: #535353;
$grey__dark--hover: #b2b2b2;

$header__height: 50px;
$header__height--fixed: 20px;</code></pre>

I also use it for file naming for example for images:

`icon__checkmark.svg`  
`icon__checkmark--active.svg`  
`header__bg.jpg`  
`header__logo.png`  
`header__logo--small.png`

I&#8217;m sure there are other areas where we could put the BEM way of naming things to good use and increase structure and ease of use. I&#8217;m curious to hear your ideas.

**Hit me up on Twitter [@_martinwolf][2].**

 [1]: http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/
 [2]: http://twitter.com/_martinwolf