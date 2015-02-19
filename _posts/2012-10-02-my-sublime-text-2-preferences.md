---
title: My Sublime Text 2 Preferences
author: Martin Wolf
layout: post
permalink: /2012/10/02/my-sublime-text-2-preferences/
categories:
  - Articles
tags:
  - configuration
  - customization
  - preferences
  - soda dark
  - sublime text 2
  - syntax highlighting
  - tomorrow night
---
[Sublime Text 2][1] is in some ways a little bit different than most editors or apps in general. For example, there is no preference menu like the ones you know. You can set a few things but most of the preferences you just type in a simple file. I think that&#8217;s fine for a code editor. The cool thing is that everybody can easily share his or her preferences file and you can see how others configured their Sublime Text and get inspired to try new things.

Because I love Sublime Text 2 and I hope some of you do too I wanted to show you my preferences file and ask you to share yours.

Just create a post on your own blog or put it up somewhere else and link back here/send me a link. I&#8217;ll collect the [trackbacks][2]/[e-mails][3]/[@replies][4] and if we get together a bunch of preferences I&#8217;ll make a post about them.

So this is mine:

<pre class="language-javascript"><code class="language-javascript">{
	"theme": "Soda Dark.sublime-theme",
	"color_scheme": "Packages/User/Tomorrow-Night.tmTheme",
	"font_face": "Source Code Pro",
	// "font_face": "Menlo",
	"font_size": 13.0,
	"word_wrap": "true",
	"highlight_line": true,
	"line_padding_bottom": 1,
	"translate_tabs_to_spaces": true,
	"tab_size": 4
}</code></pre>

I never used a dark color scheme for a text editor before I started using Sublime Text 2. I tried it for a while and it grow on me. I use the [Soda Dark Sublime Theme][5] for all the interface elements and the [Tomorrow Night color scheme][6] for the actual syntax highlighting.

As my font I chose the new [Source Code Pro][7] from Adobe – before I used Menlo. I bumped up the font size to 13 with a line padding bottom of 1. This makes everything a little bit better to read in my opinion. I set the `word_wrap` to `true` because I don&#8217;t like to scroll horizontally. Now the lines just wrap, that&#8217;s perfect for me. I also activated the line highlighting, I think it&#8217;s just much easier to work that way. Especially nice when `word_wrap` is activated, too.

If I use the tab key to indent lines, my Sublime Text automatically translates the tabs to spaces. For me, one tab equals four blanks.

These are my Sublime Text 2 Preferences. Nothing too fancy, but I really like that I can customize my editor exactly how I want to. Now it&#8217;s your turn. I&#8217;m curious to see what your preferences look like.

 [1]: http://www.sublimetext.com/2
 [2]: http://theamazingweb.net/2012/10/02/my-sublime-text-2-preferences/
 [3]: mailto:martin@theamazingweb.net
 [4]: http://twitter.com/taw_net
 [5]: https://github.com/buymeasoda/soda-theme
 [6]: https://github.com/chriskempson/tomorrow-theme
 [7]: http://theamazingweb.net/2012/09/26/announcing-source-code-pro/