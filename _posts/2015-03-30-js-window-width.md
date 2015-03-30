---
title: Window and viewport width in CSS and Javascript
layout: post
permalink: /2015/03/30/window-and-viewport-width-in-css-and-javascript/
---
**Let’s talk about the widths of the viewport and window in CSS and Javascript.**

If you write a CSS media query like `(min-width: 769px)` you don’t think long about which width is actually meant. It just works. The browser automatically does the right thing. If the viewport is `769px` wide or wider the media query returns true and the CSS will be applied.

If you need the same behaviour in Javascript because you might want to initiate a script at a certain breakpoint it gets a little bit trickier if you don’t know what width you are looking for.

## Window != Viewport
CSS media queries react to the width of the browser window including the scrollbars. In other words: The viewport, not the window or website (the width of the html element).

On Mac OSX Yosemite in Chrome for example, `(min-width: 769px)` is true if the `html` element is `754px` wide. That’s because the scrollbar has a width of `15px`. Thus the viewport is `769px` wide.

## So what does that mean for our Javascript?
jQuery’s `.width()` as well as `.outerWidth()` will return `754px` for the `$(window)` width. That’s not the width our CSS media query reacts to.

If you want a Javascript to fire at the same time a CSS media query evaluates to true, you should reach for `window.innerWidth`  
This will return `769px`. It returns the width of the window including scrollbars.

There is also `window.outerWidth` which returns the width of the window including scrollbars and other window elements like the window border or the DevTools panel if you have it open and pinned to the side.

### Recap
**CSS Media Query**:  
Width of the window including scrollbars  
**jQuery $(window).width and $(window).outerWidth**:  
Width of the window without scrollbars  
**window.outerWidth**  
Width of the window including scrollbars and other elements like the window border or DevTools  
**window.innerWidth**  
Width of the window including scrollbars

### tl;dr
CSS Media Query width == window.innerWidth