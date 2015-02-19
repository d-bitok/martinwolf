---
title: 'Fixing display: inline-block;'
author: Martin Wolf
layout: post
permalink: /2013/06/24/fixing-display-inline-block/
categories:
  - Articles
tags:
  - css
  - fix
  - hack
  - inline-block
  - trick
---
**Floating elements always have the problem that the float needs to be cleared sooner or later. It would be so much nicer to just position a bunch of elements beside each other and we already have the tools at our disposal to do exactly that: `display: inline-block;`.**

The only problem this brings with it is that elements which are displayed as `inline-block` have a little gap between each other. As far as my research goes this gap is always `4px` wide. I have no idea why this amount and it surprises me that all browsers use the same number but hey, let&#8217;s just be happy about it. So all we need to do to make this work is eliminating the gap.

Let&#8217;s say we want to craft a simple navigation menu. We have an `ul` with some `li`&#8216;s which each contains an `a` element. The list item will be positioned as `inline-block` so we can have them horizontally beside each other. Then we do the magic and give the whole list `letter-spacing: -0.31em`. This will eliminate the gap between the list items. To make sure the link is displayed normally, we set the `letter-spacing` back to `normal`.

Why `-0.31em` and not `4px` you ask? This is something [Harry Roberts][1] discovered and uses in his [CSSWizardry grids][2]. I wanted to know why and tried `-4px` and it works just fine until you zoom the page and I believe it also isn&#8217;t perfectly fine if the iPhone renders your page if you didn&#8217;t set your viewport to `width=device-width`. But if you use the magic number `-0.31em` the list items are always perfectly aligned. So I say, let&#8217;s just roll with it. And that&#8217;s it:

<pre><code class="lang-markup">&lt;nav role=&quot;navigation&quot;&gt;
    &lt;ul&gt;
        &lt;li&gt;
            &lt;a href=&quot;#&quot;&gt;Link&lt;/a&gt;
        &lt;/li&gt;
        &lt;li&gt;
            &lt;a href=&quot;#&quot;&gt;Link&lt;/a&gt;
        &lt;/li&gt;
        &lt;li&gt;
            &lt;a href=&quot;#&quot;&gt;Link&lt;/a&gt;
        &lt;/li&gt;
        &lt;li&gt;
            &lt;a href=&quot;#&quot;&gt;Link&lt;/a&gt;
        &lt;/li&gt;
        &lt;li&gt;
            &lt;a href=&quot;#&quot;&gt;Link&lt;/a&gt;
        &lt;/li&gt;
    &lt;/ul&gt;
&lt;/nav&gt;</code></pre>

<pre><code class="lang-scss">ul {
    list-style: none;
    font-size: 1em;
    letter-spacing: -0.31em;

    &gt; li {
        display: inline-block;
        letter-spacing: normal;
    }

    a {
        display: block;
        padding: 0.7em 1em;
        color: #fff;
        text-decoration: none;
        background: #e68a7d;
        &:hover, &:focus {
            background: darken(#e68a7d, 7%);
        }
    }
}</code></pre>

And as always I created a [CodePen][3] so you can hack and slay some code.

 [1]: http://csswizardry.com
 [2]: https://github.com/csswizardry/csswizardry-grids
 [3]: http://codepen.io/martinwolf/pen/JsCnB