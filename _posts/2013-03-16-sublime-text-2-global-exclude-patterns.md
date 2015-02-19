---
title: 'Sublime Text 2: Global Exclude Patterns'
author: Martin Wolf
layout: post
permalink: /2013/03/16/sublime-text-2-global-exclude-patterns/
categories:
  - Articles
tags:
  - exclude patterns
  - preferences
  - scss
  - settings
  - sublime text 2
---
**In my opinion [Sublime Text 2][1] is a great text editor and I think if you read this blog you already know that.**

In ST2 you can create projects and every project can have specific settings. If you&#8217;re using SCSS you could for example hide all CSS files which you don&#8217;t need to edit anyway. You&#8217;re not only able to hide specific files or file types but also whole folders.  
Having this level of control over your projects is great but I thought that often it&#8217;d be even better if I could just set some basic rules for everything. Until recently I didn&#8217;t know that you can do that, so I thought it might be of interest to you. Here is how you do it:  
You go to &#8216;Sublime Text 2 -> Preferences -> Settings &#8211; User&#8217; or just hit `CMD + ,` on Mac and here you can add and edit which files or folders you want to hide.  
So this is how my `folder_exclude_patterns` and `file_exclude_patterns` look like:

<pre><code class="language-javascript">{
    "folder_exclude_patterns": [".svn", ".git", ".sass-cache"],
    "file_exclude_patterns": [".DS_Store", "._*"]</code>
}</pre>

It&#8217;s important to know that these patterns override the default patterns from &#8220;Settings &#8211; Default&#8221;. You could add your patterns there, but these settings get overridden on every app update.

 [1]: http://www.sublimetext.com/2