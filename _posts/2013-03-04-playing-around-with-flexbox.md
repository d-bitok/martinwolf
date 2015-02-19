---
title: Having fun with flexbox
author: Martin Wolf
layout: post
permalink: /2013/03/04/playing-around-with-flexbox/
categories:
  - Articles
tags:
  - css
  - flex
  - flexbox
  - future
  - layout
  - modules
---
**Inspired by Eric Meyer&#8217;s [talk][1] about the future of laying out webpages I played around with the upcoming flexbox box model.**

So far I think it&#8217;ll be great as soon as everything is settled and we don&#8217;t have to use dozens of prefixes. Chris Coyier had a [post][2] about flexbox that demonstrates the prefix-hell in detail. But after all we can get decent browser support with this.

As I was browsing the web and reading a lof of articles on the topic of flexbox I saw a lot of examples showing how you can put boxes side by side, each with a different width or automatically filling the spaces or some other fancy ways. Another popular example is the reordering of those boxes when the viewport gets smaller.  
As I was coding one of those simple examples I came across the problem that I wanted to have a header that stretches itself across the whole container width it was contained in. Below I wanted to have three boxes: navigation, main content and an aside. On smaller viewports I wanted to reorder my content so that the navigation goes above the header. That&#8217;s not a very common use case, but I thought it should be able to do. To achieve that I put everything in one flex container instead of having a header element on the top and a flex container with the three boxes besides each other underneath. At first I had real problems getting the layout I wanted because I wasn&#8217;t able to get the header 100% wide. Then I found `flex-flow: row wrap;`, which you can set for the flex container. First of all it makes sure the content is layed out horizontally, which is the default, and second it let&#8217;s the content wrap. By default flexbox puts everything in one row, which is called `nowrap`.

<img src="http://theamazingweb.net/wp-content/uploads/2013/03/flexbox-layout.png" alt="flexbox-layout" width="1001" height="322" class="alignnone size-full wp-image-1300" /> <img src="http://theamazingweb.net/wp-content/uploads/2013/03/Screen-Shot-2013-03-04-at-8.54.41-PM.png" alt="Screen Shot 2013-03-04 at 8.54.41 PM" width="590" height="453" class="alignnone size-full wp-image-1302" /> 

With this solution I could get what I wanted. But although I used all the prefixes I couldn&#8217;t get it to work in Firefox and Safari. So if you want to see it in action please use Chrome. Sorry about that. You can find my test on [CodePen][3]. Feel free to comment, heart or fork.

While browsing through the [W3C Candidate Recommendation of the Flexible Box Layout Model][4] I came across a lot of possible examples that I hadn&#8217;t known about. I think flexbox is capable of a lot more than we think about now and in the future we will look back at floats and wonder how we could have lived with that for so long. Just as we now look back at the table based layout days.

 [1]: http://theamazingweb.net/2013/03/03/eric-meyer-the-era-of-intentional-layout/
 [2]: http://css-tricks.com/using-flexbox/
 [3]: http://codepen.io/martinwolf/pen/kcnsF
 [4]: http://www.w3.org/TR/css3-flexbox/