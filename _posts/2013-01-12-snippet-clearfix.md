---
title: 'Snippet: clearfix'
author: Martin Wolf
layout: post
permalink: /2013/01/12/snippet-clearfix/
categories:
  - Snippets
tags:
  - clear
  - clearfix
  - css
  - float
  - scss
  - snippet
---
For the longest time I just used a `div` with the class of `clear` with just `clear: both;` but it turns out the following is better and these days the modern way (IE8 and up) to go. You can just apply the class `clearfix` to any element that has floating stuff inside and needs to be cleared. Works perfect and doesn&#8217;t need any additional markup.

<pre class="lang-css"><code class="lang-css">.clearfix {
    &:after {
        content: '';
        display: table;
        clear: both;
    }
}</code></pre>

In case you&#8217;re wondering what this confusing syntax is all about, have a look at [SASS/SCSS][1].

 [1]: http://sass-lang.com/