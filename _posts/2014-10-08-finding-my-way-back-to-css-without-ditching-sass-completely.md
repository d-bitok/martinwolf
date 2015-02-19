---
title: Finding my way back to CSS without ditching Sass completely
author: Martin Wolf
layout: post
permalink: /2014/10/08/finding-my-way-back-to-css-without-ditching-sass-completely/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"519854041862787072";s:5:"pDate";s:19:"2014-10-08 14:17:16";}}";'
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_776473205749297";s:5:"pDate";s:19:"2014-10-08 14:17:23";}}";'
categories:
  - Articles
tags:
  - css
  - Guidelines
  - Preprocessors
  - sass
  - thinking
---
**When CSS preprocessors came out a few years ago I was blown away by the possibilities and as soon as I started to work with LESS (which I later switched to Sass) I thought that I never want to go back.**

## Fast forward a few years to the present

CSS preprocessors have matured and new ones have been born. After dozens of projects using Sass I feel very comfortable using it. I know what it can and what it can’t do. I know of it’s usefulness and why people, me included, love it. Despite all of that I’m currently stripping back my usage.

<!--more-->

## Why is that?

I assume a lot of developers, especially newer ones I guess, tend to forget that you are not writing Sass for your website. The browser won’t read Sass. It needs CSS after all. So however you get from your CSS preprocessor to your final CSS, in the end it will be a Cascading Stylesheet.

This means no matter how many awesome features like variables, calculations, nesting, extends, mixins and whatever you are using, it’s only for you and it’s important to remember what the actual CSS looks like. This is what matters to the browser and therefore for the user.

I have a few rules like “only nest two or max three levels” deep. “Don’t use complicated Sass functions”. “Keep variables to the minimum” and so on because I’m afraid of myself and that I forget the end result.

Look at your generated CSS files, not the minified ones, and see for yourself what you are producing and if that’s really what you want to send down the wire.

Over the past couple of weeks I thought about quitting Sass completely and going back to the roots of CSS. Just to see what it’s like and get a feel for it again. But there are a few things about Sass I really don’t wanna miss, for example my precious media query breakpoint mixin. Nevertheless it was actually quite eye opening to write a few media query without the help of my Sass mixin just to remember what it’s like and how much code a simple mixin might produce.

## Examples of my new Sass rules

One new rule for example is: No nesting, except for pseudo selectors (and probably pseudo elements) and media query mixins. This means I can still group things like this:

<pre><code class="lang-scss">a {
    color: #000;

    &:hover,
    &:focus {
        border-bottom: 1px solid #ccc;
    }
}

.my-module {
    font-size: 2rem;

        @include breakpoint(m) {
                font-size: 1.7rem;
        }
}</code></pre>

But on the other hand I’m now forced to write selectors myself and thus will hopefully nest even less than my 2 or 3 levels nesting rule. And if I do, I’m doing it on purpose and am aware of it. This means you will encounter things like that in my Sass files:

<pre><code class="lang-scss">.post h2 {
    font-size: 2rem;
}

.post p,
.post ul,
.post ol {
    margin-bottom: 1.5rem;
}</code></pre>

These are only a few example of how I’ll strip back my Sass usage. I think my new rules will develop over time while I’ll question every Sass feature that I’m using.

Happy CSSing!