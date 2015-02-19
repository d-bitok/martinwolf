---
title: Test driving SASS and HAML
author: Martin Wolf
layout: post
permalink: /2013/05/11/test-driving-sass-and-haml/
categories:
  - Articles
tags:
  - code
  - css
  - experiment
  - haml
  - sass
  - scss
  - test
---
**I don&#8217;t remember exactly when I started to use a CSS preprocessor, but some time has gone by since then and now I can&#8217;t really imagine myself writing vanilla CSS and pass on variables, nesting and all that cool and helpful stuff.**

### SASS

I took my first steps in preprocessor-world with [LESS][1] before I later switched to [SCSS][2], because it seemed more popular, better maintained and all around more capable. SCSS stands for Sassy CSS and is basically SASS, but with a more CSS like syntax. This means you get to keep your beloved curly braces while the original SASS syntax completely abandons them. The SASS syntax also functions without semicolons.

I always felt both is weird and that curly braces in particular help maintaining a good visible structure in your documents.  
But recently I thought I could give the SASS syntax a go and just try it and see how it turns out.

<!--more-->

Let&#8217;s have a look at an simple example:

<pre><code class="lang-css">/* SASS */
.my-link-class
    color: #000
    text-decoration: none

    &:hover, &:focus
        color: #4640c9
        text-decoration: underline</code></pre>

<pre><code class="lang-scss">/* SCSS */
.my-link-class {
    color: #000;
    text-decoration: none;

    &:hover, &:focus {
        color: #4640c9;
        text-decoration: underline;
    }
}</code></pre>

The biggest problem is that tipying curly braces is so deeply ingrained in my muscle memory that it was really hard not to type them. Not using semicolons on the other hand is something I could get used to. But typing them isn&#8217;t much work and they also help structuring your code.

So while it was a fun experiment I&#8217;ll stick with the SCSS syntax. I just like how the curly braces help me stay on top of my document structure even if I have to nest really deeply. Which, we all know, shouldn&#8217;t happen too often.

### HAML

So while I&#8217;m using a CSS preprocessor all the time I never really considered using a HTML preprocessor. I always thought it&#8217;s kinda weird. But to really form an opinion one has to try it himself. It seemed that SASS and [HAML][3] are often used together and so I wrote the HTML for my little experiment with HAML instead of good old HTML.  
SCSS and CSS are farely similar and it&#8217;s easy to get started. But HAML is really different than HTML. For example, there are no closing tags, your structure is, as in SASS, just definied by indentation. Let&#8217;s look at some HAML code and the HTML output:

<pre><code class="lang-markup">.my-class
    %p.my-other-class
        Lorem ipsum</code></pre>

<pre><code class="lang-markup">&lt;div class="my-class"&gt;
    &lt;p class="my-other-class"&gt;
        Lorem ipsum
    &lt;/p&gt;
&lt;/div&gt;</code></pre>

While this looks cool in some way and it can save you some typing it really needs some time getting used to and learning the syntax. That&#8217;s just a simple example. If you want to do more cool stuff it get&#8217;s even weirder. Let&#8217;s have a look at a submit button:

<pre><code class="lang-markup">%input.login-submit{type: "submit", value: "Login" }</code></pre>

<pre><code class="lang-markup">&lt;input class="login-submit" type="submit" value="Login"&gt;</code></pre>

That&#8217;s more or less the same amount of code and I&#8217;m already extremely fast at crafting HTML and tools like Emmet or the basic code completion of our code editors are helping as well.

So, I&#8217;ll stick with basic HTML. No preprocessor is needed and I just understand the code much better and think it&#8217;s better structured. At least for me.

### Conclusion

I think it was good to take a look at SASS as well as HAML so I can say with confidence, that both are not for me and that I&#8217;m perfectly happy with SCSS and pure HTML.

In conducted my test on CodePen and made a little, fun login form.

<pre class="codepen" data-height="500" data-type="result" data-href="vxzbL" data-user="martinwolf" data-safe="true"><code></code><a href="http://codepen.io/martinwolf/pen/vxzbL">Check out this Pen!</a></pre>

 [1]: http://lesscss.org/
 [2]: http://sass-lang.com/
 [3]: http://haml.info/