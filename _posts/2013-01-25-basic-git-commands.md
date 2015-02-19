---
title: Basic git commands
author: Martin Wolf
layout: post
permalink: /2013/01/25/basic-git-commands/
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:237:"a:1:{i:0;a:8:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";}}";'
snapTW:
  - 's:154:"a:1:{i:0;a:5:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";}}";'
categories:
  - Articles
tags:
  - command line
  - commands
  - git
  - github
  - terminal
---
I use Git(Hub) every day but always did so through the [GitHub app][1]. It&#8217;s a great and simple app with a nice gui but I always wanted to be able to do more with the terminal. Not just git related things, stuff in general like setting up an apache, using compass and so on.  
So I decided to just try it and use [iTerm 2][2] to commit and push my changes.  
It&#8217;s really not that hard and GitHub has a great [help section][3] for those of you who want to have a look.

Don&#8217;t get me wrong, it&#8217;s not necessarily better to use the command line but it&#8217;s just that I *want* to be able to do it. Another reason is that I like to use as few apps as possible. So if I can switch to only using the command line I could pass on GitHub, CodeKit and MAMP. Let&#8217;s see how far I&#8217;ll get.

So for my own reference I put together a small list with some basic git commands. I thought why not share them with you. So here they go:

<pre><code class="language-javascript">// Check status of files and branch
git status

// Add all changed, new or removed files to staging area
git add -A

// Add file.php to staging area
git add file.php

// Remove everything from staging area
git reset HEAD -- .

// Commit staged files
git commit -m "message"

// Automatically stage all changed files (not newly created ones) and commit them
git commit -am "message"

// Push changes to remote repo
git push

// Delete file.php and remove it from tracked files
git rm file.php

// Rename file.php to file-changed.php
git mv file.php file-changed.php

// Make new branch with branchname from current one
git checkout -b branchname

// Switch to existing branch branchname
git checkout branchname

// Delete branch branchname
git branch -d branchname

// Delete branch branchname remote
git push origin --delete branchname</code></pre>

 [1]: http://mac.github.com/
 [2]: http://www.iterm2.com/
 [3]: https://help.github.com/