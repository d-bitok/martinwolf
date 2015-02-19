---
title: Pushing to multiple git repositories simultaneously
author: Martin Wolf
layout: post
permalink: /2014/07/14/pushing-to-multiple-git-repositories-simultaneously/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_733957610000857";s:5:"pDate";s:19:"2014-07-14 09:34:37";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"488617554517454848";s:5:"pDate";s:19:"2014-07-14 09:34:37";}}";'
categories:
  - Articles
tags:
  - git
  - git push all
  - github
  - Owning Content
---
**I currently host private git repositories on my own server. This is relatively cheap and it gives me a feeling of security in case a service decides to shut down, gets hacked or whatever. It&#8217;s also in line with the [Develop It Yourself][1] methodology Bastian Allgeier wrote about recently.**

But we all know that GitHub is THE place for open source code and the programmer community. Sometimes it can even act as a kind of resume. So there is certain code I want to have on GitHub, but also on my own server.

<!--more-->

Luckily that&#8217;s very easy to achieve with no overhead because you can push to multiple repos with one command. The only thing you have to do is add both remotes to your git config. You have two options how to do this.

You can either go into your `.git` folder, open the `config` file and manually add the needed information like that:

<pre class="language-"><code>[remote "all"]
    url=ssh://url/to/repo.git
    url=ssh://another/url/to/repo.git</code></pre>

Or you can add the information from the command line:

<pre class="language-"><code>git config --add remote.all.url ssh://url/to/repo.git
git config --add remote.all.url ssh://another/url/to/repo.git</code></pre>

And now you can push to both repositories at the same time with

<pre class="language-"><code>git push all</code></pre>

And here an example of a project I simultaneously host on my server and on GitHub. The WordPress Theme of wolfsport.de, the soccer blog of my brother [I wrote about recently][2].

<http://git.horrido.io/projects/wolfsport/>  
<https://github.com/martinwolf/wolfsport>

 [1]: http://bastianallgeier.com/notes/diy
 [2]: http://martinwolf.org/2014/07/11/developing-wolfsport-de/