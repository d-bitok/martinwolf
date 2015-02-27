---
title: New Site - Thoughts and Considerations
layout: post
permalink: /2015/02/24/new-site-thoughts-considerations/
---
**As you may have noticed I redesigned this very site. Since going freelance I only had the blog which also acted as my portfolio of sorts**

Most of my early assignments came from friends or people that already knew me and my skills.

While time went on I got in contact with new people and potential clients and the question that came up a lot was what I have worked on, if I could show some references. I had these infos on the site, but kind of burried deep down in my about page.

It was time for a portfolio, but I didn't want to separate it too much from the blog and I wanted to keep blogging on martinwolf.org. So I decided to make the frontpage more like a portfolio homepage and link to blog articles fruther down the page. So I was able to put the focus on me and the projects I worked on instead of the blog posts. Most people get to the articles directly anyway.

I think this is a nice compromise and fellow developers in search for articles as well as potential clients get the best from the new site.

## Jekyll

Once again I fell in love with the idea to switch to Jekyll and this time I pulled through. Thanks to this [plugin](https://github.com/benbalter/wordpress-to-jekyll-exporter) I was able to super easily export all posts and pages from WordPress and drop them into Jekyll. There were only a few issues with tags that started with @. Deleting it was the easiest solution. Not that big of a deal in my opinion.

The power of Jekyll for me lies therein that it generates static HTML files. This means there is no database or server site language involved which makes sites a lot faster.

Furthermore I like that I can write posts in Markdown, which is possible with various WordPress plugins, but I always ran into issues with code examples. In the end something always wasn't working as I wanted so I wrote the posts in HTML.

Don't get me wrong. I love WordPress and it's possibilities are more or less endless. I use it heavily for client sites which demand more functionality than this site, but for the purpose of my portfolio/blog I just don't need it and Jekyll does a great job.  
Especially because I decided to drop the link posts and focus more on real articles, which means I won't post daily or even several times a day like I used to in the past.

Besides that I loved to tinker with Jekyll. Just like the old days, trying something new, getting excited and finally making it work.

## Gulp and Jekyll
First I had to figure out how to combine my gulp workflow (preprocessing Sass, adding vendor prefixes, minifying the CSS, etc) with building Jekyll, watching for changes and automatically rebuilding and serving it locally.

I found a gulpfile on GitHub which basically did that and I started to merge my own tasks with it and thus created my own personal gulpfile. It put it into a [gist](https://gist.github.com/martinwolf/b7e2c380c70e48782925) if you want to take a look.

## Browsersync
[Browsersync](http://browsersync.io/) is the new kid on the block, the cool one, the one everybody wants to hang out with. And so did I but I didn't find the time and motivation to really get to it. So this time I wanted to test it and see what all the fuss was about.  
So what is Browsersync? It's basically a more sophisticated LiveReload. It watches files for changes and reloads the browser of injects the CSS so a reload isn't necessary. But it can do so much more, as the name says, it syncs actions like scrolling or filling out input fiels across browsers. As I saw it the first time, it really felt like magic. You have to give browsersync a try.

## HTML Minification with Jekyll
When the redesign first went live the HTML wasn't minified, that's bad because it means the page size is bigger than it needs to be and minification whouldn't be a big deal. After a helpful pointer from [Philipp Rudloff](http://twitter.com/kleinfreund) I'm now using a Jekyll layout which compresses the HTML. The only thing you have to do is save the file and set the layout of your highest template to compress. If that's not working out for you, there is always the option to use custom settings.

## Critical CSS
The latest trend in frontend performance is to include the critical path CSS inline in the document so it can render the page as soon as possible without having to wait for the complete CSS file to download. This means you define an area (I used something around 1200x900px) for which you extract the CSS and inline that into the head of your site and then load the CSS async with [loadCSS](https://github.com/filamentgroup/loadCSS). This makes sure that the top area of your page is rendered as fast as possible while the rest of the page waits for the other styles. So the complete rendering of the page isn't faster but it feels much faster because the visible portion is usable earlier.

There are several tools that can help you to automatically extract the CSS. I use Addy Osmani's [critical](https://github.com/addyosmani/critical) as a gulp task. I recommend reading [this post](http://www.filamentgroup.com/lab/performance-rwd.html) by Scott Jehl on the topic of frontend performance and more tools to help you with it.

## Web Fonts
I use Typekit to serve the custom web fonts. I load the fonts asynchronously so the rendering of the page isn't blocked, so even if you are on a slow connection you can read the content, which is the most important part of the site, as well as interact with the page before the custom fonts are loaded.

## No Analytics
I decided to drop not only Google Analytics but analytics all together. This has two reasons: First, I've to load one external third party Javascript less, which means the site is faster and I'm in control of as much code as possible. Second, I looked at my stats very often, I'd say too often.  
Most of the time it just made my mood worse, which is a bad thing. I tried to not look at the stats daily because in the end I don't gain anything from it, but it didn't work, I just wouldn't stop. So I now chose to cut the rope and just don't include the tracker. This may seem exaggerated but it's an experiment that hopefully brings me some sort of peace of mind. I will just publish articles and do my thing without worrying to much about traffic.

I'm sure I will miss the long term view on the stats, say looking back at recent month or even year, but for now I have to try that.  
Saying that I may add it back in again after some time when I've hopefully learned to not give too much about stats.

## Any questions?
I hope the article was interesting or you learned something or feel inspired to improve your own site. If you have further questions or suggestions, feel free to send me a tweet at [@_martinwolf](http://twitter.com/_martinwolf) or an e-mail to [martin@martinwolf.org](mailto:martin@martinwolf.org).
