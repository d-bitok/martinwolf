---
title: 'Use position relative &#038; absolute in tables'
author: Martin Wolf
layout: post
permalink: /2014/05/13/use-position-relative-absolute-in-tables/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:258:"a:1:{i:0;a:9:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";}}";'
snapTW:
  - 's:277:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"466247044127260672";s:5:"pDate";s:19:"2014-05-13 16:02:12";}}";'
categories:
  - Articles
tags:
  - absolute
  - css
  - hack
  - table
  - table layout
  - trick
---
Given that the days of building layouts with tables are long gone, we don&#8217;t have to use tables that often in our day to day developer lives. Or at least that&#8217;s the case for me. (Hang in there HTML e-mail builders. I feel you.)  
This means if I have to build a complex table it can get somewhat confusing from time to time. Recently I needed to position an element absolute inside a table cell.

As it turns out, table cells don&#8217;t like to be position relative to serve as a point of reference for the absolute positioned element inside it. Here is a little trick (or call it hack if you want to), to use position relative on a table cell and thus position elements absolute inside of it.

What you need to do is put a helper `div` inside your `td` which gets all the styling that you normally would have applied to your `td`, like `padding` or a `background-color` for example. This `div` will mimic your table cell and can get `position: relative;`

And here is how the code looks like as well as an not very good looking [example on CodePen][1].

This is the HTML for our little hack to work:

<pre><code class="lang-markup" >&lt;table cellpadding="0" cellspacing="0" border="0"&gt;
  &lt;tr&gt;
    &lt;td&gt;
      &lt;div&gt;my content &lt;span class="my-absolute-class"&gt;x&lt;/span&gt;&lt;/div&gt;
    &lt;/td&gt;
    &lt;td&gt;
      &lt;div&gt;more content&lt;/div&gt;
    &lt;/td&gt;
  &lt;tr&gt;
&lt;/table&gt;</code></pre>

And the corresponding CSS to make it complete:

<pre><code class="lang-scss">table {
  width: 300px;
  border: 1px solid #ccc;
  border-right: 0;
}

td &gt; div {
  position: relative;
  padding: 10px;
  border-right: 1px solid #ccc;
}

.my-absolute-class {
  position: absolute;
  top: 5px;
  right: 5px;
  padding: 0px 3px;
  color: #fff;
  background: #000;
}</code></pre>

<p data-height="180" data-theme-id="3560" data-slug-hash="esliL" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/esliL/'>Position relative/absolute in tables</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>.
</p>



### Update

It&#8217;s pointed out to me on Twitter by [@niksy][2], that this solution fails if you are dealing with multiline cells. As far as I can see, the only solution to this problem is to use Javascript to set the height of the helper `div` as tall as the `td` — on load and on resize if the height of the td changes in a responsive environment.

 [1]: http://codepen.io/martinwolf/pen/esliL
 [2]: https://twitter.com/niksy