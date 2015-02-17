---
title: Detect if embedded tweet has been loaded
author: Martin Wolf
layout: post
permalink: /2015/02/02/detect-if-embedded-tweet-has-been-loaded/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_844254995637784";s:5:"pDate";s:19:"2015-02-02 17:35:44";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"562303376822919172";s:5:"pDate";s:19:"2015-02-02 17:35:46";}}";'
categories:
  - Articles
tags:
  - bind
  - embed tweet
  - javascript
  - js
  - twitter
---
When you want embed a tweet into your site you get some code along the lines of that from Twitter:

{% highlight html %}
<blockquote class="twitter-tweet" lang="en"><p>Web fonts have the potential to be as flexible and responsive as the layouts they exist within, says <a href="https://twitter.com/NickSherman">@nicksherman</a>: <a href="http://t.co/PYjxJ3028Z">http://t.co/PYjxJ3028Z</a></p>&mdash; A List Apart (@alistapart) <a href="https://twitter.com/alistapart/status/560225824897396737">January 28, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
{% endhighlight %}

As you can see that&#8217;s a `blockquote` which contains the tweet as well as a link to the tweet. In addition to that there is a `<script>` tag which asynchronously loads the `widgets.js` from twitter. That&#8217;s good because if you embed a tweet into a site this won&#8217;t block the rendering. After the file is loaded, it injects the full tweet into the site.

While this is a good procedure, there is no way to know when the tweet is loaded and rendered as intended. Recently that got me into trouble because I needed to know the dimensions of the completely loaded tweet before I could proceed.

After some searching through the [Twitter Developers site][1] I found what I was looking for.

## The solution

First we load the `widgets.js` right before the closing </body> tag like that and omit the script element when we copy the tweet embed code:

{% highlight html %}
<script>window.twttr = (function(d, s, id) {
  var js, fjs = d.getElementsByTagName(s)[0],
    t = window.twttr || {};
  if (d.getElementById(id)) return;
  js = d.createElement(s);
  js.id = id;
  js.src = "https://platform.twitter.com/widgets.js";
  fjs.parentNode.insertBefore(js, fjs);

  t._e = [];
  t.ready = function(f) {
    t._e.push(f);
  };

  return t;
}(document, "script", "twitter-wjs"));</script>
{% endhighlight %}

Next we set up the Twitter Scripting Events in our javascript file which will allow us to detect if the tweet has been fully loaded and rendered.

{% highlight javascript %}
twttr.ready(function (twttr) {
    // At this point the widget.js file had been loaded.
    // We can now make use of the twttr events
    twttr.events.bind('rendered', function (event) {
         // At this point the tweet as been fully loaded
         // and rendered and you we can proceed with our Javascript
        console.log("Created widget", event.target.id);
    });
});
{% endhighlight %}

There are a bunch of other events you can bind to. You can find the complete list in the [Twitter Developer Documentation][2].

 [1]: https://dev.twitter.com/
 [2]: https://dev.twitter.com/web/javascript/events
