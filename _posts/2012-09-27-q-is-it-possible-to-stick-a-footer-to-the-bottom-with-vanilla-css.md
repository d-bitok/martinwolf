---
title: 'Q: Is it possible to stick a footer to the bottom of a page with vanilla CSS?'
author: Martin Wolf
layout: post
permalink: /2012/09/27/q-is-it-possible-to-stick-a-footer-to-the-bottom-with-vanilla-css/
is_submission:
  - 1
user_submit_url:
  - janoelze
user_submit_ip:
  - 85.179.199.56
categories:
  - Reader Questions
tags:
  - bottom
  - box-sizing
  - css
  - footer
  - stick
  - vanilla css
---
[Jan][1] described the problem:

<img src="http://theamazingweb.net/wp-content/uploads/2012/09/question-browser-window.jpg" alt="" title="question-browser-window" width="500" height="1074" class="alignnone size-full wp-image-277" /> 

So I wasn&#8217;t entirely sure what [vanilla CSS][2] is exactly, but as I understand it you style everything without using classes or id&#8217;s.

Vanilla CSS hasn&#8217;t included any HTML5 tags yet, but I added a footer element to the HTML and CSS because we need a footer, right? So no class, just a footer. I also added `html` to the CSS because we need it. So here we go, this is all it takes:

<pre class="language-css"><code class="language-css">html {
    position: relative;
    height: 100%;
}
body {
    position: relative;
    min-height: 100%;
    margin: 0;
    padding-bottom: 250px;
    -webkit-box-sizing: border-box;
       -moz-box-sizing: border-box;
            box-sizing: border-box;
}

footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 200px;
    background: #6499e2;
}</code></pre>

Basically what we need to do is making sure that `html` and `body` are always as high as the viewport to position the footer at the absolute bottom of the page. If you resize the browser window the footer would lay on top of the content. To prevent that from happening we add a bigger `padding-bottom` to our body element than the footer is high. Because of `box-sizing: border-box` the padding-bottom isn&#8217;t added to the height of 100% of the body and voilà!

You can see the result here on [CodePen][3].

 [1]: http://twitter.com/janoelze
 [2]: http://www.vanillacss.com/
 [3]: http://codepen.io/martinwolf/full/yacnE