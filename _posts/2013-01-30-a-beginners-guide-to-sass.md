---
title: A beginners guide to SASS, part 1
author: Martin Wolf
layout: post
permalink: /2013/01/30/a-beginners-guide-to-sass/
categories:
  - Articles
tags:
  - beginner
  - codekit
  - css
  - guide
  - preprocessor
  - sass
  - scss
---
**Some of you might heave heard of CSS preprocessing and the popular languages involved: [SASS][1] and [LESS][2]. And I&#8217;m sure some or even most of you are using these on a daily basis. In the past I used SASS in my code examples here on TheAmazingWeb which might have been problematic for some of you who never have seen this syntax. So I thought it&#8217;s time to write a simple introduction to getting you started so that you understand what I&#8217;m talking about. And I&#8217;m sure as soon as you understand the potential you&#8217;ll use it on your own projects.**

### SASS or LESS?

I use SASS as my CSS preprocessor of choice with it the SCSS syntax. SASS and SCSS are basically the same but the SCSS syntax still uses braces where as the SASS syntax omits them completely. But I think this makes reading your SASS much more difficult.  
LESS is not that different from SASS but does a few things differently. Chris Coyier wrote a great comparison, if you want to know more about the differences. But I&#8217;d recommend using SASS.

### So how do I start?

Basically you write CSS as you always have but use a different file ending. In our case we use .scss. Then we use an app to compile a .css file from the .scss, because what we need to link in our sites is still the normal CSS file.

The app I would recommend using is [CodeKit][3]. I recently switched to using the command line with [Compass][4], but that&#8217;s another topic.

Just download the app, install it and drop your project folder in there. The rest is very self-explanatory. CodeKit detects your SCSS files and automatically compiles them to CSS. You can specify the output path and choose to compress your CSS, which I definitely recommend. CodeKit can do much more stuff for you, just have a look at it.

### Let&#8217;s see some SCSS magic

SCSS enables us to do a lot of cool stuff which normal CSS can&#8217;t do. So for example you can nest rules which makes crafting your CSS much easier and faster. Nevertheless, you need to always have in mind that you SCSS gets compiled into normal CSS in the end. So you save work but not actual bytes in form of less text.

Let&#8217;s look at an example.

<pre><code class="language-css">.page-header {
  width: 100%;
  height: 200px;
  &gt; p {
    color: #000;
  }
}</code></pre>

The SCSS above gets compiled to this CSS:

<pre><code class="language-css">.page-header {
  width: 100%;
  height: 200px;
}

.page-header &gt; p {
  color: #000;
}</code></pre>

So in our development SCSS file we are able to nest rules which saves us time and work. And the code looks nice and clear. While working with SCSS it&#8217;s tempting to nest your rules very deep, but this is just as bad as it was with normal CSS. So a good rule of thumb is not to nest deeper than three levels.

While nesting rules you have the &#8220;&&#8221; selector at your disposal which is a very simple yet powerful tool. Let me show you an example:

<pre><code class="language-css">a {
  color: #000;
  text-decoration: none;
  &:hover, &:focus {
    text-decoration: underline;
  }
  &:active {
    color: #0e78a4;
  }
}</code></pre>

Compiled CSS:

<pre><code class="language-css">a {
  color: #000;
  text-decoration: none;
}

a:hover, a:focus {
  text-decoration: underline;
}

a:active {
  color: #0e78a4;
}</code></pre>

So what we see here is that the &#8220;&&#8221; is a placeholder for the current selector, in this case the `a` tag. This does also work if you already have nested selectors, like that:

<pre><code class="language-css">.page-header {
  a {
    color: #000;
    text-decoration: none;
    &:hover, &:focus {
      text-decoration: underline;
    }
  }
}</code></pre>

Compiled CSS:

<pre><code class="language-css">.page-header a {
  color: #000;
  text-decoration: none;
}

.page-header a:hover, .page-header a:focus {
  text-decoration: underline;
}</code></pre>

But you can use the &#8220;&&#8221; in another very useful way. Let me show you:

<pre><code class="language-css">article {
  font-size: 1.1em;
  .home & {
    font-size: 1.4em;
  }
}</code></pre>

Compiled CSS:

<pre><code class="language-css">article {
  font-size: 1.1em;
}

.home article {
  font-size: 1.4em;
}</code></pre>

So the &#8220;&&#8221; is still a placeholder for your current selector but you can also place another selector in front of it. This comes in handy, too.

Variables are another very helpful thing you can use with SCSS. For example you could define a `$brandcolor` of your specific blue and every time you want something to style in blue who just use the variable. This is good because you get a consistent look throughout your whole site and if you need to change your brandcolor who just have to do it in one place. Or you could define a variable `$padding` and always use it if you need to space things out. There are endless possibilities of what you can do.  
Variables work as follow:

<pre><code class="language-css">$brandcolor: #0e78a4;

.logo {
  color: $brandcolor;
}

a {
  border-bottom: 1px solid $brandcolor;
}</code></pre>

Compiled CSS:

<pre><code class="language-css">.logo {
  color: #0e78a4;
}

a {
  border-bottom: 1px solid #0e78a4;
}</code></pre>

### Wrap-up

These are just a few simple things SASS and a CSS preprocessor can do four you. We barely scratched the surface of the whole topic but I hope it got you hooked and you try it out.  
You not even need to start a new project. You can just rename your .css files to .scss and start right away. The basic CSS just stays like it is and you can write new selectors in SCSS. It&#8217;s that easy.

If you have any questions, don&#8217;t hesitate to ask in the comments section below. I&#8217;ve already planned part 2 with another set of cool things you can do with SCSS. But if you don&#8217;t want to wait, you can find all you can do with SCSS here: <http://sass-lang.com>

Have a nice day!

 [1]: http://sass-lang.com/
 [2]: http://lesscss.org/
 [3]: http://incident57.com/codekit/
 [4]: http://compass-style.org/