---
title: 'Postion: -webkit-sticky test'
author: Martin Wolf
layout: post
permalink: /2013/09/19/postion-webkit-sticky-test/
categories:
  - Articles
tags:
  - code
  - codepen
  - css
  - sticky
  - webkit
---
With the introduction of iOS7 we also get a new mobile Safari which, as the upcoming Safari 6.1 for desktops, supports `position: -webkit-sticky;`. This is something like a hybrid of `position: static` and `fixed`. The element is static until it&#8217;d be scrolled out of the viewport and then gets fixed. It&#8217;s easy to implement and would be a nice addition to our CSS tool belt if it gets implemented in every major browser.

You can see it in action in this CodePen. Remember: Only on Safari for iOS7 or Safari 6.1 beta.

**Update:** The CodePen only works with Safari 6.1 and not on iOS. That&#8217;s because of some iframe embed issue thingy I think. But I tested it locally on iOS7 and it works fine.  
**Update:** Another update! Chrome 29 implemented `position: sticky;`. Prefix free! \o/

<p data-height="374" data-theme-id="1276" data-slug-hash="JgolK" data-user="martinwolf" data-default-tab="result" class='codepen'>
  See the Pen <a href='http://codepen.io/martinwolf/pen/JgolK'>Postion: -webkit-sticky test</a> by Martin Wolf (<a href='http://codepen.io/martinwolf'>@martinwolf</a>) on <a href='http://codepen.io'>CodePen</a>
</p>