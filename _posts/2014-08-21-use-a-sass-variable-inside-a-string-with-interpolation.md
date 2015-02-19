---
title: Use a Sass variable inside a string with Interpolation
author: Martin Wolf
layout: post
permalink: /2014/08/21/use-a-sass-variable-inside-a-string-with-interpolation/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_752588918137726";s:5:"pDate";s:19:"2014-08-21 09:03:06";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"502380365408124928";s:5:"pDate";s:19:"2014-08-21 09:03:07";}}";'
categories:
  - Articles
tags:
  - Interpolation
  - sass
  - scss
  - Strings
  - variables
---
One of my favourite features of Sass are [variables][1]. Let&#8217;s say you define a variable like that:

<pre><code class="lang-scss">$wrap-width: 1200px;</code></pre>

And then you want to use that variable inside a string of another one, for example a media query variable. Then this **won&#8217;t work**:

<pre><code class="lang-scss">$mq--wrap: '(max-width: $wrap-width)';</code></pre>

<!--more-->

Instead you need to use the [#{} interpolation syntax][2] of Sass, like that:

<pre><code class="lang-scss">$mq--wrap: '(max-width: #{$wrap-width})';</code></pre>

This way Sass recognises `$wrap-with` as a variable and replaces it with `1200px`.

You also need to interpolate a variable if you want to do something like this:

<pre><code class="lang-scss">$gap: 20px;

.my-class {
    margin-top: -#{$gap};
}</code></pre>

This will generate to following output:

<pre><code class="lang-scss">.my-class {
    margin-top: -20px;
}</code></pre>

### UPDATE:

It turns out the last example is wrong. [Click here for proof][3]. At least in Sass v3.4.0. I could swear I had trouble with that somewhen in the past. Thanks [@FWeinb][4].

 [1]: http://sass-lang.com/documentation/file.SASS_REFERENCE.html#variables_
 [2]: http://sass-lang.com/documentation/file.SASS_REFERENCE.html#interpolation_
 [3]: http://sassmeister.com/gist/708157a9c4d1824dabb3
 [4]: https://twitter.com/fweinb/status/502384619682283520