---
title: Load CSS asynchronously with loadCSS
author: Martin Wolf
layout: post
permalink: /2014/12/18/load-css-asynchronously-with-loadcss/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_812829615446989";s:5:"pDate";s:19:"2014-12-16 10:24:06";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"544800129635844096";s:5:"pDate";s:19:"2014-12-16 10:24:07";}}";'
categories:
  - Articles
tags:
  - Async
  - asynchronously
  - Filament Group
  - javascript
  - loadCSS
  - performance
  - scott jehl
  - web performance
---
**The problem with CSS is that we can&#8217;t load it asynchronous natively. In contrast to the `script` tag there is no async attribute for the `link` tag.**

<pre><code class="lang-markup" >&lt;link rel="stylesheet" href="dist/css/style.min.css"&gt;
&lt;script src="dist/js/picturefill.min.js" async&gt;&lt;/script&gt;</code></pre>

You might think why on earth do I want to load CSS asynchronously, this would complete mess up the rendering of the site. You are right. But what if you want to load your webfonts CSS so you don&#8217;t block rendering only because of some custom fonts like I described in my latest article. Or what if you load the critical CSS which is needed to display the above the fold content synchronously and then load the rest of the pages CSS async so it doesn&#8217;t block rendering and your site is usable faster. There is no native way to doing that. You coudl put the CSS at the end of your page but this would still not make it load async, it just would get loaded later in the process.

<!--more-->

In my [last post about FOUT][1] and loading web fonts asynchronously I mentioned [loadCSS][2] by the Filament Group, or rather Scott Jehl. Scott created a little Javascript function which allows us to load CSS asynchronously. I have used it in several projects and it works perfectly. It&#8217;s really easy to use:

First you place the loadCSS function in the head of your site.  
Make sure to always grab the newest version [from GitHub][3] in case there was an update.

<pre><code class="lang-javascript" >&lt;script&gt;
    /*!
    loadCSS: load a CSS file asynchronously.
    [c]2014 @scottjehl, Filament Group, Inc.
    Licensed MIT
    */
    function loadCSS( href, before, media ){
        "use strict";
        var ss = window.document.createElement( "link" );
        var ref = before || window.document.getElementsByTagName( "script" )[ 0 ];
        var sheets = window.document.styleSheets;
        ss.rel = "stylesheet";
        ss.href = href;
        ss.media = "only x";
        ref.parentNode.insertBefore( ss, ref );
        function toggleMedia(){
            var defined;
            for( var i = 0; i &lt; sheets.length; i++ ){
                if( sheets[ i ].href && sheets[ i ].href.indexOf( href ) &gt; -1 ){
                    defined = true;
                }
            }
            if( defined ){
                ss.media = media || "all";
            }
            else {
                setTimeout( toggleMedia );
            }
        }
        toggleMedia();
        return ss;
    }
&lt;/script&gt;</code></pre>

Then you can pass the a stylesheet url into the function:

<pre><code class="lang-markup" >&lt;script&gt;
    loadCSS( "dist/css/non-critical-style.min.css" );
&lt;/script&gt;</code></pre>

It&#8217;s a good idea to also put a link tag into a noscript tag so users without Javascript still get the CSS.

<pre><code class="lang-markup" >&lt;noscript&gt;&lt;link rel="stylesheet" href="dist/css/non-critical-style.min.css"&lt;/noscript&gt;</code></pre>

There are also two optional arguments to the loadCSS function: `before` and `media`.

By default loadCSS inserts your stylesheet link tag before the first script tag in the DOM. If you don&#8217;t want that and like to decide where the link tag gets inserted, you can define the element before which the tag should be placed with the before argument:

<pre><code class="lang-javascript" >loadCSS( "dist/css/non-critical-style.min.css", window.document.getElementsByTagName( 'script' )[ 1 ] );</code></pre>

This would insert the stylesheet before the second `<script>` tag instead of the first.

With the media argument you can set the media attribute of the stylesheet. Default is `media="all"`:

<pre><code class="lang-javascript" >loadCSS( "dist/css/non-critical-style.min.css", "", "print" );</code></pre>

That&#8217;s it. Happy CSS async loading thanks to Scott Jehl!

 [1]: http://martinwolf.org/2014/12/15/why-fout-isnt-so-bad-after-all/
 [2]: https://github.com/filamentgroup/loadCSS
 [3]: https://github.com/filamentgroup/loadCSS/blob/master/loadCSS.js