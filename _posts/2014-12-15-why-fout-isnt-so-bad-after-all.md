---
title: 'Why FOUT isn&#8217;t so bad after all'
author: Martin Wolf
layout: post
permalink: /2014/12/15/why-fout-isnt-so-bad-after-all/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_812138072182810";s:5:"pDate";s:19:"2014-12-15 09:24:42";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"544422811948032000";s:5:"pDate";s:19:"2014-12-15 09:24:48";}}";'
categories:
  - Articles
tags:
  - css
  - Flash of unstyled text
  - FOUT
  - javascript
  - Load Async
  - typekit
  - webfonts
---
**FOUT is an abbreviation of Flash Of Unstyled Text. All over the web you will read how bad it is and how to prevent it from happening. But today I will tell you that I&#8217;m happily living it and also explain why.**

Here is a gif showcasing FOUT:  
<img class="alignnone size-full wp-image-3263" srcset="http://martinwolf.org/wp-content/uploads/2014/12/fout.gif 710w, http://martinwolf.org/wp-content/uploads/2014/12/fout.gif 1420w, http://martinwolf.org/wp-content/uploads/2014/12/fout-360x91.gif 360w, http://martinwolf.org/wp-content/uploads/2014/12/fout.gif 720w, http://martinwolf.org/wp-content/uploads/2014/12/fout-280x71.gif 280w, http://martinwolf.org/wp-content/uploads/2014/12/fout-560x142.gif 560w" sizes="(max-width: 640px) calc(100vw - 4rem), (max-width: 900px) calc(((100vw - 2rem) * 0.666) - 2rem), 710px" />

<!--more-->

FOUT happens when you use a custom web font and before it is fully loaded the fallback font is visible for a short period of time. If you use fonts from Typekit for example you have two different options. You can either load it synchronously and block the rendering of your text and possibly other ressources as well until the fonts are fully loaded or you can load the fonts with their async script.

The first one is obviously bad on two fronts because it prevents the text from showing up until the font is loaded and it also blocks all other assets from loading until it has finished. We definitely don&#8217;t want to load webfonts synchronously.

### Load Webfont Scripts Async

Because we want to load as many assets simultaneously as possible we can choose to load the fonts async with a script from Typekit.

<pre><code class="lang-javascript">&lt;script&gt;
    (function(d) {
        var config = {
        kitId: 'yourID',
        scriptTimeout: 3000
    }, h=d.documentElement,t=setTimeout(function(){h.className=h.className.replace(/\bwf-loading\b/g,"")+" wf-inactive";},config.scriptTimeout),tk=d.createElement("script"),f=false,s=d.getElementsByTagName("script")[0],a;h.className+=" wf-loading";tk.src='//use.typekit.net/'+config.kitId+'.js';tk.async=true;tk.onload=tk.onreadystatechange=function(){a=this.readyState;if(f||a&&a!="complete"&&a!="loaded")return;f=true;clearTimeout(t);try{Typekit.load(config)}catch(e){}};s.parentNode.insertBefore(tk,s)
    })(document);
&lt;/script&gt;</code></pre>

This will eliminate the problem that the loading of the fonts block the loading of other assets. But because this will result in FOUT because the user first sees the fallback font as long as the Typekit font hasn&#8217;t finished loading, Typekit suggests that you hide all text until the custom webfont is ready for usage.

<pre><code class="lang-css">.wf-loading h1 {
    visibility: hidden;
}
 
.wf-active h1 {
    visibility: visible;
}</code></pre>

**This is a bad Idea.**

While this prevents FOUT and looks a little bit nicer, it also hides the most important part of your website while you wait for files from a third party service. What if the Typekit servers have trouble? Then your site is practially unusable. The same goes for users on slow connections. I was on vaction and only had a terrible EDGE connection and wanted to look up something real quick on a site I built. I stared at the screen and waited for a webfont to load before I could identify the links on the homepage so I could go to the desired page. I couldn&#8217;t have cared less for that custom font. I just wanted to see the content. After this experience I think different about webfonts and FOUT. And the importance of performance in general.

### Load CSS async with loadCSS

So if you use custom web fonts make sure they load async. Your users will thank you.  
If you don&#8217;t use a third party service which provides you with an async script, take a look at Scott Jehls [loadCSS()][1] script which allows you to load (your web fonts) CSS asynchronously.  
I will write a post on loadCSS in the future if you like me to do so.

**In my opinion the most important thing for the user is a site that&#8217;s usable as fast as possible.** And if the user is on a fast connection he&#8217;ll barely notice the flash or the fonts are cached anyway. I think this is overall a much better user experience.

 [1]: https://github.com/filamentgroup/loadCSS