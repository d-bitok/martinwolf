---
title: The QUOTE.fm Blockquote Style
author: Martin Wolf
layout: post
permalink: /2013/05/18/the-quote-fm-blockquote-style/
categories:
  - Articles
tags:
  - blockquote
  - codepen
  - QUOTE.fm
  - scss
  - span
---
**I got asked if I could make a CodePen with the signature blockquote style of QUOTE.fm. So here we go.**

The difficulty with this styling is that every line has padding on every side which is not really possible with CSS because you can&#8217;t target single lines. But somehow we can manage to pull it off with three nested `span` elements.

After some fiddling I asked Twitter and got a few different solutions from which I came up with this final markup. To be honest, I can&#8217;t really explain why or how it works. It&#8217;s definitely a hack and should be easier with CSS. Anyway, it works down to IE7, so I think we are good. (Okay, we need a small fix for Firefox&#8230;)

<pre><code class="lang-markup">&lt;blockquote class="quote"&gt;
    &lt;a href="http://theamazingweb.net"&gt;
        &lt;span class="quote-lvl1"&gt;
            &lt;span class="quote-lvl2"&gt;
                &lt;span class="quote-lvl3"&gt;
                    Lorem ipsum dolor sit amet. Lorem ipsum dolor sit lorem ipsum dolor sit amet delegetur su.m Lorem ipsum dolor sit amet. Lorem ipsum dolor sit lorem ipsum dolor sit amet de.legetur sum Lorem ipsum dolor sit amet. Lorem ipsum dolor sit lorem ipsum dolor sit amet delegetur sum.
                &lt;/span&gt;
            &lt;/span&gt;
        &lt;/span&gt;
    &lt;/a&gt;
&lt;/blockquote&gt;</code></pre>

<pre><code class="lang-scss">.quote {
    margin: 10px 0 5px 0;
    &gt; a {
        display: block;
        padding-left: 20px;
        font-size: 14px;
        font-weight: normal;
        color: #fff;
        line-height: 32px;
        &:hover {
            text-decoration: none;
        }
        &:active {
            position: relative;
            top: 1px;
        }
    }
}

.quote-lvl1,
.quote-lvl2,
.quote-lvl3 {
    position: relative;
}

.quote-lvl1,
.quote-lvl2 {
    padding: 6px 0;
    background: $qfmblue2;
    border-bottom: 1px solid #6ec5e9;
    .quote &gt; a:hover & {
        background: $qfmblue2Hover;
        border-bottom: 1px solid #5bbae1;
    }
}

.quote-lvl2 {
    right: 20px;
}

.quote-lvl3 {
    left: 10px;
}

@-moz-document url-prefix() {
    .quote-lvl1,
    .quote-lvl2 {
        padding: 6px 0 5px 0;
    }
}</code></pre>

And here you can see the code in action try fiddling with it yourself:

<pre class="codepen" data-height="300" data-type="result" data-href="lkfGJ" data-user="martinwolf" data-safe="true"><code></code><a href="http://codepen.io/martinwolf/pen/lkfGJ">Check out this Pen!</a></pre>