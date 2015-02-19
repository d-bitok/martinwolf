---
title: 'Q: How to find the right file in a WordPress Theme?'
author: Martin Wolf
layout: post
permalink: /2012/09/26/q-how-to-find-the-right-file-in-a-wordpress-theme/
is_submission:
  - 1
user_submit_url:
  - 
user_submit_ip:
  - 79.215.137.147
categories:
  - Reader Questions
tags:
  - comments
  - comments.php
  - functions.php
  - 'q&amp;a'
  - wordpress
---
Felix asked:

> As threatened via Twitter yesterday :)
> 
> As you can see here:  
> <http://www.felixklingpictures.com/2012/09/24/under-construction-european-central-bank/>  
> the comment date is written like: &#8220;1 Day ago&#8221; etc. I would like to change it (for example &#8220;25.09.2012, 17:43&#8243; or kick it out completely) but I don&#8217;t know in which file. How can I find the right file?
> 
> Thanks Martin :)

Im not sure what the best way is to find the right file if you&#8217;re new to WordPress, but this [blog post][1] should help you understanding WordPress themes in general.

In your case there should be a `comments.php` in your theme folder. If you can&#8217;t find the date in this file, it&#8217;s most likely that your theme uses a function to generate the comments which you would find in the `functions.php` of your theme.  
Everything you need to know about formatting the date and time is explained [here in the WordPress Codex][2].

 [1]: http://yoast.com/wordpress-theme-anatomy/
 [2]: http://codex.wordpress.org/Formatting_Date_and_Time