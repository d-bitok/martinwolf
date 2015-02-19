---
title: 'WordPress: Links to articles exactly one year, one month and one week ago'
author: Martin Wolf
layout: post
permalink: /2014/10/30/wordpress-links-to-articles-exactly-one-year-one-month-and-one-week-ago/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:377:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_788908434505774";s:5:"pDate";s:19:"2014-10-30 11:22:01";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"527782473930145792";s:5:"pDate";s:19:"2014-10-30 11:22:02";}}";'
categories:
  - Articles
tags:
  - A Year Ago
  - Date
  - Permalinks
  - strtotime
  - wordpress
  - WordPress Snippet
  - WP Code
---
Recently I developed a simple WordPress Theme for a client and he wanted three links in the navigation which point to the posts exactly one year ago, one month ago and one week ago.

With the help from some friends in IRC I made it work without an additional plugin, which is always a priority for me when developing a WP Theme.

I&#8217;m everything but definitely no PHP expert or even a real PHP programmer so I&#8217;m sure you could easily write this more efficient. Feel free to post in the comments. Anyway, it works and it makes sense to me. Here it is:

<!--more-->

<pre><code class="lang-php" >&lt;?php
    $current_day = date('j');
    $current_month = date('n');
    $last_year = date('Y', strtotime('now - 1 year'));
    $last_month_day = date('j', strtotime('now - 1 month'));
    $last_month_month = date('n', strtotime('now - 1 month'));
    $last_month_year = date('Y', strtotime('now - 1 month'));
    $last_week_day = date('j', strtotime('now - 1 week'));
    $last_week_month = date('n', strtotime('now - 1 week'));
    $last_week_year = date('Y', strtotime('now - 1 week'));
?&gt;

&lt;nav&gt;
    &lt;ul&gt;
        &lt;li class="nav-list__item"&gt;
            &lt;?php
                query_posts('day='.$current_day.'&monthnum='.$current_month.'&year='.$last_year);
                if (have_posts()): while (have_posts()) : the_post();
            ?&gt;
            &lt;a class="nav-list__link" href="&lt;?php the_permalink(); ?&gt;"&gt;
                Heute vor einem Jahr
            &lt;/a&gt;
            &lt;?php
                endwhile; endif;
                wp_reset_query();
            ?&gt;
        &lt;/li&gt;
        &lt;li class="nav-list__item"&gt;
            &lt;?php
                query_posts('day='.$last_month_day.'&monthnum='.$last_month_month.'&year='.$last_month_year);
                if (have_posts()): while (have_posts()) : the_post();
            ?&gt;
            &lt;a class="nav-list__link" href="&lt;?php the_permalink(); ?&gt;"&gt;
                Heute vor einem Monat
            &lt;/a&gt;
            &lt;?php
                endwhile; endif;
                wp_reset_query();
            ?&gt;
        &lt;/li&gt;
        &lt;li class="nav-list__item"&gt;
            &lt;?php
                query_posts('day='.$last_week_day.'&monthnum='.$last_week_month.'&year='.$last_week_year);
                if (have_posts()): while (have_posts()) : the_post();
            ?&gt;
            &lt;a class="nav-list__link" href="&lt;?php the_permalink(); ?&gt;"&gt;
                Heute vor einer Woche
            &lt;/a&gt;
            &lt;?php
                endwhile; endif;
                wp_reset_query();
            ?&gt;
        &lt;/li&gt;
    &lt;/ul&gt;
&lt;/nav&gt;</code></pre>

Okay let me explain in detail. First off we get all the dates we will need later to query the permalink to the posts.

For the link to the post exactly one year ago we need the current day and the current month as well as the past year. You can get those with the PHP date function and the handy strototime function. You write what you would say you want the output to be and thanks to some magic it just works.

For the link to the post exactly one month and one week ago we let the PHP function do it&#8217;s magic again and ask for `now - 1 month` and `now - 1 week`.

You would think that you&#8217;d only need the current year and current month, but then you can get intro trouble in the first week of a new month and year.

After we have all the dates we need we use the WordPress function `query_posts` and pass in the parameters `day`, `monthnum` and `year`. Attention, it&#8217;s not `month`, but `monthnum`.

Then we write a standard WordPress loop, create the link and use the `the_permalink();` function for the `href` attribute. If there was more than one post on the specific date, you&#8217;ll get a link to each one.

**Don&#8217;t forget to reset the query after your loop with `wp_reset_query();` so the rest of the page functions normally.**  
If you don&#8217;t do that the rest of your page would use your custom `query_posts`.

You repeat this procedure for every link and then you are good to go. No extra WordPress Plugins needed.

I hope this was helpful and understanding to you.