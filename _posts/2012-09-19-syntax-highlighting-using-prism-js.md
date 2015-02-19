---
title: Syntax Highlighting using prism.js
author: Martin Wolf
layout: post
permalink: /2012/09/19/syntax-highlighting-using-prism-js/
categories:
  - Articles
tags:
  - prism.js
  - script
  - syntax highlighting
---
The development of this site is still very much in progress, so this morning I added Syntax Highlighting for future posts about CSS, HTML and maybe Javascript stuff. After seeing it in of Chris Coyier&#8217;s CSS-Tricks [Redesign screencasts][1] I decided to use [prism.js][2] by [Lea Verou][3] for that. It&#8217;s really simple, easy to use and lightweight. And it&#8217;s super nice for styling.

You basically just download the JS and CSS file and link it up in your document. Instead of adding an additional HTTP request for the CSS file I just import it in my main stylesheet.

Then you just write your code samples and add `class="language-css"`, `class="language-markup"` or `class="language-javascript"` to your `pre` and `code` tags. That&#8217;s all you&#8217;ve got to do.  
So here it is in action for some CSS code:

<pre class="language-css"><code class="language-css">.my-super-duper-class {
    color: #000;
    font-family: Arial, sans-serif;
    font-size: 16px;
}</code></pre>

 [1]: http://css-tricks.com/lodge/
 [2]: http://prismjs.com/
 [3]: http://lea.verou.me/