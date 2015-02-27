---
title: IE7+8 friendly nth-child(x)
author: Martin Wolf
layout: post
permalink: /2015/01/22/ie78-friendly-nth-child/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_837920346271249";s:5:"pDate";s:19:"2015-01-22 11:19:11";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"558222342531579904";s:5:"pDate";s:19:"2015-01-22 11:19:12";}}";'
categories:
  - Articles
tags:
  - adjacent sibling
  - css
  - IE7
  - IE8
  - nth-child
  - Workaround
---
**Honestly, it has been a while since I had to think about IE7 or even IE8. Their usage dropped substantially over the past years and months. Sure, for certain audiences they are still a big topic, but luckily in the projects I worked on in the past I could happily ignore those and just was able to just focuse on IE9 and newer. What a nice new world.**

But as it turns out in the current project I&#8217;m working on we have to at least somehow consider IE7 and IE8 and make things work okay. A page doesn&#8217;t need to look the same in every browser, I hope we all have understood that by now, but the site should be usable and the key content should be consumable by your target audience.

<!--more-->

The CSS3 `nth-child` selectors are very helpful in a lot of different circumstances but are sadly not supported by IE7 and IE8. Luckily we can make something simple as `nth-child(2)` work in those browser with a nifty little trick using the adjacent sibling selector (`element1 + element2`) in combination with `:first-child`, which works in IE7 and IE8 because it&#8217;s a CSS2.1 selector. Attention, that does not apply to `:last-child`.

### How does it work?

This selects the second `li` which is a child of an `ul`. 

{% highlight css %}
ul li:nth-child(2) {
    /* ... */
}
{% endhighlight %}

Translated into the adjacent sibling selector syntax that means we want to select the adjacent sibling of the first `li` inside the `ul`.

<pre><code class="lang-css">ul li:first-child + li {
    /* ... */
}</code></pre>

With this method you can also select the 3rd, 4th, &#8230; `li`.

<pre><code class="lang-css">ul li:first-child + li + li {
    /* ... */
}</code></pre>

This would select the 3rd `li` inside the `ul`.  
Sadly that workaround doesn&#8217;t help with the more advanced CSS3 selectors like `nth-child(2n)`, `:nth-child(2n+5) or the aforementioned <code>:last-child`</code>.

As always I&#8217;ve put that code together in a [CodePen][1] so you can try it out:

<p data-height="370" data-theme-id="3560" data-slug-hash="VYboPr" data-default-tab="result" data-user="martinwolf" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/VYboPr/'>Using the adjacent sibling selector to simulate the nth-child(x) selector for IE7/IE8</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
</p>

 [1]: http://codepen.io/martinwolf/pen/VYboPr
